## Strings
```
const string1 = 'Hello, World!';

const string2 = "Today is the first day of school!";

const string3 = `JavaScript is awesome!`
```
**String Methods**
* `String.length`
* `String.toLowerCase()`
* `String.toUpperCase()`
* `String.replace()`

**ES2015 Methods**
* `Strings.startsWith()`
* `Strings.endsWith()`
* `Strings.includes()`
* `Strings.repeat()`

*Conflicts with new tool libraries and the way they modify the prototype is why we have `includes` instead of `contains`.*

## Escape Notation
```
const string4 = 'It\'s a great day to learn JavaScript!'
const string5 = "He asked, \"What time is it?\"."
```
## String Concatenation
```
const name = 'Mady';
const message = "Hello, my name is " + name + ". How are you today?";
```
## String Interpolation
```
const dog = 'Charlie';
const age = 10;
let message = `My dog ${dog} is ${age} years old.`;
message = `My dog ${dog} is ${age * 7} in dog years.`;
```
## Long String Literals
```
let longString = "This is a very long string which needs " +
                 "to wrap across multiple lines because " +
                 "otherwise my code is unreadable."
```
```
let longString = "This is a very long string which needs \
                  to wrap across multiple lines because \
                  otherwise my code is unreadable."
```
```
let longString = `This is a very long string which needs
                  to wrap across multiple lines because
                  otherwise my code is unreadable.`
```
### HTML Fragments with Template Literals
```
const person = {
  name: 'Sara',
  job: 'Web Developer',
  city: 'Greenville',
  bio: 'Sara is a cool girl who loves learning JavaScript!',
}

const markup = `
  <div>
    <h2>
      ${person.name}
      <span>${person.job}</span>
    </h2>
    <p>${person.city}</p>
    <p>${person.bio}</p>
  </div>
`
document.body.innerHTML = markup;
```
```
const dogs = [
  {name: 'Charlie', age: 10},
  {name: 'Joey', age: 4},
  {name: 'Ozzie', age: 7},
];

const markup = `
  <ul>
    ${dogs.map(dog => `<li>${dog.name}</li>`).join('')}
  </ul>
`

document.body.innerHTML = markup;
```
## Tagged Template Literals

**First Attempt**
```
function highlight(strings, values) {
  debugger; // throw debugger in so you can access local scope in the console
  console.log('strings', strings);
  console.log('values', value); // values is only the first value, not all value
}

const dog = 'Charlie';
const age = 10;
const message = highlight`My dog's name is ${dog} and he is ${age} old.`;
```
**Second Attempt**
```
function highlight(strings, value1, value2) {
  debugger;
  console.log('strings', strings);
  console.log('value1', value1);
  console.log('value2, value2'); // what if you don't know how many values were passed in
}

const dog = 'Charlie';
const age = 10;
const message = highlight`My dog's name is ${dog} and he is ${age} old.`;
```
**Third Attempt**
```
function highlight(strings, ...values) {
  debugger;
  console.log('strings', strings);
  console.log('values', values); // values is an array of all values passed in
}
const dog = 'Charlie';
const age = 10;
const message = highlight`My dog's name is ${dog} and he is ${age} old.`;
```
**Let's Do This!**
```
function format(strings, ...values) {
  let str = '';
  strings.forEach((string, i) => {
    // here you can modify the text, create html, etc. if you wanted to
    str += string + (values[i] || ''); // strings array is always one more than values array
  });
  return str;
}
const dog = 'Charlie';
const age = 10;
const message = format`My dog's name is ${dog} and he is ${age} old.`;
```
## Fun With Strings

**Exercise One**
```
function leftPad(str, length = 10) {
  return `${' '.repeat(length - str.length)}${str}`;
}

console.log(leftPad('name'));
console.log(leftPad('address'));
console.log(leftPad('city'));
console.log(leftPad('state'));
```
**Exercise 2**
```
`${0 / 0}`.repeat(10) + ' Batman!';
```
