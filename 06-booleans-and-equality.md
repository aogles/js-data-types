## Booleans

A `boolean` value is either `true` or `false`. It's like a light switch - it's either on or off.

## Operators

Operators act on values to produce new values. The value and side effects differ for each operator.

**[Equality Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Equality_operators)**
  * `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=`
  * Loose equality
  * Strict equality

**[Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Binary_logical_operators)**
  * Logical operators are typically used with `Boolean` (logical) values. When they are, they return a `Boolean` value.
  * logical NOT `!`, logical OR `||`, logical AND `&&`

  * `! true`
  * `!(10 > 5)`
  * `!!2`

  * `true && true`
  * `true && false`
  * `10 > 5 && 10 < 100`
  * `10 > 5 && 10 < 10`

  * `true || true`
  * `true || false`
  * `false || false`
  * `10 > 5 || 10 < 100`
  * `10 > 5 || 10 < 10`

**[Assignment Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators)**
  * `=` assigns a value
  * `==` and `===` are used for comparison

`Boolean` logic is the basis of making decisions in JavaScript.
```
const age = 22;
if(age > 21) {
  console.log('beer');
}
```
Some things to keep in mind.

* `true` is not the same as `'true'`
* NOT is `!` AND is `&&` OR is `||`
* If two things must be true to proceed, then condition1 AND condition2 is the logical statement you need
* If only one of two things must be true to proceed, then condition1 OR condition2 is the logical statment you need
* In JavaScript, all values are either `truthy` or `falsy`, meaning they can be (and are) coerced into booleans by operators and control flow
* JavaScript uses Type Conversion to coerce any value to a `Boolean` in contexts that require it, such as conditionals and loops

**Falsy values (considered false when evaluated in a Boolean context)**
  * `""`
  * `0`
  * `false`
  * `null`
  * `undefined`
  * `NaN`

## Equality

* If two values have the same type, just compare them
* If two values have different types, try to coerce them into the same type and then compare them

## Coercion

* When comparing a `Number` and `String`, coerce the `String` to a `Number`
* When comparing a `Boolean` and Anything, coerce the `Boolean` to a `Number`
* `null == undefined` returns `true`
* `NaN == NaN` returns `false`
* There can be multiple steps

In this example, the `String` is coerced to a `Number`, the comparison is performed, and the value returned
```
1 / 1 == "";
1 == 0;
returns false;
```
The `Boolean` is coerced to a `Number`, the `String` is coerced to a `Number`, the comparison is performed, and the value returned
```
"1" == true;
"1" == 1;
1 == 1;
returns true;
```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#Loose_equality_using

## Strict Equality

* Two expressions are strictly equal if they have the same type and the same value
* Types are not coerced

## Object Equality

Objects (incl. arrays and functions) are compared by reference. Two references are only equal if they reference the same object.

## Other Coercion

* If you try to add anything to a `String`, the other operand is coerced to a `String` and the two `Strings` are concatenated
* To coerce an `Object` (incl. arrays and functions) to a `String`, the   `toString`  method is called on the `Object`
```
function greeting() {
  console.log('Hello, World!');
}

greeting.toString();
```
