## Boolean Algebra

* Welcome everyone. Today's topic is going to be all about Boolean algebra, the basis of computing.

## Learning Objectives

* Walk through the learning objectives of the day

## What is Boolean algebra?

* At the end of the day everything we do on a computer can be boiled down to 0s and 1s (otherwise known as _binary_) - at the physical layer this translates to switches on a circuit board that are either in an ON state or an OFF state. You can think of 1 as being ON or TRUE, and 0 as being OFF or FALSE. Understanding the basics of Boolean algebra and how we can use these two simple states to build complex logical expressions, will provide a great foundation as you venture into software engineering.

## Boolean Expressions

* Walk them through the three boolean operators listed on this slide. Using the `AND` operator creates a **Boolean product**, and using the `OR` operator creates a **Boolean sum**. 
* No fancy term for using `NOT` operator but just let them know to think of it as a negating operator, that returns the opposite of what the expression would otherwise return. Adding the `NOT` operator to an expression creates that expression's **complement**.

## Boolean Expressions (Practice)

* Walk through each of the examples asking someone from the class to read the expressions using the names of the Boolean operators (`AND`, `OR`, and `NOT`)
* Confirm or correct their answers verbally - for the more complex expressions with parentheses and sub-expressions try to adjust your vocal inflection/speed to make clear which parts are grouped together. It will be made clear on the next slide.

## Boolean Expressions (Solution)

* Answer key
  * `xy` => `x AND y`
  * `x'y` => `NOT x AND y`
  * `x + y'` => `x OR NOT y`
  * `xy + y'z` => `(x AND y) OR (NOT Y AND Z)`
  * `(xy)'` => `NOT (X AND Y)`
* Let them know with complex operations that the order of operations they're used to in math (PEMDAS/BODMAS) still applies - you solve what's in parentheses first and also prioritize products (the `AND`s) over sums (the `OR`s). For the second to last example break down that the two Boolean expressions on either side of the plus sign are first evaluated, and their results are then what goes into the `OR` evaluation.
* For the last example point out that `X AND Y` is evaluated first since it is in parenthesis, and then that is negated by the `NOT` outside of the parentheses.

## Boolean Functions

* Explain that a boolean function is just like any other function, the only difference is that its inputs are Boolean values, and the function performs exclusively Boolean operations.
* Walk through the example Boolean function - it takes in 3 inputs (x, y, and z) and performs a variety of Boolean operations on the inputs. Namely, it does the following:
  1. `x OR y`
  2. `NOT Y AND Z`
  3. `<result_of_1> OR <result_of_2>`
* Can represent a Boolean function with truth tables. Each row of a truth table represents a different combination of inputs and the output that it generates for the given Boolean function.
* There will be `2^n` rows in the truth table where `n` is the number of inputs, since each input has 2 possible values.
* Let's look at some examples

## Truth Table (2 inputs)

* The function represented here is `xy` or `x AND y` (as noted in the output column). Walk them through reading the table and how each row represents a different combination of inputs. Since there are 2 variables there are 4 total rows. Only 1 row has an output of 1, as both x & y must be TRUE for the entire expression to be TRUE.
* Take any questions that students may have on interpreting the truth table.

## Truth Table (3 inputs)

* The function represented here is `x + y'z` or `x OR (NOT y AND z)`
* Point out that the first 3 columns are the values of the inputs, and the last column is the output. The 2 columns in between are not technically part of the truth table but rather us solving intermediary steps to break down the problem into its sub-expressions, making it easier to reason about the problem.
* Take any questions that students may have on interpreting the truth table.

## Boolean Identities

