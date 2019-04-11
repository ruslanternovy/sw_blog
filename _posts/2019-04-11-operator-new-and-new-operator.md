---
layout: post
title:  "Overloading operator new"
date:   2019-04-10 1:11:15 -0500
categories: interview questions
---
This is a first post in series called "Interview questions".

New operator is pretty straight forward and it works according to the specification. But there can be several situation where creating objects in heap can be customized for different purposes. After reading several articles about overloading operator new I decided to summarize everything I read about the reasons for overloading operator new.

First of overloading operator new inside a class will cause usage of it only for this class. For this purposes a class member function can be used to overload the operator. If operator new was overloaded globally it means that it will be used as a globally overloaded operator new within the given namespace if it exists.

There are several reasons to why operator new can be overloaded:
1. Increase in performance using caching. When you do not free up memory and save pointers for free blocks.
2. Create memory for several different objects.
3. Create a logger for allocation/deallocation memory.

Finally it's a good practice as they say, unless it's a very specific reason for overloading operator new don't use it.
This post will likely be updated as I read more interesting information about overloading operator new.
