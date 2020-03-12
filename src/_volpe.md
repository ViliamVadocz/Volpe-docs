# What is Volpe

Volpe is a compiled functional programming language made for fun with some fresh concepts.

## Compiled

Volpe is compiled into machine code with Python using the llvmlite library. Thanks to this
it is fast. The compiler also catches most mistakes and saves you time.

## Functional Programming

Volpe is a functional programming language. That mean that functions do not have side effects.
They cannot affect something outside of their scope. A function should always do the same thing 
given the same input. Once a function is defined, it does not change.

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

## Consistency

Volpe puts a large emphasis on being consistent in syntax and function.
If a symbol does one thing in some scenario, it should allow you to do the same thing
in another.

Take the implication `->` operator as a perfect example. It's a lazy logic operator,
where it evaluates the expression on the left, and if true, it evaluates the one on the
right to confirm that it is also true. This property also makes it perfect for controlling
flow in a program. It can serve the same function conditionals do in other languages.
The difference is that Volpe does not have a new symbol or keyword for that one specific use.

## Symbols > Keywords

Volpe does not use any keywords. This is done so developers are free to use whatever variable
names they like without having to worry about name collision. The code looks clean and is
fast to write. For example, instead of needing to type `return` you just write `:>`.
