---
layout: post
title: "Reference types VS value types in C#"
---

A lot of the this post will reference John Skeet's blog posts on the subject. This is more or less written for my own understanding. Particularly I would think that jonskeet.uk/csharp/references.html would be far more beneficial for others than my blog itself.

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

So what should happen here, to this value type? We should print "Original printed text", because copyOfPrintedPage, although its text is changed, is a separate object (tbh I don't know if object is the right word there).

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


![originalWebPage=Original printed text](/assets/2019-02-20-ref-value-types-post/ref_types_output.jpg)

So what we expect is that a copyOfWebPage should change the original page's text, as it is just pointing to the originalWebPage. But a new WebPage, being a new webpage, shoud not change the original webpage, as it is pointing to different data.
