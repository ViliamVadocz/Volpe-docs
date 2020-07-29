# Symbols and their Meaning

- *lhs* = left hand side
- *rhs* = right hand side

Here is a list of all the symbols used by Volpe and their meaning:

## Basic

- `:=` assignment
  - value of *rhs* is assigned to symbol on *lhs*
  - tuple deconstruction may apply

- `{}` code block; object
  - as code block, whatever is inside gets executed once
  - objects are key value pairs, but the key can be left out
    - `{value1, key: value2, value3}`

- `()` function arguments; function call; mathematical precedence
  - if preceded by a symbol, calls the function
  - if followed by a code block, defines a function
  - otherwise controls order of operations

- `[]` array
  - elements of same type separated by commas

- `;` statement separator
  - used to separate statements on the same line

- `,` element separator
  - required after every element except last
  - in objects with only one element it is required to
    place a comma to differentiate it from a block

## Logic / Flow control

Defined for booleans (true or false expressions).

- `->` implication; if-then
  - lazy implication, evaluates *lhs*, if true, evaluates *rhs*
  - if not the last expression in a block, and *lhs* is true, returns *rhs*

- `&&` logical and
  - lazy and, only true if both sides are true

- `||` logical or
  - lazy or, true if either side is true

- `!` logical not
  - logical negation
  - false if true, true if false

### Truth Tables

| `A` | `B` | `A -> B` | `A && B` | <code>A &#124;&#124; B</code> | `!A` |
|:---:|:---:|:--------:|:--------:|:-----------------------------:|:----:|
|  T  |  T  |    T     |    T     |               T               |  F   |
|  T  |  F  |    F     |    F     |               T               |  F   |
|  F  |  T  |    T     |    F     |               T               |  T   |
|  F  |  F  |    T     |    F     |               F               |  T   |

## Comparison

Defined only for integers, floating point numbers, and characters.

- `=` equality
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

- `%` modulo
  - *lhs* modulo *rhs*
  - the remainder after division of *lhs* by *rhs*

- `+=` add assign
  - add *rhs* to the value of *lhs* and assign to *lhs*

- `-=` subtract assign
  - subtract *rhs* from the value of *lhs* and assign to *lhs*

- `*=` multiply assign
  - multiply by *rhs* and assign to *lhs*

- `/=` divide assign
  - divide by *rhs* and assign to *lhs*

- `%=` modulo assign
  - modulo by *rhs* and assign to *lhs*

## Comments

- `#` single-line comment
  - can be placed anywhere
  - the comment continues until the end of the line

- `#! !#` multiline comment
  - `#!` opening signature
  - `!#` closing signature
  - everything between the opening and closing signature is ignored

## Special

- `@` recursion
  - symbol referring to the function we are in
  - example: `@(args)`

- `~` float conversion
  - float on *rhs* gets converted to integer (round down)

- `.` int conversion
  - int on *lhs* + decimal on *rhs* become new float
  - `10.5`
  - `{a := 10; a.5}`
