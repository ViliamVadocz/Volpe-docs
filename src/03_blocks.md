# Blocks

A block is a contained chunk of code with its own scope. Each block has a value
and type based on its return. A block receives no input, but it can capture
variables from outside scopes.

```volpe
a := {
    x := 10
    y := 20
    z := 2 * x + y
    z > 2 * (x + y)
}
```

```volpe
x := -15
abs_x := {
    x < 0 -> -x
    x
}
```

```volpe
a := 10
b := {
    a := a + 10
    a
}
{a, b}  # {10, 20}
```

## Return

Returning in volpe is always implicit. This is possible because of a few rules about returning:

- A block must have an unconditional return to make sure it returns in all cases
- Dead code (code after an unconditional return) is not allowed

But this is not the whole story. We need to look at the *implication* operator `->`.
It is a lazy operator between two boolean values. This is weird because `-x` is not a bool.
What is really happening here is we are *returning* `-x` and that is a boolean type.

*note to self:* improve this explanation because it sucks
