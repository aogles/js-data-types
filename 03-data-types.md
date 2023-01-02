## JavaScript Comments

A comment is ignored by the JS engine

```
// This is an example of a single line comment
```
```
/*
This is an example of a multi-line comment
Multi-line comments start with /* and end with */
Any text between /* and */ will be ignored by JavaScript
*/
```
A JavaScript program is one or more JS statements. Like a sentence, a statement is one coherent "thought" or instruction.

A statement is an instruction to the computer, to the browser, to the JavaScript interpreter to do something.

* It should appear on its own line
* It should end with a semicolon (a semicolon means "this instruction is over, move to the next one.")

**Automatic Semicolon Insertion (ASI)**

JavaScript does not enforce the use of a semicolon at the end of a statement. Instead, the semicolon is optional, and the JavaScript interpreter will "intelligently" add them when it runs the code.

> I wish I had made newlines more significant in JS back in those ten days in May, 1995. Then instead of ASI, we would be cursing the need to use infix operators at the ends of continued lines, or perhaps \ or brute-force parentheses, to force continuation onto a successive line. But that ship sailed almost 17 years ago. - Brendan Eich

## JavaScript Built-in Data Structures

Six data types that are primitives:

* `boolean`
  * `true`; `false`; 10 > 5;
  * `undefined` is `false`
  * `null` is `false`
  * `boolean`: `true` is `true`, `false` is `false`
  * `number`: `+0`, `-0`, `NaN` are `false` otherwise `true`
  * `string`: `""` (it's length is 0) is `false` otherwise `true`
  * `object` is `true`
* `null`
  * represents an object that is not defined
  * you can empty an object by setting it to `null` (the value is `null`, but type is still an `object`)
  * `typeof null` is `object`
* `undefined`
  * represents a value that is not defined
  * You can empty an object by setting it to `undefined` (both value and type is `undefined`)
  * `typeof undefined` is `undefined`
* `number`
  * `1`; `3.14`; `-20`; `4.5e7`;
  * [64-bit floating number](https://0.30000000000000004.com/)
  * `typeof +Infinity/-Infinity` is `number`
  * `typeof NaN` is `number`
* `string`
  * `'Cool'`; `"Cool"`; `"That was 'cool'"`; `"That was \"cool\""`;
  * concatenation
  * interpolation
* `symbol`
  * `Symbols` do not have a literal syntax (e.g how `Strings` have `''`)
  * A `symbol` is a unique and immutable primitive value and may be used as the key of an `object` property

Anything that doesn’t belong to any of these six primitive types is considered an object: `{}`; `function` object; `array` object
