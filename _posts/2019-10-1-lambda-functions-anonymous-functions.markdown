---
layout: post
title: "Lambda Functions and Anonymous functions"
date: 2019-10-1
---

# Anonymous functions



# What is a closure?

A closure is a combination of a function and a variable in that functions scope. 

# Javascript execution context

What happens when you run a function in Javascript?

Well to fully show what happens we need a complicated example:

```javascript
var message = 'Hello World';
function foo(message) {
    bar(message);
}
function bar(message) {
    console.log(message);
}
foo(message);
```

Javascript, being single-threaded, can really only handle one function at a time. But it still, as in this case, may have to deal with multiple function calls at once. In this example, bar is being called from within foo, meaning that foo must pause until bar is finished. This is handled with a stack called the 'Execution Context Stack'. It places foo onto the stack, then bar, and when bar finishes, pops bar, and continues with foo.

![checking](/assets/2019-10-1-lambda-functions-anonymous-functions/js_execution_stack_graphic.gif)



