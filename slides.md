## Boolean Algebra

---

## Learning Objectives

* Understand the basics of Boolean algebra and how they apply to computing
* Understand the common Boolean operators `AND`, `OR`, and `NOT`
* Solve Boolean expressions
* Draw truth tables and Karnaugh Maps to represent Boolean functions
* Gain familiarity with Boolean identities and the duality principle
* Use Boolean identities to simplify Boolean expressions
* Use the `NOT` operator to get the complement of a Boolean expression

---

## What is Boolean algebra?

* Everything you do on a computer is ultimately translated into 1s and 0s, otherwise known as **binary**
  * 1 is TRUE or ON
  * 0 is FALSE or OFF
* The binary digits represent the state of a physical switch on a circuitboard either being ON or OFF
* We use these two simple states to build complex logical expressions

---

## Boolean Expressions

* Combination of variables and Boolean operators
* **Boolean Product** - combining boolean variables with the `AND` operator
  * `x AND y`, often abbreviated to simply `xy`
* **Boolean Sum** - combining boolean variables with the `OR` operator
  * `x OR y`, often abbreviated to simply `x + y`
* Use the `NOT` operator to negate a boolean expression and get its **complement**
  * `NOT x`, often abbreviated to simply `x'`

---

## Boolean Expressions (Practice)

* `xy`
* `x'y`
* `x + y'`
* `xy + y'z`
* `(xy)'`

---

## Boolean Expressions (Solution)

* `xy` => `x AND y`
* `x'y` => `NOT x AND y`
* `x + y'` => `x OR NOT y`
* `xy + y'z` => `(x AND y) OR (NOT Y AND Z)`
* `(xy)'` => `NOT (X AND Y)`

---

## Boolean Functions

* A function, like any other, that takes in inputs and performs operations on those inputs to product an output
* Boolean functions take in Boolean inputs, and perform strictly Boolean operations and are composed of one or more Boolean expressions.
  * Example: `F(x, y, z) => (x + y) + y'z`
* Boolean functions can be represented by **truth tables** that represent the output of every possible combination of inputs
  * Will have `2^n` rows where n is the number of inputs

---

## Truth Table (2 inputs)

![truth-table-2-inputs](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/truth-table-2-inputs.png?token=AHULCLDWHPFB46VLTGYG6BK6VILC4)

--- 

## Truth Table (3 inputs)

![truth-table-3-inputs](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/truth-table-3-inputs.png?token=AHULCLBG6663WKXXYJVTL2C6VILH4)

---

## Boolean Identities

* Identities or laws that apply to Boolean expressions
* **Duality Principle** - each law has both an `AND` form and an `OR` form

![boolean-identities](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/boolean-identities.png?token=AHULCLC3VUA5GCWSNAJGPXS6VIK4Q)

---

## Simplifying Boolean Expressions

* Can simplify Boolean expressions just like we can simplify algebraic expressions. 
* Use the Boolean identities/laws to achieve this.

---

## Simplifying Boolean Expressions (example)

* Let's simplify the following Boolean expression: 

`F(x, y) = (xy)'(x' + y)(y' + y)`

![simplifying-boolean-expressions](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/simplifying-boolean-expressions.png?token=AHULCLAM5AMZZ2WJUDFB44K6VILBS)

---

## Function Representations

* Many Boolean expressions are **logically equivalent** - boil down to the same simplified expression and can be represented by the same truth table
* To eliminate confusion, standardized forms are used to represent Boolean functions
  * **sum-of-products-form (more common)** - Collection of `AND`ed variables that are `OR`ed together.
    * Example: `xy + yz' + xyz`
  * **product-of-sums-form** - Collection of `OR`ed variables that are `AND`ed together.
    * Example: `(x + y)(y' + z)(x' + z')`

## Karnaugh Maps (Kmaps)

* Graphical way of representing Boolean functions. Row & Column headers correspond to input values, and the cells at their cross section represent the output for that set of inputs.
* **Minterm** - A product term that contains all Boolean variables in the function exactly once, either complemented or not complemented. 
  * There are `(2^n)` minterms for a Boolean function, where `n` is the number of inputs
* Can simplify Boolean expressions using Kmaps by organizing outputs into _groups_.

---

## Kmap (2 inputs)

### `F(x, y) = xy`

![kmap-2-inputs](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/kmap-2-inputs.png?token=AHULCLEE2PCCVDQ275CRGRS6VIK6U)

---

## Kmap (3 inputs)

### `F(x, y, z) = x'y'z + x'yz + xy'z + xyz`

![kmap-3-inputs](https://raw.githubusercontent.com/appacademy/worldwide-lecture-notes/online-learning-boolean-algebra/online-learning-challenges/boolean-algebra/assets/kmap-3-inputs.png?token=AHULCLCMMEXQKAUMNPQD2WS6VIK76)

---

## Thank You!