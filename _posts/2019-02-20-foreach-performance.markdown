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

A lambda expression is simply a way of calling a function 


