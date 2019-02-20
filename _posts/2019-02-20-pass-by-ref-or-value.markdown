---
layout: post
title: "Pass by reference vs pass by value"
date: 2019-02-20 18:43:00 +1100
---

The idea of **pass** by reference and **pass** by value. If F1 calls F2, and F1 gives F2 a parameter P1 by value, then P1 is unaffected by F2, it is merely *used* by F2.

```C
void swap (int a, int b) {
	int c = a;
	a = b;
	b = c;
}
```

In the code above, passing a variable to the swap function by value would be useless, as the caller and the callee have two independent variables.

```C
int main () {
	int p = 1;
	int q = 2;
	swap (p, q);
	println("%d\n", p);
	return EXIT_SUCCESS;
}
```

What would be the value of p above? Noting that in C syntax, we have passed p and q by value.

---

So for the most part that's all fine, we often don't want to manipulate the original variable.

But what if we do?

At the moment, when we give the swap function our variable p, we are giving it p's value, not p itself. So we have to find out some way to give it p itself. And what is p?

P is a memory address that holds the value of p. Everything in a computer is somehow related to memory. And in this case what p is is a memory address. So when we pass in p we are saying 'access the value at this memory address and copy it into a new value a, which itself is a new memory address'.

So now we need a way to tell the compiler, don't *access* p's memory address, *use* p's memory address. So C uses something called a pointer to achieve this. It may seem a bit out of the blue, but remember that we already have a motivation for such a thing, and that the name is actually self-explanatory.

A pointer, points. It points to a memory address. That means that specifically, instead of storing the value at that memory address, it just stores the memory address. There are 3 pieces of syntax that need to be understood here:

```C
int* ptr;
int x = 1;
ptr = &x;
```

What the lines above show are int\* ptr, a pointer, being given the memory address of some var x. And that's the syntax we use to achieve it. Specifically, ptr now contains the address of x, and there are three ways of using ptr now:

1. We could get the value of x itself from ptr as so
```C
println("%d", *ptr);
```
2. We could use the memory address of x to change x's value
```C
*ptr = 10;
printf("%d\n", x);
```
What do you think will be printed out?

3. We could use the pointer in place of x entirely
```C
*ptr = 10;
printf("%d\n", *ptr);
```

So from that maybe you've built up a small intuition:
- & gets the address of the variable
- \* gets the value of the variable that pointer is pointing to

So you should be able to tell from that what happens if we just do this:

```C
ptr = 10;
```

You should get an error. As this will make the pointer point to the memory address 10.

So now you might be able to understand this program:

```C
int main() {
	int x = 1;
	int y = 2;
	int *p = &x;
	int *q = &y;

	p = q;
	*p = *p * 2;
	printf("%d, %d\n", *q, y);

	return 0;
}
```

And if you can understand that, you should have a crack at making the swap program work with pointers so that it prints 2.


```C
void swap (int a, int b) {
	int c = a;
	a = b;
	b = c;
}

int main () {
	int p = 1;
	int q = 2;
	swap (p, q);
	println("%d\n", p);
	return EXIT_SUCCESS;
}
```

As a hint, the program will require no extra variables. But the variables as they are may have to be changed.
