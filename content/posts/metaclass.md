---
author: "Harish Vutukuri"
title: "Meta Classes"
date: "2021-02-11"
description: "Meta Classes in python"
tags: ["python", "advanced"]
ShowToc: true
TocOpen: true
---

## **Introduction**

A Metaclass means the class of a class. In Python Classes are objects, which are instances of some Class.

As can see below every Class in Python are instance of a class **`type`**.

```python
class Example:
    pass

>>> type(Example)
 <class 'type'>
```

> `type` is a MetaClass in Python which is responsible for classes creation.

---

## **Dynamic Class creation using type()**

1. When `type()` is called with one argument, it returns the argument type.

2. When `type()` is called with 3 arguments, a class is created.

   - Class name
   - Tuple having base classes inherited by class
   - Class dictionary populated with class methods and variables

```python
# creating a base class
class Base:
    def myfunc(self):
        print("This is from Base!")

# Normal Way
class Test(Base):
    x = 1

# Dynamic Way using type()
Test = type('Test', (Base, ), dict(x=1))
```

---

## **Creating Custom Metaclass**

Let's consider an example:

```python
class Foo:
    pass

>>> f = Foo()
```

The expression `Foo()` creates a new instance of class Foo and the following occurs:

- The `__call__` method of Foo’s parent class is called. Since Foo is a standard new-style class, its parent class is the `type` metaclass, so type’s `__call__` method is invoked.

- That `__call__` method in turn invokes the following:
  - `__new__`
  - `__init__`

To create a Custom MetaClass, the class has to **inherit `type` and overide `__new__`, `__init__` methods**.

![](/images/mc.png "MetaClass")

---

## **Notes**

1. Metaclasses can be used when the classes needs to change dynamically.
2. Metaclasses can be used when a decorator needs to be applied to every function in a class.
