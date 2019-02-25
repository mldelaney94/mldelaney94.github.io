---
layout: post
title: "Reference types VS value types in C#"
---

A lot of the this post will reference Jon Skeet's blog posts on the subject. This is more or less written for my own understanding. Particularly I would think that jonskeet.uk/csharp/references.html would be far more beneficial for others than my blog itself.

---

So to start off, John says that a magazine is semantically value-based and a website with the same information is semantically reference-based.

This essentially makes sense to me, a page contains the data, and the website contains a reference to the site which contains the data. Its all about how many hoops we're jumping through to reach it.

```cs
using System;

struct PrintedPage
{
	public string Text;
}

class WebPage
{
	public string Text;
}
```

So above we have two types, all with the same information. A struct is a value type, and a class is a reference type.

```cs
class Demonstration
{
	static void Main()
	{
		PrintedPage originalPrintedPage = new PrintedPage();
		originalPrintedPage.Text = "Original printed text";

		PrintedPage copyOfPrintedPage = originalPrintedPage;

		copyOfPrintedPage.Text = "Changed printed text";

		Console.WriteLine ("originalPrintedPage={0}",
				originalPrintedPage.text);
	}
}
```

So what should happen here, to this value type? We should print "Original printed text", because copyOfPrintedPage, although its text is changed, is a separate object.

![originalPrintedPage=Original printed text](/assets/2019-02-20-ref-value-types-post/valueTypePrintOut.jpg)

---

Now for a reference type using the class WebPage

```cs
using System;

class Demo
{
	static void Main()
	{
		WebPage originalWebPage = new WebPage();
		originalWebPage.Text = "Original web text";

		WebPage copyOfWebPage = originalWebPage;

		copyOfWebPage.Text = "Changed web text";

		Console.WriteLine ("originalWebPage={0}",
					originalWebPage.Text);

		copyOfWebPage = new WebPage();
		copyOfWebPage.Text = "Changed web page again";

		Console.WriteLine ("originalWebPage={0}",
					originalWebPage.Text);
	}
}
```

In the code above we first assign a new WebPage to be 'equal' to the original webpage. When we do that, because a Class is a reference type by default, they are essentially pointers. As such, when we make copyOfWebPage = originalWebPage, we are really making a new pointer copyOfWebPage and giving it the address of originalWebPage to point to.

As such we would expect, when we print out the string that both 'classes' (pointers) have, to get the string contained in originalWebPage.

Now when we make a new webpage, this last bit was just done to nail the point home, it doesn't point to originalWebPage, so originalWebPage is unaffected by anything we do to it.


![originalWebPage=Original printed text](/assets/2019-02-20-ref-value-types-post/ref_types_output.jpg)

---

Now that we understand that some things are reference types and other things are value types, we have to understand how to handle these types in different situations. What if you want to use a reference type as a value type or vice versa? C sharp has the capability for this built in with the keywords 'ref', 'out' and 'params'.

'ref' is for when you want to pass a value type by reference:

```cs
struct IntHolder
{
	public int i;
}

class Demo
{
	public static void Main()
	{
		IntHolder a = new IntHolder();
		a.i = 5;

		foo(ref a);
		Console.WriteLine(a.i);
	}

	static void foo (ref IntHolder a)
	{
		a.i = 10;
	}
}
```

So if we have a function that takes in a reference, and we input a value type as a reference, then we should get an output of 10.

---

Right so we have covered passing value types (structs, ints) by reference using the ref keyword. Lets think about what 'passing a reference type by value'.

```cs
public class IntHolder
{
	public int i = 0;
}

class Demo
{
	public static void Main()
	{
		IntHolder a = new IntHolder();
		a.i = 5;

		foo(a);
		Console.WriteLine(a.i);
	}

	public static void foo (IntHolder a)
	{
		a = new IntHolder();
	}
}
```

Lets think about our current intuition for this code. It should print out 0, the default value of IntHolders member. But it doesn't, it prints out 5, why is this? Well it must be because 'a' is still pointing at the same memory location as before. This would indicate that the class 'a' is copied, including its memory locations, into foo. So when we change 'a's' members, we access their locations, but we don't actually change 'a' itself. According to Jon Skeet this is the most important thing to understand from the blog post.

---

So there is just out and params to understand from this point on.

Out is like ref, except that it creates an assumption. The assumption that the param has no value, and *must* be assigned one. Ref and out work the same, out just *requires* an assignment of value.

Params allow an arbitrary number of arguments to passed into a function as a one-dimensional array. Unlike out and ref, you don't need to include params at the time the function is called, only in the function declaration. The important notes to make about params is that it allows for a function to be called even when there are 0 arguments without a problem. And that it allows for you to makeup a parameter list like this:

```cs
public static int addTwoEach(1,2,3,4,5);
```

---

So this blog post was long, but we learned a few key points.

1. The biggest point is that reference types are not passed by reference. They are passed by value with the same references for their members.

2. Out and ref do the same thing, but out requires a declaration of value to the input param whilst ref does not (out assumes its unassigned, ref could be either).

3. Params allows for an arbitrary number of arguments from 0 to infinity instead of the normal 1 to infinity.
