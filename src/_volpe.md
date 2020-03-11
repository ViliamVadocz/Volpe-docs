# What is Volpe

Volpe is a programming language made for fun with some fresh concepts.

## Consistency

Volpe puts a large emphasis on being consistent.
Everything in the language should behave like you expect it to.

*Why introduce new syntax when there is already something else that makes more sense?*

## Functional Programming

Volpe is a functional programming language. That mean that functions do not have side effects.
A function should always do the same thing given the same input. Once a function is defined,
it does not change.

To give an example, take this Python code:

```python
n = 2

def f(x):
    x + n

assert f(1) == 3  # true

n = 5

assert f(1) == 3  # error!
```

The function `f` changed when an outside variable `n` changed. The same input `1` resulted in a
different output. This can lead to hard-to-catch problems and is something Volpe tries to avoid.

In Volpe:

```volpe
n = 2

f = x => x + n

f(1) == 3  # true

n = 5

f(1) == 3  # still true
```

## Symbols > Keywords

Volpe does not use any keywords. This is done so developers are free to use whatever variable
names they like, without having to worry about name collision. The code looks cleaner and is
fast to write, since instead of typing `return` you can just write `:>`.
