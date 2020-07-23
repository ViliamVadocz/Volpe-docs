# Types

All the core Volpe types are on the stack and have a known size during compilation.

## Simple Types

### `bool`

- 1 byte
- True or False
- used with logic operators

```volpe
true := 1 > 0
false := !true
```

### `char`

- 1 byte
- ascii character
- can be put into arrays to form a string

```volpe
a := 'a'
b := 'b'
```

### `int64`

- 8 bytes
- signed integer
- a whole number

```volpe
x := 42
y := 1337
```

### `flt64`

- 8 bytes
- floating point number
- rational numbers, both large and small
- susceptible to precision errors

```volpe
pi := 3.141
e := 2.718
```

## Aggregate Types

### `array<T>`

- all elements have the same type `T`
- size of array must be known at compile time

```volpe
arr := [1, 2, 3]
str := "hello"
```

### `object`

- elements can have different types
- can be deconstructed

```volpe
stuff := {1, 2.0, 'w'}  # {_0: 1, _1: 2.0, _2: 'w'} under the hood
person := {name: "John", age: 24}
```

### `closure`

- every closure is a unique type based on its "origin"
- the size of the closure on the stack is just it's captured environment

```volpe
# f and g have different types
f := (x) {x + 1}
g := (x) {x + 1}

# a and b have the same type
# because they both originate in make_add_1
make_add_1 := () { (x) {x + 1} }
a := make_add_1()
b := make_add_1()
```
