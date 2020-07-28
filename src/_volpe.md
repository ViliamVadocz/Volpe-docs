# What is Volpe

Volpe is an [open-source](https://github.com/LHolten/Volpe) compiled
strongly-typed functional programming language without any keywords.

## Compiled

Volpe is compiled into [LLVM IR](https://en.wikipedia.org/wiki/LLVM) using the
[llvmlite](https://llvmlite.readthedocs.io/en/latest/) library for Python. It
benefits from LLVM optimizations and is quite fast.

## Strongly Typed

Every variable has a defined type known at compile time, yet there is no need
for type hints. We use context clues as well as
[unification](https://pypi.org/project/unification/) to figure out the correct
type. We also support generics by generating new closures if the argument types
do not match an existing version of the closure.

## Functional Programming

Volpe is a functional programming language. That means functions / closures do
not have side-effects (except for IO operations like printing), i.e. they cannot
affect something outside of their scope. They should always do the same thing
given the same input. Once a function / closure is defined, it does not change.

To give an example, take this Python code:

```python
n = 2
f = lambda x: x + n
f(1)  # returns 3
n = 5
f(1)  # returns 6 <- DIFFERENT
```

The closure `f` changed when an outside variable `n` changed. The same input `1`
resulted in a different output. This can lead to hard-to-catch problems and is
something Volpe avoids.

In Volpe:

```volpe
n := 2
f := (x) {x + n}
f(1)  # returns 3
n := 5
f(1)  # returns 3 <- SAME
```

## Symbols > Keywords

Volpe does not use any keywords. This is done so developers are free to use
whatever variable names they like without having to worry about name collision.
This is somewhat of a double-edged sword because it makes the code harder to
read for people not familiar with the language. Fortunately, with good variable
names (you can use anything!) you can lessen the impact of this downside.
