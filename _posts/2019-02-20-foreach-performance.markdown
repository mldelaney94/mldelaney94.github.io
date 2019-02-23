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

3. An anonymous method is a method without a name, just a body. Delegates only have a signature, anonymous methods only have a body. So they can be combined.

So from that a lambda function is a function with only a body. Parts of the Enumerable class use delegate functions, making lambda's convenient for looping and in general, lambda expressions are very useful for making a function quickly and easily in a situation where a complete function is not called for and mostly with little performance decrease.

---

Great, now to look at the performance of lambdas in foreach loops. Lambda expressions are convenient, but have a downside. **Each time** they are called, the compiler has to create a delegate. If creating this delegate leads to heap-based memory allocations, this can lead to a large amount of memory traffic.

However if there are no memory allocations then it can even be significantly faster due to a compiler optimisation. From Konrad Kokosa's book "Pro .NET Memory Management":

```
There is an important optimisation regarding lambda expressions. If they do not close (capture) any data - most likely C# compiler will generate code to cache such a delegate instance as a static field (so it will be allocated only once, at the first usage).
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
[ambiguous codes origin](https://web.archive/org/web/2015070782707/http://diditwith.net/Permalink,guid,235646ae-3476-4893-899d-105e4d48c25b.aspx). 


What does it print out?

Well to me, it obviously prints out 1, as whether we are working by value or by reference or not, the time 'a' is called is when that memory address is accessed, it is not accessed at the delegate declaration.

Turns out I'm right (sorry reader, couldn't leave that one entirely up to you).

So this is in part a good piece of code for explaining closures. If you use a function that calls a free variable, then whatever happens to that variable will affect that function, as it has a reference to it, not a value, and it is not a parameter that can have its value copied in.

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


