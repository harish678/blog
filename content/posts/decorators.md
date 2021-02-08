---
author: "Harish Vutukuri"
title: "Decorators"
date: "2021-01-29"
description: "Guide to creating decorators in python"
tags: ["python", "advanced"]
ShowToc: true
TocOpen: true
---

## **Introduction**

Before looking into Decorators, we need to know key points about Functions in Python.

- Functions are `Objects`. Means they can be referenced, passed as an argument, can be returned as well.

<mark><strong> Decorators dynamically alter the functionality of a function, method, or class without having to directly use subclasses or change the source code of the function being decorated </strong></mark>

## **Implementaion**

### <u>Function as a Decorator</u>

**Boilerplate Code:**

```python
import functools

def decorator(func):
    @functools.wraps(func)
    def wrapper_decorator(*args, **kwargs):
        # Do something before
        value = func(*args, **kwargs)
        # Do something after
        return value
    return wrapper_decorator
```

Now we will see an example, how much time it took for a function to execute.

There are two ways to call a decorator (_Both ways are shown in the code below_):

1. By using `@` symbol.
2. By wrapping the decorator on to a function.

![](/images/d1.png "Function as a Decorator")

### <u>Class as a Decorator</u>

Recall in the 2nd method above we have called the decorator using `test2 = timer(test2)`. If timer is a class, it needs to take func as an argument in its `__init__()` method. The logic has to be written in `__call__()` method.

**Boilerplate Code:**

```python
class Decorator:
    def __init__(self, func):
        self.func = func

    def __call__(self, *args, **kwargs):
        # Do something before
        result = self.func(*args, **kwargs)
        # Do something after
        return result
```

Now we will see the same example as above using Class Decorator

![](/images/d2.png "Class as a Decorator")

### <u>Decorators with Arguments </u>

We can pass some arguments to the Decorator as well. For that we have to enclose the whole decorator boilerplate code inside another function.

In the example we will send `num_times` to decorator and the decorator will call the wrapper function that many times.

![](/images/d3.png "Decorators with Arguments")

### <u>Multiple Decorators on a function </u>

We can call multiple decorators on a single function.

<u>**Note:**</u> Order of the decorators is IMPORTANT.

In the below example `@repeat` will be called first and `@timer` later. If we reverse the order the execution of the decorator is reversed. We are using the same `repeat` and `timer` decorators define in above examples.

![](/images/d4.png "Multiple Decorators on a function")
