<div align="center">
  <h1> Getting Started with ReactJS</h1>
 

<sub>Author:
<a>Romel Mejos</a><br>
</sub>

</div>


# Getting Started React

This section covers prerequisites to get started with React. You should have a good understanding of the following technologies:

- HTML
- CSS
- JavaScript



# 1. What is React?

React (also known as React.js or ReactJS) is a JavaScript library for building a reusable user interface(UI). It was initially released on May 29, 2013. React was created by Facebook Software Engineer Jordan Walke. React makes creating UI components very easy. The official React documentation can be found [here](https://reactjs.org/docs/getting-started.html). When we work with React we do not interact directly with the DOM. React has its own way to handle the DOM(Document Object Model) manipulation. React uses its virtual DOM to make new changes and it updates only the element, that needs changing. Do not directly interact with DOM when you build a React Application and leave the DOM manipulation job for the React virtual DOM.

To summarize:

- React was released in May 2013
- React was created by Facebook
- React is a JavaScript library for building user interfaces
- React is used to build single page applications - An application which has only one HTML page.
- React allows us to create reusable UI components
- React latest release 
- [React versions](https://reactjs.org/versions/)
- React official documentation can be found [here](https://reactjs.org/docs/getting-started.html)

# 2. Why React?
Here is exactly why developers, startups, and tech giants choose React.

## Core Technical Advantages

1. Component-Based Architecture: UI is broken down into small, isolated Lego-like pieces called components. You write a component once (like a button or navigation bar) and reuse it across your entire application, significantly speeding up development.

2. The Virtual DOM: Standard JavaScript updates the entire web page layout when data changes, which causes lagging. React creates a lightweight copy of the page in its memory (the Virtual DOM), isolates exactly what changed, and updates only that specific element.

3. Declarative UI: Instead of writing complex, step-by-step instructions to manipulate the user interface, you simply describe what the UI should look like based on the current state. React automatically updates the view when the data updates.JSX Syntax:

4. React uses JSX (JavaScript XML), allowing you to write HTML structure directly inside your JavaScript code. This keeps your visual layout and logical code perfectly unified and highly readable.

## Business & Career Benefits

1. Massive Job Market: React is highly sought after by employers globally. Learning React opens doors to high-paying development roles and extensive freelance opportunities.
   
3. Backed by Meta: Created and maintained by Meta (formerly Facebook), React is heavily used across their live platforms like Facebook and Instagram. This guarantees the tool remains stable, supported, and continuously updated for years to come.
   
5. Unmatched Ecosystem: Because of its massive community, you can find pre-built solutions, testing libraries, and UI packages for almost any feature you need to build.
   
7. Cross-Platform Efficiency: By learning React, you instantly gain a foundation for mobile development. Using React Native, you can build native iOS and Android apps using the exact same design concepts and code structures


## Why we choose to use React ? We use it because of the following reasons:

- fast
- modular
- scalable
- flexible
- big community and popular
- open source
- High job opportunity

# 3. JSX

JSX stands for JavaScript XML, and it is a syntax extension for JavaScript used primarily in React JS to easily write and structure user interfaces. It allows you to write HTML-like markup directly inside a JavaScript file, combining your visual interface structure with your application logic in one cohesive place.

## Core Rules of JSX

JSX has a few strict formatting rules that differentiate it from traditional HTML:

1. Single Root Element: You must wrap adjacent elements in a single parent container (like a <div>) or an empty fragment (<>...</>).
   
3. Close Every Tag: All tags must be explicitly closed, including self-closing elements like <img /> or <br />.
   
5. camelCase Attributes: Because JSX turns into JavaScript, attributes use JavaScript naming conventions. For instance, HTML's class becomes className, and onclick becomes onClick.



```js
// JSX syntax
// we don't need to use quotes with JSX

const jsxElement = <h1>I am a JSX element</h1>
const welcome = <h1>Welcome to React Challenge</h1>
const data = <small>June 2026</small>
```

The above strange looking code seems like JavaScript and it seems like , but it is not JavaScript and it seems like HTML but not completely an HTML element. It is a mix of JavaScript and an HTML elements. JSX can allow us to use HTML in JavaScript. The HTML element in the JSX above is _h1_ and _small_.


# JSX Expressions

Expressions - You can insert any valid JavaScript expression inside JSX by wrapping it in curly braces { }.

React will evaluate the expression and render the result in the DOM.

Example
Execute the expression 218 * 1.36:

```js
function Car() {
  return (
    <>
      <h1>My car</h1>
      <p>It has {218 * 1.36} horsepower</p>
    </>
  );
} 
```
## Variables 

Variables are also valid expressions. Insert variables in JSX by wrapping it in curly braces { }.

Example
Use a variable inside JSX:

```js
function Car() {
  const hp = 218 * 1.36;
  return (
    <>
      <h1>My car</h1>
      <p>It has {hp} horsepower</p>
    </>
  );
}
```
## Function Calls 

Function Calls are valid expressions. Insert function calls in JSX by wrapping it in curly braces { }.

Example
Use a function inside JSX:

```js
function kwtohp(kw) {
  return kw * 1.36;
}

function Car() {
  return (
    <>
      <h1>My car</h1>
      <p>It has {kwtohp(218)} horsepower</p>
    </>
  );
}
```

## Object Properties

Access object properties within JSX:

Example
Refer to an object property inside JSX:

```js
function Car() {
  const myobj = {
    name: "Fiat",
    model: "500",
    color: "white"
  };
  return (
    <>
      <h1>My car is a {myobj.color} {myobj.name} {myobj.model}</h1>
    </>
  );
}
```


# JSX Attributes

JSX allows you to insert attributes into HTML elements, but there are a few important differences.

``` class = className ```

The class attribute is a much used attribute in HTML, but since JSX is rendered as JavaScript, and the class keyword is a reserved word in JavaScript, you are not allowed to use it in JSX.

JSX solved this by using className instead. When JSX is rendered, it translates className attributes into class attributes.

Example
Use attribute className instead of class in JSX:

```js
function Car() {
  return (
    <h1 className="myclass">Hello World</h1>
  );
}
```

## Expressions as Attributes

You can also use JavaScript expressions as attribute values. This is very useful for dynamic attributes.

Example
Use JavaScript expressions as attribute values:
```js
function Car() {
  const x = "myclass";
  return (
    <h1 className={x}>Hello World</h1>
  );
}
```

Note that the attribute value is not wrapped in quotes, this is important when using expressions (JavaScript variables) as attribute values. If you use quotes, JSX will treat it as a string literals and not a JavaScript expression.

camelCase Event Attributes
Event attributes in JSX are written in camelCase.

Example
Use camelCase for event attributes:
```js
function Car() {
  const myfunc = () => {
    alert('Hello World');
  };
  return (
    <button onClick={myfunc}>Click me</button>
  );
}
```
## Boolean Attributes

If you pass no value for an attribute, JSX treats it as true. To pass false, you must specify it as an expression.

Example
Boolean true in JSX, this will make the button disabled:
```js
<button onClick={myfunc} disabled>Click me</button>
```
Example
Also true in JSX, this will also make the button disabled:
```js
<button onClick={myfunc} disabled={true}>Click me</button>
```
Example
False in JSX, this will NOT make the button disabled:
```js
<button onClick={myfunc} disabled={false}>Click me</button>
```

## The style Attribute

The style attribute in JSX only accepts a JavaScript object with camelCased CSS property names, rather than a CSS string (as in HTML).

Example
Use the style attribute:
```js
function Car() {
  const mystyles = {
    color: "red",
    fontSize: "20px",
    backgroundColor: "lightyellow",
  };

  return (
    <>
      <h1 style={mystyles}>My car</h1>
    </>
  );
}
```
Notice two things about the example above.

The styles are stored in an object.

Style properties are written in camelCase, e.g. fontSize, instead of font-size.
This is an important difference between HTML and JSX.


