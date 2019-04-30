# Haskell Book Chapter 1

## 2.3

- Normal form: No more evaluation steps can be taken for a certain expression.
- Reducible expressions are also called *redexes*.

## Functions

- functions are a specific type of expression.
- Same as in lambda calculus, all functions in Haskell can only take one argument and return one result.
- Evaluationg an expression === Reducing the terms until the expression reaches its simplest form.
- Non-strict evaluation === Lazy evaluation --> defers evaluation of terms until they're forced by other terms referring to them.
- Values are expression, but cannot be reduced further -> Values are a terminal point of reduction.
- Haskell doesn't evaluate everything to normal form by default -> only evaluates to weak head normal form by default -> it means not everything will get reduced to its irreducible form immediately.

## 2.9

- function can be used as *infix style* wrapped with backtick (``).
- infix operator can be used as prefix function with parenthesis
- `$` sign will allow everything to the right of it to be evaluated first and can be used to delay function application.
- **sectioniong** === partially applied functions
