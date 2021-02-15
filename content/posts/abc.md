---
author: "Harish Vutukuri"
title: "Abstraction"
date: "2021-02-15"
description: "Abstraction in python using abc module"
tags: ["python", "advanced"]
ShowToc: true
TocOpen: true
---

## **Introduction**

Abstraction is the process of hiding the real implementation of an application from the user and emphasizing only on usage of it.

> Abstraction in Python is achieved by using `Abstract Base Classes (ABCs)` [^1]. The `abc` module in Python library provides the infrastructure for defining custom abstract base classes.

`Abstract classes` are classes that contain one or more abstract methods and generally provides incomplete functionality. An abstract method is a method that is declared, but contains no implementation. Abstract classes cannot be instantiated, and require subclasses to provide implementations for the abstract methods.

There are many built-in ABCs in Python. ABCs for Data structures like Iterator, Generator, Set, Mapping etc. are defined in `collections.abc` module.

---

## **Implementation**

The `abc` module defines `ABCMeta` class which is a metaclass [^2] (or) `ABC` helper class for defining abstract base class and `@abstractmethod` decorator [^3] for defining abstract methods.

Let's create a Abstract Class `Shape` for Rectangle and Square which implements the `area()` abstract method.

---

### **Abstraction using `ABCMeta`**

![](/images/abc.png "ABCMeta")

> **NOTE**: All abstract methods defined in Abstaction Class has to be implemented by subclass or else `TypeError` exception is raised.

---

### **Abstraction using `ABC`**

`ABC` helper class already has `ABCMeta` as its metaclass. Simply replace the `metaclass=ABCMeta` with `ABC` from the above implementation.

![](/images/abc2.png "ABC")

## FootNotes

[^1]: https://docs.python.org/3/library/abc.html
[^2]: More about Meta Classes: http://harish678.github.io/posts/metaclass/
[^3]: More about Decorators: http://harish678.github.io/posts/decorators/
