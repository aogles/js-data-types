## What are Variables?

A variable is like a name badge, in that it doesn't contain anything, but is a name or label for a value.

**Declare a variable:**

  `var age;`

**Assign a value to a variable:**

  `age = 52;`

A single equal sign is the `assignment operator`.

**Shorthand:**

  `var age = 52;`

**Declare multiple variables:**

  `var age, favoriteColor, name;`

**Declare and assign multiple variables:**

  `var age = 37, favoriteColor = "green", name = "Jake";`

## Variable Naming

* First character `a-z`, `A-Z`, `$`, `_`
* Variables starting with `$` are often used for DOM objects
  * Use `$` to reference DOM objects
  * `function $(x) {return document.getElementById(x);}` (idea behind jQuery)
  * `$` heavily associated with jQuery library (has declined in popularity due to core functionality added to vanilla JavaScript)
* Variables starting with `_` are often used for things that are not meant to be used by the developer
  * underscore convention is a pretty good convention to use for things that are sort of private, but that you don't actually need to hide
  * Use `_` to preface the name of an object's property or method that is private - a property or method that is accessible internally, but not to be called outside the object
  * standard way to indicate an unused function argument, e.g. an unused variable during looping:
    ```
    # JavaScript

    const object = { a: 1, b: 2, c: 3 };
    let propertyCount = 0;

    for (const _ in object) {
      propertyCount++;
    }
    ```
    ```
    # Python

    [0 for _ in range(n)]
    ```
  * `_` is heavily associated with the Underscore library
* The other characters can be letters, `$`, `_` , or numbers
* They are case sensitive
* The convention, but not rule, is to capitalize each word after the first

## var, let and const

* var
  * Declares a variable, optionally initializing it to a value
  * Subject to hoisting (declarations only)
  * [Is var dead?](https://wesbos.com/is-var-dead)
* let
  * Declares a block-scoped, local variable, optionally initializing it to a value
  * Not subject to variable hoisting
* const
  * Declares a block-scoped, read-only named constant
  * Not subject to variable hoisting

*Variables are not tied to a type. A variable can be assigned data of any type, and `var` and `let` can be reassigned data of any type.*

## More Practice
```
var name = 'Fluffy'; // this is a variable declaration statement
let age = 300;
const cool = true;
```
`var` and `let` can be updated
```
name = 'Sam'; // you don't have to redeclare the variable
age = 30;
```
What happens if you try to reassign `const`?

## Scope

Scope answers the questions "Where do variables live?". "Where are my variables available to me?" and "How does my code find them?".

A variable declared outside a function, becomes GLOBAL. A global variable has global scope: All scripts and functions on a web page can access it.

* `var` is function scoped
* `let` and `const` are block scoped
  * there is a period between entering scope and being declared where they cannot be accessed
  * this period is the temporal dead zone, the state where variables are un-reachable inside their scope ***possible interview question***
  * `let` and `const` variables exist in the temporal dead zone from the start of their enclosing scope until they are declared
* `let` and `const` were implemented with ES2015 standard
```
var name = 'Mady';
function greeting() {
  console.log(name)
}
```
```
function greeting() {
  var name = 'Mady';
  console.log(name)
}
```
```
function greeting() {
  var name = 'Mady';
}
console.log(name);
```
```
for(var i = 0; i < 10; i++) {
  setTimeout(function() {
    console.log(`The value of 'i' is ${i}.`)
  }, 1000);
}
```
```
for(let i = 0; i < 10; i++) { // start of code block
  setTimeout(function() {
    console.log(`The value of 'i' is ${i}.`)
  }, 1000);
}
```

## [Strict Mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)

JavaScript's strict mode, introduced in ECMAScript 5, is a way to opt in to a restricted variant of JavaScript, thereby implicitly opting-out of "sloppy mode". Strict mode isn't just a subset: it intentionally has different semantics from normal code.

Strict mode makes several changes to normal JavaScript semantics:

* Eliminates some JavaScript silent errors by changing them to throw errors.
* Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that's not strict mode.
* Prohibits some syntax likely to be defined in future versions of ECMAScript.
* Strict mode is enforced by default when you use JS Modules.

Example of silent error that strict mode eliminates...
```
<script>
  heroString = 'I am batman'; // no error unless you add 'use strict' above it
</script>
```
The browser goes ooops, you forgot, I'll do it for you! BAD! Why does this functionality still exist? Backwards compatibility.
```
<script>
  'use strict'
  heroString = 'I am batman'; // error
</script>
```
