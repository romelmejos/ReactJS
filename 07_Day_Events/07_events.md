<div align="center">
  <h1> Events</h1>
 
</div>


# Events

## What is an event?

An event is an action or occurrence recognized by a software. To make an event more clear let's use the daily activities we do when we use a computer such as clicking on a button, hover on an image, pressing a keyboard, scrolling the mouse wheel and etc. In this section, we will focus only some of the mouse and keyboard events. The react documentation has already a detail note about [events](https://reactjs.org/docs/handling-events.html).

Handling events in React is very similar to handling elements on DOM elements using pure JavaScript. Some of the syntax difference between handling event in React and pure JavaScript:

- React events are named using camelCase, rather than lowercase.
- With JSX you pass a function as the event handler, rather than a string.

Just like HTML DOM events, React can perform actions based on user events.

React has the same events as HTML: click, change, mouseover etc.



## Adding Events

React events are written in camelCase syntax:

onClick instead of onclick.

React event handlers are written inside curly braces:

onClick={shoot}  instead of onclick="shoot()".

REACT:
```js
<button onClick={shoot}>Take the Shot!</button>
```

HTML:
```html
<button onclick="shoot()">Take the Shot!</button>
```

Example:
Put the shoot function inside the Football component:

```js
function Football() {
  const shoot = () => {
    alert("Great Shot!");
  }

  return (
    <button onClick={shoot}>Take the shot!</button>
  );
}

createRoot(document.getElementById('root')).render(
  <Football />
);
```
## Passing Arguments

To pass an argument to an event handler, use an arrow function.

Example:
Send "Goal!" as a parameter to the shoot function, using arrow function:

```js
function Football() {
  const shoot = (a) => {
    alert(a);
  }

  return (
    <button onClick={() => shoot("Goal!")}>Take the shot!</button>
  );
}

createRoot(document.getElementById('root')).render(
  <Football />
);
```

## React Event Object
Event handlers have access to the React event that triggered the function.

In our example the event is the "click" event.

Example:
Arrow Function: Sending the event object manually:

```js
function Football() {
  const shoot = (a, b) => {
    alert(b.type);
    /*
    'b' represents the React event that triggered the function,
    in this case the 'click' event
    */
  }

  return (
    <button onClick={(event) => shoot("Goal!", event)}>Take the shot!</button>
  );
}

createRoot(document.getElementById('root')).render(
  <Football />
);
```
This will come in handy when we look at Form in a later chapter.


