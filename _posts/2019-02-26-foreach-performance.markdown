---
layout: post
title: "Foreach performance in C#"
date: 2019-02-20 5:19:00 +1100
categories: performance
---

I was optimising code this week and specifically was looking at speeding up foreachloops. For our purposes we will look at two different types of foreach loops, the lambda foreach and the normal foreach.

I think that its important that we know what situation calls for each type.

So first, lets breakdown what the different types of foreach loops are doing differently to one another:

#Lambda foreach loop

A lambda expression is a gnarly thorn in my side. I hate the explanations I have gotten online for it with a passion.

Lets review the definition for one from the official C# documents:

```
A lambda expression is an anonymous function that you can use to create delegates or expression tree types.
```

What the hell does that mean? Well, perhaps obviously from this, you have to understand anonymous functions, delegates and expression trees to understand lambda expressions.

1. Delegates: They are essentially an interface for a single method. That is, they denote a method signature, without actually implementing the method. 

2. An expression tree is a tree of operators and operands and is actually difficult to explain. I recommend looking at [expression tree explanation](http://www.geeksforgeeks.org/expression-tree/). A cop-out I know but I feel like they're something to be revisited, perhaps in another blog post.

3. An anonymous method is a method without a name, just a body. Delegates only have a signature, anonymous methods only have a body. The compiler will just generate a name for you.

So from that a lambda function is a function with only a body. Parts of the Enumerable class use delegate functions, making lambda's convenient for looping and in general, lambda expressions are very useful for making a function quickly and easily in a situation where a complete function is not called for and mostly with little performance decrease.

---

Great, now to look at the performance of lambdas in foreach loops. Lambda expressions are convenient, but have a downside. **Each time** they are called, the compiler has to create a delegate. If creating this delegate leads to heap-based memory allocations, this can lead to a large amount of memory traffic.

However if there are no memory allocations then it can even be significantly faster due to a compiler optimisation. From Konrad Kokosa's book "Pro .NET Memory Management":

```
There is an important optimisation regarding lambda expressions.
If they do not close (capture) any data - most likely C# compiler will generate code to cache such a delegate instance as a static field
(so it will be allocated only once, at the first usage).
```

So what does 'close' mean? This is a concept that's fully known as **closures**. And it is another poorly explained pain in the bum. 

"A closure is a first class function with free variables that are bound in the lexical environment."

Back to definitions:

1. A first class function is pretty much a normal function to be honest. Like you call it, assign its return to a value, it takes in parameters etc.

2. Free variables are just variables outside of the scope of the function. So like this:

```cs
var free = "string here";
String func (string notFree)
{
	return free + notFree;
}
```

The input 'free' comes from outside the function, it is not passed as a parameter or declared inside the function, but is used inside the function, that is the definition of a free variable.

So lets examine some code that can seem ambiguous to some:

```cs
delegate void Action();

static void Main ()
{
	int x = 0;

	Action a = delegate { Console.WriteLine(x); };

	x = 1;

	a();
}
```
[ambiguous codes origin](https://web.archive.org/web/20150707082707/http://diditwith.net/PermaLink,guid,235646ae-3476-4893-899d-105e4d48c25b.aspx). 


What does it print out?

Well to me, it obviously prints out 1, as whether we are working by value or by reference or not, the time 'a' is called is when that memory address is accessed, it is not accessed at the delegate declaration.

Turns out I'm right (sorry reader, couldn't leave that one entirely up to you).

So this is in part a good piece of code for explaining closures. If you use a function that calls a free variable, then whatever happens to that variable will affect that function, as it has a reference to it, not a value, as it is not a parameter that can have its value copied in.

Now lets get a little trickier:

```cs
delegate void Action();

static Action GetAction()
{
	int x = 0;

	Action a = delegate { Console.WriteLine(x); }

	x = 1;

	return a;
}

static void Main()
{
	Action a = GetAction();

	a();
}
```

Now what will happen here? Note that x is now out of scope. It should not exist anymore after the function is finished calling. And yet it prints out 1. At this point an explanation I read online said it's "compiler magic". Infuriating.

So something at this point must occur to save that variable in a safe reference.

From the [C sharp language specification](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf) 9.2.8 on delegate types:

```
The closest equivalent of a delegate in C or C++ is a function pointer,
but whereas a function pointer can only reference static functions,
a delegate can reference both static and instance methods.
In the latter case, the delegate stores not only a reference to the method's entry point,
but also a reference to the object instance on which to invoke the method.
```

So in this case, essentially, x it getting 'promoted' from the stack to the heap. And how could it 'store' it? It would do so in a helper class, and make 'x' a field of that class (to be honest although I looked at the assembly of this myself, it wasn't clear what was going on except that it used a pointer for x).

So to the compiler the code actually looks like this:

```cs
delegate void Action();

sealed class ActionClosure
{
	public int x;

	public void AnonMethod()
	{
		Console.WriteLine(x);
	}
}

static Action GetAction()
{
	ActionClosure closure = new ActionClosure();
	closure.x = 0;

	Action a = new Action(closure.AnonMethod);

	closure.x = 1;
	
	return a;
}

static void Main()
{
	Action a = GetAction();

	a();
}
```

So at the start of the method, it creates the class "ActionClosure" (name chosen randomly), and uses references to 'x' from that class for the rest of the life of the program and the delegate 'a' is replaced with closure.AnonMethod from that same class.

Okay, so now hopefully you understand what happens with a closure but might not feel up to spotting one in the wild, or using one in your code. One step at a time, we're still really just trying to understand how **lambdas** work afterall.

---

Great, so if the lambda doesn't close data, that is, its not required to store any data, then the compiler will probably optimise it as a static, and you will only pay for the overhead of instantiating it once.

Now a normal foreach loop.

Foreach is a little tricky due to the fact that foreach pretty just works on anything with a public GetEnumerator() with a "bool MoveNext()" method and "? Current {get;}" property. And how it works is dependend on those implementations. For instance in a list it uses pointer to "next" and for arrays it might just use an int until it returns false (i.e. position >= length).

But its reasonably fast in its default state for lists and arrays though. And that's what matters.

---

So now lets have a look at performance when the methods don't 'close' data. This code creates a list of 100 char long strings using a random number generator between the values 65 and 90 (ascii values) with a seed of 1. Then runs a foreach loop, a lambda foreach loop, and a for loop to remove all the characters from the stringbuilder.

```cs
using BenchmarkDotNet.Attributes;
using BenchmarkDotNet.Running;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace foreach_perf
{
    class Program
    {
        static void Main(string[] args)
        {
            var summary = BenchmarkRunner.Run<LangForEachVSLambForEach>();
            Console.ReadKey();
        }
    }

    [MemoryDiagnoser]
    [DisassemblyDiagnoser(printSource:true, printIL:true)] 
    public class LangForEachVSLambForEach
    {

        List<StringBuilder> stringField;
        [IterationSetup]
        public void Setup()
        {
            List<StringBuilder> listOfStrings = new List<StringBuilder>();
            Random rnd = new Random(1);
            for(int i = 0; i < 100; i++)
            {
                StringBuilder randSb = makeRandSb(rnd);
                listOfStrings.Add(randSb);
            }
            stringField = listOfStrings;
        }

        [Benchmark]
        [MemoryDiagnoser]
        public int LambForEach ()
        {
            stringField.ForEach(x => x.Clear());
            return stringField.Count;
        }

        [Benchmark]
        [MemoryDiagnoser]
        public int For ()
        {
            for(int i = 0; i < stringField.Count; i++) {
                stringField[i].Clear();
            }
            return stringField.Count;
        }

        [Benchmark]
        [MemoryDiagnoser]
        public int LangForEach ()
        {
            foreach (var item in stringField)
            {
                item.Clear();
            }
            return stringField.Count;
        }

        public StringBuilder makeRandSb(Random rnd)
        {
            StringBuilder sb = new StringBuilder(100);
            for(int i = 0; i < 100; i++)
            {
                char c = (char) rnd.Next(65, 90); //ascii values
                sb.Append(c); 
            }
            
            return sb;
        }
    }
}
```

![for performance](/assets/2019-02-20-foreach-perf/forMethodsBench.jpg)

So we can see that a basic for loop is fastest? Why? Because it doesn't have to call "Current" and "MoveNext" for every element in the sequence like a for loop does. And we can see that lambda is faster due to the 'closure' optimisation.

Just for fun, according to the disassembly, the for loop has 55 total bytes of code, the normal foreach 129 and the lambda, 94. To be honest though, I think that its dishonest to think that that should lead to such a huge difference. The biggest difference in code performance is most likely to be memory intensive operations. For instance the easiest way to make the code faster is to make the strings shorter.


![Disassembly of for loops](/assets/2019-02-20-foreach-perf/foreach_perf.LangForEachVSLambForEach-asm.pretty.md)  I don't know how to link just to a file yet I'll get round to it.

Right so now we actually need to close some data and see which one is faster.

---


![Disassembly of for loops](/assets/2019-02-20-foreach-perf/forMethodsAllocBench/)


So I tested it by abusing immutable strings, allocating them in the creation of a new class, then changing them in a for loop. As you can see, realistically there is a minimal difference between ForEach and ForLamb, but we'll stick with foreach for now if allocations occur in the function. 

Basically due to closures, if there where many closures in a lambda foreach its performance would be degraded due to lots of promotions. However officially its probably not worth the time to optimise the whole codebase for each for loop. Instead just think before you write a lambda foreach.
