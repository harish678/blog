---
author: "Harish Vutukuri"
title: "Iterators and Generators"
date: "2021-02-10"
description: "Guide to creating iterators and generators in python"
tags: ["python", "advanced"]
ShowToc: true
TocOpen: true
---

## **Iterator**

Iterator is an object that can loop over _iterable_ objects. We can use Iterator in for loops. A list is a well known Iterator.

### **Implementaion**

An object can be a Iterator, if we implement two methods:

1. `__iter__` - returns the object itself.
2. `__next__` - returns the next values and raises `StopIteration` exception when all objects are looped.

![](/images/it.png "Iterator")

---

## **Generator**

Generator functions allow you to declare a function that behaves like an iterator.

### **Implementaion**

#### <u>Method 1</u>

A simple and easy way to create a Generator is to replace a `return` statement with a `yield` statement in a function.

The difference is that while a `return` statement terminates a function entirely, `yield` statement pauses the function saving all its states and later continues from there on successive calls.

![](/images/gen1.png "Generator Method 1")

#### <u>Method 2</u>

An object can be a Generator, if we implement `__next__` method.

<u> **Note:** </u> In the above method the `yield` statement internally generated the `__iter__` and `__next__` methods.

![](/images/gen2.png "Generator Method 2")

#### <u>Method 3</u>

Generator expressions provide an additional shortcut to build generators out of expressions similar to that of list comprehensions.

![](/images/gen3.png "Generator Method 3")

---

## Notes

> Every generator is an iterator, but not vice versa.

---
