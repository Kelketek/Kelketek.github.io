---
title: "R-style Piping in Python"
date: 2024-10-08
categories: [Writing, Blogs]
tags: [writing, technical writing, blogs, python, rlang]
description: "A guide to implementing Rlang-style piping in Python."
image:
  path: /assets/img/posts/piping.jpg
  alt: A photograph of a several pipes in parallel, each with a wheel-turned valve.
---

## A Pipe Dream

Recently, my wife had the good fortune of getting into grad school. In preparation for the data analysis she would be performing, she wanted to learn [R](https://www.r-project.org/). She asked for my help learning. I didn't know R, but knew several other languages and offered to take an online course with her to figure out the basics. In the process I learned of a language feature that I found myself missing in Python.

That feature is the piping operator.

## What is Piping?

Let's make a contrived example with fictional functions. Anyone who has worked in a functional style is familiar with how one can end up with nested calls to modify data. You can easily end up with something like:

```python
first(randomize(append_items(do_something(array), new_entries)))
```

This kind of nesting can be difficult to read, as it requires looking for the 'middle' of the operation and then stepping outward to find the result. This can take some getting used to, and sometimes programmers may use intermediary values to make it more clear what's happening:

```python
something_done = do_something(array)
appended_version = append_items(array, new_entries)
randomized = randomize(appended_version)
first_entry = first(randomized)
```

This removes the need to start inward and step outward, and instead lets the operations be read from top to bottom. However, this can get quite verbose and requires declaring multiple additional variables. Is there a better way?

Introducing the piping operator. Piping allows you to write:
```r
array %>% do_something()
```

...Which is equivalent to:

```python
do_something(array)
```

When piping to a function, the interpreter takes the output of the statement on the left side of `%>%` (the pipe operator) and shims it in as an implied first argument to the function on the right side of the operator. That means we can now do:

```r
array %>% do_something() %>% append_items(new_entries) %>% randomize() %>% first()
```

Now we read the operations from left to right, each step making it clear how we modify the data for each step.

## Adding Piping to Python

Python doesn't have `%>%`. It does, however, have a lesser used operator for bitwise OR, `|`. The symbol `|` is called a 'pipe' because of its appearance and its use for 'piping' in [shell scripting](https://www.howtogeek.com/438882/how-to-use-pipes-on-linux/). The shell scripting version is a bit different, but similar in concept.

It would be cool if we could use this operator to make piping in Python. However, we can't just do:

```python
array | do_something()
```

...as `do_something()` will be evaluated immediately, and will doubtless raise an exception since it's missing its argument! Not to mention, this doesn't magically change the semantics of `|` even if `do_something()` were interpreted as some sort of pre-bound function.

Is there a way we can change the semantics of `|`, and make piping-compatible functions?

### Operator Overloading

You may be already familiar with the concept of operator overloading. But in case you are not, some languages, such as Python or C++, allow you to add operator-specific semantics to classes. This allows you to write more expressive code. For instance, the Python Pathlib `Path` class allows you to construct operating system paths using a `/` like so:

```python
from pathlib import Path

# Outputs PosixPath('/home/fox/bin') on a Linux system.
Path('/') / 'home' / 'fox' / 'bin'
```

To do this, it implements a specific method, `__truediv__`, which can accept a string as an argument, and return a new `Path` object. All (or nearly all) operators have relevant 'dunder methods' (so called because of the double underscores that surround their names) to implement the overloading behavior. The full list of these methods can be found in the [Python data model reference](https://docs.python.org/3/reference/datamodel.html).

To our great fortune, there's a dunder method for handling our `|` operator, `__or__`. Except, we don't want `__or__`. We want `__ror__`! What's the difference? The `__or__` method is activated when we are on the left side of the `|`, but we'll be using our special functions on the right side.

Let's make a pipe-compatible class. We'll hand it a function, and that function will be called with the left-hand of the operator as its first argument:

```python
class PipeWrapped:
    def __init__(self, func):
        self.func = func

    def __ror__(self, other):
        return self.func(other)
```

Let's give it a spin!

```python
def inner_reverse_iterable(iterable):
    # The 'reversed' built-in returns an iterable,
    # so we'll need to convert it to a list.
    return reversed(iterable)

def inner_tupilify(iterable):
    # ...which we do here.
    return tuple(iterable)

reverse_iterable = PipeWrapped(reverse_iterable)
tupilify = PipeWrapped(inner_listify)

# Returns (4, 3, 2, 1)
(1, 2, 3, 4) | reverse_iterable | tupilify
```

Great! We can now pipe things to functions. Actually, this whole 'making intermediary functions' thing is kind of annoying. Let's create a [decorator function](https://www.geeksforgeeks.org/decorators-in-python/) to make this cleaner:

```python
def pipeable(func):
    return PipeWrapped(func)

@pipeable
def reverse_iterable(iterable):
    return reversed(iterable)

@pipeable
def tupilfy(iterable):
    return tuple(iterable)

# Returns (4, 3, 2, 1)
(1, 2, 3, 4) | reverse_iterable | tupilify
```

Great! That looks nicer. But we're still missing a couple of things. For one, we can no longer call these functions directly if we need to. We *always* have to pipe to them. That might be fine, but it might be annoying if we find ourselves using this function in different contexts.

And the second, more problematic issue, is that these functions cannot have pre-bound arguments. Our promise of R-parity is not yet met!

To get there, we need one more class, and one more special dunder method!

```python
class Pipe:
    def __init__(self, func):
        self.func
    def __call__(self, *args, **kwargs):
        # The __call__ dunder method allows you to call an object
        # like a function!
        return PipeWrapped(self.func, *args, **kwargs)
```

...and we need to update our PipeWrapped class and pipeable decorators like so:

```python
class PipeWrapped:
  def __init__(self, func, *args, **kwargs):
    self.func = func
    self.args = args
    self.kwargs = kwargs

  def __ror__(self, other):
    return self.func(other, *self.args, **self.kwargs)

def pipeable(func):
    return Pipe(func)
```

Now, when we call a `@pipeable`-decorated function, it returns a factory function that pre-binds the original function with whatever arguments and keyword arguments you like. So:

```python
@pipeable
def append(tup, *args):
    # Return a new tuple with the elements added to the end.
    return tup + args

# Returns (1, 2, 3, 4, 5, 6)
(1, 2, 3) | append(4, 5, 6)

# Returns ('A', 'B', 'C', 'D', 'E', 'F')
append.func(('A', 'B', 'C'), 'D', 'E', 'F')
```

Tada! Now we can define any number of pipeable functions we want, and use them just like in R-lang. The only difference is we need to use the `.func` property to call these functions when we need to use them directly.

[Here's a gist with the full code.](https://gist.github.com/Kelketek/4594314a17c17ed978df6272e0534c1f)

If you used this to make something (or if you're looking for someone to join your team), [please email me](fox@vulpinity.com)! I'd love to hear from you.
