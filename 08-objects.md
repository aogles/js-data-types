## JavaScript Objects

Almost everything in JavaScript is an `Object`. In fact, only six things are not `Objects`. They are - `null`, `undefined`, `String`, `Number`, `Boolean`, `Symbol` and `BigInt`.

An `Object` creates an association between two terms, the `key` and the `value`.
```
{ key: value }
```
The combination of the `key` and `value` represent a `property` on that `Object`.

An `Object` is a collection of `key` `value` pairs.

`Objects` are used for modeling. We can model a user profile, personal accounts and application data.

### Object Literal Syntax
```
const student = {
  first: 'Justin',
  last: 'Hathaway',
  age: 21,
}
```
When defining JavaScript properties, the `key` is always a `String`. However, the property keys don't require quotes (`""`) like usual `Strings`.

Property values can be any type.

You can also leave spaces between keys, values and the colon to increase readability.

Be sure to separate properties with commas.

### Dot Notation

Dot notation allows us to access properties inside an object.
```
const student = {
  first: 'Justin',
  last: 'Hathaway',
  age: 21,
  greeting: function() {
    console.log(`Hi. I'm ${this.first}.`)
  }
}
student.age;
student.greeting();
```
Dot notation allows us to add and edit properties inside an object.
```
student.first = 'Henry';
student.grade = 89;
```
**You can accidentally change the type of a property value to another type if you aren't careful.**
```
student.greeting = `Hi. My name is ${this.first} ${this.last}.`;
student.greeting();
```
You can also delete properties in a `Object`.
```
delete student.last;
```
### Square Bracket Notation

Bracket notation allows us to access properties with `Strings`. When using bracket notation, the property is wrapped in square brackets (`[]`) and the `key` is always a `String`.
```
student["age"];
```
Use bracket notation when accessing a property with a variable.
```
const student = {
  first: 'Justin',
  last: 'Hathaway',
  age: 21,
}
const key = prompt('What are you looking for?');
student[key];

const last = prompt('What is your last name?');
student[last] = 'Chapman';
```
`Object` keys can include spaces and dashes. Use square bracket notation to access and/or update properties of an `Object` if the `key` includes a space or a dash.

### Object Equality

`Objects` (incl. `Arrays` and `Functions`) are compared by reference. Two references are only equal if they reference the same `Object`.
```
{ name: 'Charlie' } === { name: 'Charlie' }
```
```
const a = [1];
const b = a;

a === b
```
### ES2015 Syntax
```
let age = 30;
const person = {
  age,
  name: 'Elise',
}
```
## JavaScript Symbols (ES2015)

A `Symbol` is a unique identifier.

`Symbols` help us avoid naming collisions. When you need to create a property in a unique way, that's when you should reach for a `Symbol`.
```
const mady = Symbol('Mady');
```
The value passed to `Symbol` is called the descriptor - not a value.
```
console.log(mady);

const person = Symbol('Mady');
console.log(person);

console.log(mady === person);
console.log(mady == person);
```
`Symbols` are absolutely unique - you will never have a naming collision with them.
```
const classRoom = {
  'Mark': { grade: 50, gender: 'male' },
  'Mary': { grade: 80, gender: 'female' },
  'Mark': { grade: 70, gender: 'male' },
}

console.log(classRoom.Mark);

const classRoom = {
  [Symbol('Mark')]: { first: 'Mark', last: 'Smith', grade: 50, gender: 'male' },
  [Symbol('Mary')]: { first: 'Mary', last: 'Jones', grade: 80, gender: 'female' },
  [Symbol('Mark')]: { first: 'Mark', last: 'Cole', grade: 70, gender: 'male' },
}

console.log(classRoom);
```
Symbols are not iterable.
```
for(person in classRoom) {
  console.log(person);
}

const symbols = Object.getOwnPropertySymbols(classRoom);
const data = symbols.map(symbol => classRoom[symbol]);
data.map((person) => console.log(person));
```
