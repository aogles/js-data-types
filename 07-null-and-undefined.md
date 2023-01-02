## `null` and `undefined`

`null` and `undefined` express nothing, but in different ways. If you declare a variable and do not initialize it to a value, the value is `undefined`. The variable exists, but the value is not set. `Null` is a value that is explicitly set.

`Undefined` does not have a value set, whereas `null` is something that has a value of nothing.

* `null`
  * represents an object that is not defined
  * you can empty an object by setting it to `null` (the value is `null`, but type is still an `object`)
  * `typeof null` is `object`
* `undefined`
  * represents a value that is not defined
  * You can empty an object by setting it to `undefined` (both value and type is `undefined`)
  * `typeof undefined` is `undefined`
```
const person = {
  name: 'Cher';
}

console.log(person.last);
```
```
const student = {
  firstName: 'Charlie',
  lastName: 'Zwiers'
}

student.lastName = null;
```
