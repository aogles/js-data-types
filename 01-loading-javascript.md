## Loading JavaScript

### 1. In the JavaScript console

* `option + cmd + J`
* `$ console.log('Hello, World!');`

***JS that runs in the console is running in context to the page loaded in the browser window.***

* `$ document.querySelectorAll('div');`

### 2. In a script tag (without a source attribute)
```
<script>
  console.log('Hello, World!');
</script>
```
```
<script>
  const element = document.querySelector('p');
  console.log(element);
</script>
```
**NOTE: Demonstrate selecting an element in the DOM and printing it to the console. Demo the result when (1) the script tag is above the HTML in the `body` element, (2) inside the `head` element, and (3) when it is below the HTML in the `body` element.**
```
<body>
  <script>
    const element = document.querySelector('div');
    console.log(element);
  </script>
  <div>Hello, world!</div>
</body>
```
```
<head>
  <script>
    const element = document.querySelector('div');
    console.log(element);
  </script>
</head>
<body>
  <div>Hello, world!</div>
</body>
```
```
<body>
  <div>Hello, world!</div>
  <script>
    const element = document.querySelector('div');
    console.log(element);
  </script>
</body>
```
### 3. In a script tag (with a source attribute that references an external file)

You do not need a type attribute unless you're referencing module code.
```
<script type="module" src="main.js"></script>
```
An omitted type attribute indicates the script is JavaScript. The HTML5 specification urges authors to omit the attribute rather than provide a redundant MIME type (Multipurpose Internet Mail Extensions or MIME type).

MIME type, also know as media type, indicates the nature and format of a document, file, or assortment of bytes.

MIME types gives the browser information, so it knows how to handle the specified file.
```
console.log('Hello, World!');
```
```
const element = document.querySelector('p');
console.log(element);
```
A source attribute nullifies all JS inside the opening and closing script tags.

**INSTRUCTOR: Demonstrate selecting an element in the DOM and printing it to the console. Demo the result when (1) the script tag is in the `head` element and (2) when it is below the HTML in the `body` element.**

### 4. In the REPL

* `$ node`
* `> 2 + 2`
* `$ control + C` to exit
* Stands for read-evaluate-print loop
* It's an interactive console where you can type in commands and immediately see the result of those commands

### 5. From the terminal using the `node` command

* `$ node <filename>`
