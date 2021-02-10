---
author: "Harish Vutukuri"
title: "Context Manager"
date: "2020-01-27"
description: "Guide to creating context managers in python"
tags: ["python", "advanced"]
ShowToc: true
TocOpen: true
---

## **Introduction**

Context managers allow you to allocate and release resources precisely when you want to. The most widely used example of context managers is the `with` statement.

Suppose you have two related operations which you’d like to execute as a pair, with a block of code in between. Context managers allow you to do specifically that.

## **Implementaion**

In the below example we will implement a program to open the file and read its contents using two methods.

### <u>Method 1</u>

An object can be a Context Manager if we add `__enter__` and `__exit__` methods.

![](/images/cm1.png "Context Manager Method 1")

### <u>Method 2</u>

Can create a Context Manager using `@contextmanager` decorator [^1].

The function being decorated must return a `generator-iterator` when called.

![](/images/cm2.png "Context Manager Method 2")

## FootNotes

[^1]: https://docs.python.org/3/library/contextlib.html#contextlib.contextmanager
