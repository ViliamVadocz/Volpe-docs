# Symbols and their Meaning

- *lhs* = left hand side
- *rhs* = right hand side

Here is a list of all the symbols used by Volpe and their meaning:

## Basic

- `=` assignment
  - value of *rhs* is assigned to symbol on *lhs*
  - tuple deconstruction may apply

- `:>` return
  - return value on *rhs* out of current scope
  - does not mean it returns from the function, just one scope up

- `=>` function
  - *lhs* defines arguments
  - *rhs* defines what to do with them

- `{}` code block; scope
  - as code block, whatever is inside gets executed once
  - defines scope, often used in flow control
  - found after `=>` in functions if they are not using *shorthand notation*

- `()` function call; mathematical precedence
  - if preceded by a symbol, calls the function
  - otherwise controls order of operations

- `,` element separator in tuples and function arguments
  - required after every element except last

## Logic / Flow control

Defined for booleans (true or false expressions).

- `->` implication
  - lazy implication, evaluates *lhs*, if true, evaluates *rhs*

- `&&` logical and
  - lazy and, only true if both sides are true

- `||` logical or
  - lazy or, true if either side is true

- `!` logical not
  - logical negation
  - false if true, true if false

- `;` lowest priority and
  - like logical and, except has much lower priority
  - used to separate expressions on the same line
  - if either side is false, the line will evaluate to false, triggering an assertion error

### Truth Tables

```text
A  B | A -> B | A && B | A || B | !A | A; B
-----+--------+--------+--------+----+------
T  T |   T    |   T    |   T    | F  |  T
T  F |   F    |   F    |   T    | F  |  F
F  T |   T    |   F    |   T    | T  |  F
F  F |   T    |   F    |   T    | T  |  F
```

## Comparison

Defined only for integers and floating point numbers.

- `==` equality
  - true if both sides have the same value

- `!=` inequality
  - false if both sides have the same value

- `>` greater than
  - checks that *lhs* is greater than *rhs*

- `<` less than
  - checks that *lhs* is less than *rhs*

- `>=` greater or equal
  - checks that *lhs* is greater or equal to *rhs*

- `<=` less or equal
  - checks that *lhs* is greater or equal to *rhs*

## Mathematics

Only defined for integers and floating point numbers.

- `+` addition
  - add *rhs* to *lhs*

- `-` subtract; negation
  - subtract *rhs* from *lhs*
  - when used as unary, negate *rhs*

- `*` multiply
  - multiply *rhs* and *lhs*

- `/` division
  - divide *lhs* by *rhs*

- `**` power (not implemented)
  - take *lhs* to the *rhs* power

- `+=` add assign (not implemented)
  - add *rhs* to the value of *lhs* and assign to *lhs*

- `-=` subtract assign (not implemented)
  - subtract *rhs* from the value of *lhs* and assign to *lhs*

- `/=` divide assign (not implemented)
  - divide by *rhs* and assign to *lhs*

- `*=` multiply assign (not implemented)
  - multiply by *rhs* and assign to *lhs*

## Iterables

- `[]` tuple
  - create tuple
  - use `,` to separate elements
  - tuples can be nested

- `..` range (not implemented)
  - make an integer iterator spanning range from *lhs* to *rhs*

- `::` map (not implemented)
  - map a function on *rhs* to every element of iterable on *lhs*

- `:():` map with carried variables
  - variables in the brackets are carried by the function on *rhs* and stay in scope
  - no brackets are needed when there is only one or no variable

## Comments

- `#` single-line comment
  - can be placed anywhere
  - the comment continues until the end of the line

- `#! !#` multiline comment
  - `#!` opening signature
  - `!#` closing signature
  - everything between the opening and closing signature is ignored.

## Special

- `@` recursion
  - symbol referring to the function we are in
  - example: `@(args)`

- `~` conversion
  - integer on *rhs* gets converted to floating point number

- `${}` nullary function (not implemented)
  - shorthand for function with no arguments
  - same as `() => {}`
  - the `$` differentiates it from code blocks
