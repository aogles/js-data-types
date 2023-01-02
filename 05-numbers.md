## JavaScript Statements vs Expressions

JavaScript distinguishes expressions and statements. A statement is an instruction, an action that doesn't have a return value. Conditions with if, loops with while and for — those are all statements, because they just perform actions and control actions, but don't become values.

An expression is any combination of values and functions that are combined and interpreted by the compiler to create a new value. Simply, an expression is code that evaluates to a value.

Most everything in JS is an expression - it has a value!

* A value is an expression: `cool` returns `cool`
* A variable is an expression: `name` returns the assigned value
* A variable declaration is an expression: `let name;` returns `undefined`
* A variable assignment is an expression: `name = 'Charlie';` returns `Charlie`

## Numbers

The JavaScript `Number` type is used to represent and manipulate numbers. It can represent whole and fractional values, but there are some limits.

In JavaScript, all numbers are floating point. Integers are floating-point numbers without a fraction.

* `1`; `3.14`; `-20`; `4.5e7`;
* [64-bit floating number](https://0.30000000000000004.com/)
  * window.location = `https://${0.1 + 0.2}.com`
  * store monetary values in cents
* `typeof +/-Infinity` is `number`
* `typeof NaN` is `number`

`NaN` represents a `Number` that doesn't make sense
  * `0 / 0`
  * `1 + 'one'`
  * [WAT - Destroy All Software](https://www.destroyallsoftware.com/talks/wat)

## Operators

Operators act on values to produce new values. The value and side effects differ for each operator.

Arithmetic
  * `+`, `-`, `*`, `/`

The `+` is loaded. You can use it for string concatenations, as well as addition. Watch out for type coercion!
```
const message = 'Hello, ' + 'World!';

const sum1 = 2 + 2;
const sum2 = 2 + '3'; // the number is coerced to a string
```
Coercion with other operators will convert to numbers
```
const product1 = 2 * 3;
const product2 = 2 * '3'; // the string is coerced to a number
```
The `modulus` operator is used to return the remainder
```
const remainder1 = 4 % 3;
const remainder2 = 234390 % 34390;
```
```
const numOfOreos = 45;
const numOfStudents = 6;

console.log(`Each student gets ${Math.floor(numOfOreos / numOfStudents)} Oreos.`);
console.log(`There are ${numOfOreos % numOfStudents} Oreos left.`);
```
## Helper Methods

* `Math.pow()`
  * `Math.pow(2, 2);`
  * `Math.pow(2, 2, 2);`
  * `2 ** 2 ** 2;`
* `Math.round()`
* `Math.floor()`
* `Math.ceil()`
* `Math.random()`
```
const numArray = [2,3,4,2,6,4];

let randomNum = numArray[Math.floor(Math.random() * numArray.length)];

randomNum = numArray[Math.floor(Math.random() * numArray.length)];

randomNum = numArray[Math.floor(Math.random() * numArray.length)];
```
