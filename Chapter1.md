# Haskell Book Chapter 1

## 1.1

- **Calculus** is one process for formalizing a method and **lambda calculus** formalizes the concept of effective computability, like turning machines.
- Haskell is a lambda calculus.

## 1.2

- The essence of functional programming it that programs are a combination of _expressions_.
- Functional programming languages are all based on the lambda calculus.
- when we say “_pure_” functional language, it means it can be translatable into lambda expression.
- Referential transparency (purity) : the same function, given the same value to evaluate, will always return the same result.
- Why abstraction is good? allows to write more concise programs by factoring common, repeated structures into more generic code that can be reused.

## 1.4 The structure of lambda expressions

- Three basic components (_lambda terms_) of lambda calculus
  - expressions: superset of all below.
  - variables
  - abstractions: is a function, consisting of _head_ and _body_.
    -> `λx.x`. The reason why it has no name (function name) means it can be used to solve different concrete problems by appling general function (lambda calculus) to different values.
- _application_ - the act of applying a lambda function to an argument.
- _Alpha equivalence_ - _x_ isn't semantically meaningful, so `λx.x === λd.d === λz.z`

## 1.5 Beta reduction

- **My Definition**: When applying a function to an argument, if you can eliminate the head of the abstraction (since its only purpose is to bind a variable with value), this process is called **beta reduction**
- **Formal Definition**:
  > Beta reduction is this process of applying a lambda term to an argument, replacing the bound variables with the value of the argu- ment, and eliminating the head. Eliminating the head tells you the function has been applied.
- `λx.x` is the identity function - accept a single argument and return that same argument.
- Steps to apply identity function to another lambda abstraction:

  1. (𝜆𝑥.𝑥)(𝜆𝑦.𝑦)
  2. [𝑥 ∶= (𝜆𝑦.𝑦)] # indicate that `z` will be substituted for all occurences of x (here means `λy.y`).
  3. 𝜆𝑦.𝑦

- Applications in lambda calculus are _left associative_, which means:
  ```
  (𝜆𝑥.𝑥)(𝜆𝑦.𝑦)𝑧 === ((𝜆𝑥.𝑥)(𝜆𝑦.𝑦))𝑧
  ```
- Free variables - body expression has variables that are not named in the head.

## 1.6

- Each lambda can only bind one parameter and can only accept one argument.
- _currying_ - when fucntions have multiple arguments (multiple heads), apply one argument and eliminate leftmost head one by one.
  ```
  𝜆𝑥𝑦.𝑥𝑦
  ```
  is a convenient shorthand for
  ```
  𝜆𝑥.(𝜆𝑦.𝑥𝑦)
  ```
- The lambda calculus is a process or method, like a game with a few simple rules for transforming lambdas, but no specific meaning. -> just a math tool🤔
- Beta normal form is when you cannot beta reduce (apply lambdas to arguments) the terms any further. === **a fully evaluated expression** === **a fully executed program**

## 1.8 Combinators

- is a lambda term with no free variables.
- serve only to combine the arguments they are given.
- combinators: `𝜆𝑥.𝑥`, `𝜆𝑥𝑦.𝑥`
- not combinators: `𝜆𝑦.𝑥`, `𝜆𝑥.𝑥𝑧`

## 1.9 Divergence

- cannot reduce to normal form because reduction process never terminates.
- e.g `(𝜆𝑥.𝑥𝑥)(𝜆𝑥.𝑥𝑥)` (_omega_)
- This matters in programming because terms that diverge are terms that don’t produce an answer or meaningful result.

## Summary

- Haskell is a _typed_ lambda calculus.
- Lambda calculus is a formal system for expressing programs in terms of abstraction and application.
