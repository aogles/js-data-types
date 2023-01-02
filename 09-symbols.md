## Symbols

A [symbol](https://developer.mozilla.org/en-US/docs/Glossary/Symbol) is a primitive value (non-mutable) which cannot be recreated. It's value represents a unique identifier. For example:
```
const sym1 = Symbol();
const sym2 = Symbol();
sym1 === sym2 // returns false
```
When instantiating a `Symbol` there is an optional description argument, but it is used for debugging purposes only. If provided, it doesn't really affect the symbol itself.
```
// Here are two symbols with the same description:
const sym1 = Symbol("debugging");
const sym2 = Symbol("debugging");
console.log(sym1 === sym2) // returns "false"
```
`Symbols` can be used as keys in objects. Here's an example:
```
const obj = {};
const sym = Symbol()

obj[sym] = 'hello';
obj.name = 'Sophie';

console.log(obj);
console.log(sym in obj);
console.log(obj[sym]);
console.log(Object.keys(obj)); // symbols do not show in the result of Object.keys()
```
To maintain backwards compatibility, symbols do not show in the result of `Object.keys()`. `Object.keys()` is older and returns an array whose elements are strings. If it's behavior was modified to return symbols, as well, it could (and in some cases would) break pre-existing code. 

If you want to return an array of all symbol properties, use `Object.getOwnPropertySymbols()` instead. Or, you can use `Reflect.ownKeys()` to get a list of all keys on an object that includes both strings and symbols.

### What are some real world benenfits?

Symbols prevent property name collisions when disparate libraries are used to add properties to objects.

Consider the situation where two different libraries are used to attach some sort of metadata to an object. Perhaps each library sets some sort of identifier on the object. If each library used the same identifier, e.g. the two character string `id`, a property name collision would occur.
```
function lib1tag(obj) {
  obj.id = 42;
}
function lib2tag(obj) {
  obj.id = 369;
}
```
```
function lib1tag(obj) {
  obj[Symbol('lib1')] = 42;
}

function lib2tag(obj) {
  obj[Symbol('lib2')] = 369;
}
```
### What are some shortcomings?

`Symbols` used as property names on an object are not represented in JSON payloads. JSON only allows strings as keys.
```
const user = {
  name: 'Kat',
  age: 21
};

lib1tag(user);
lib2tag(user);

JSON.stringify(user);
```