* Explain that boolean identities are laws surrounding boolean operations.
* Explain the duality principle in that each of these laws can be expressed both in terms of an `AND` operation as well as an `OR` operation
* Each law explained
  * **Identity Law** - `1 AND x` is the same as simply `x`. `O OR x` is also the same as simply `x`.
  * **Null Law** - `O AND x` will always be `0`. `1 OR x` will always be `1`.
  * **Idempotent Law** - `x AND x` will always be `x`. `x OR x` will always be `x`.
  * **Inverse Law** - `x AND NOT x` will always be `0`. `x OR NOT x` will always be `1`.
  * **Commutative Law** - `x AND y` is the same as `y AND x`. `x OR y` is the same as `y OR x`. Essentially saying the order does not matter.
  * **Associative Law** - `(x AND y) AND z` is the same as `x AND (y AND z)`. `(x OR y) OR z` is the same as `x OR (y OR z)`. How you group the expressions does not matter.
  * **Distributive Law** - `x OR (y AND z)` is the same as `(x OR y) AND (x OR z)`. `x AND (y OR z)` is the same as `(x AND y) OR (x AND z)`
  * **Absorption Law** - `x AND (x OR y)` is simply `x`. `x OR (x AND y)` is simply `x`.
  * **DeMorgan's Law** - `NOT (x AND y)` is the same as `NOT x OR NOT y`. `NOT (x OR y)` is the same as `NOT x AND NOT y`.
    * Common mistake - `NOT (x AND y)` is NOT the same as `NOT x AND NOT y`. The latter is TRUE if _both_ x & y are FALSE, whereas the former is TRUE if _either_ x & y are FALSE 
  * **Double Component Law** - `NOT NOT x` is the same as `x`. `AND` & `OR` form are the same here since neither operation is involved (only uses `NOT`). 
* Worth noting that the commutative, associative, and distributive laws are similar to the ones that they likely learned when they learned algebra in middle/high school. It is the same principle here again just with Boolean variables/operators instead of arithmetic ones.

## Simplifying Boolean Expressions

* Explain that just like we can simplify algebraic expressions, we can simplify Boolean expressions.
* We can apply the Boolean identities we just learned to achieve this.

## Simplifying Boolean Expressions (Example)

* Walk through the example of simplifying a Boolean expression and talk about how each law simplifies it one step further. Use the reference above on each law to guide your explanation.

## Function Representations

* Building off of the last slide discuss how there are many Boolean expressions that on their face may look different, but when boiled down and simplified are actually the same expression.
* Discuss how as Boolean expressions get long they can become confusing and difficult to make sense of. This is why there are standardized patterns of _representing_ the Boolean expressions. Both are listed on the slides, but the **sum-of-products-form** is more common. This is a bunch of `AND`ed variables that are then strung together with `OR`s. You can first solve each `AND` expression, and then use their outputs to solve the `OR` portion.

## Karnaugh Maps (Kmaps)

* Explain that Kmaps are a graphical way of representing Boolean functions, and that they are different than truth tables.
* Whereas truth tables have a row for every combination of inputs, Kmaps have rows and columns that represent the values of different inputs and the cells at their cross section represent the output for that set of inputs. Can make an analogy to a Punnett Square that some people might remember from biology class, as it is rather similar (at least when looking at a simple 2-input case).
* We can use Kmaps to simplify expressions by creating _groups_ within the Kmap.
* The are various rules for creating these groups, and we won't go into detail on them in this lecture but you can find them in the Karnaugh Maps reading on AAOpen.
* We'll focus on being able to read a Kmap - let's look at an example.

## Kmap (2 inputs)

* Explain that this Kmap maps the Boolean function `x AND y`. The first column contains the possible values of `x` and the first row contains the possible values of `y`.
* We can look at the cell where the input values of x & y intersect to see what output that gives us. In this case we see that all combinations will give `0` except when both `x` and `y` are 1. This makes sense since this is the `AND` operation - both must be 1 or TRUE for the whole expression to be 1 or TRUE.
* Contrast the structure of the Kmap with the truth table from earlier (feel free to go back a few slides).

## Kmap (3 inputs)

* Slightly more advanced example. The function here is pretty complex (though can actually be simplified to just `z`!). Focus on walking through how the Kmap is set up and explaining that again the first column represents the input values for `x`, but the first row actually represents the input values of each possible combination of `y` and `z`! That's why there's 4 of them. In total there are 8 different possible combinations of the input values since we are dealing with 3 variables (`2 ^ 3 = 8`).
* Answer any questions that students have on interpereting this Kmap.

## Thank You!

* That's all, you're done! Let them know that they can check out the last 2 readings in this module on AAOpen to get further references/resources to help them understand Boolean algebra.