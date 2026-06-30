<div align="center">
  <h1>Props </h1>
  
</div>

[<< Day 4](../04_Day_Component/04_components.md) | [Day 6 >>](../06_Day_Map_List_Keys/06_map_list_keys.md)

![30 Days of React banner](../images/30_days_of_react_banner_day_5.jpg)

- [Props](#props)
  - [Props in Functional Component](#props-in-functional-component)
  - [What is props?](#what-is-props)
  - [Props object](#props-object)
    - [Different data type props](#different-data-type-props)
    - [String props type](#string-props-type)
    - [Number props type](#number-props-type)
    - [Boolean props type](#boolean-props-type)
    - [Array props type](#array-props-type)
    - [Object props type](#object-props-type)
    - [Function prop types](#function-prop-types)
  - [Destructuring props](#destructuring-props)
  - [propTypes](#proptypes)
  - [defaultProps](#defaultprops)
- [Exercises: Components and Props](#exercises-components-and-props)
  - [Exercises: Level 1](#exercises-level-1)
  - [Exercises: Level 2](#exercises-level-2)
  - [Exercises: Level 3](#exercises-level-3)

# React Props

Props are arguments passed into React components.

Props are passed to components via HTML attributes.

``` props stands for properties.```


## What is props?

Props is a special keyword in React that stands for properties and is being used to pass data from one component to another and mostly from parent component to child component. We can say props is a data carrier or a means to transport data.

React Props are like function arguments in JavaScript and attributes in HTML.

To send props into a component, use the same syntax as HTML attributes:

Example
Add a brand attribute to the Car element:


```js
createRoot(document.getElementById('root')).render(
  <Car brand="Ford" />
);
```

The component receives the argument as a props object:

Example
Use the brand attribute in the Car component:

```js
function Car(props) {
  return (
    <h2>I am a {props.brand}!</h2>
  );
}
```

The name of the object is props, but you can call it anything you want.

Example
You can use myobj instead of props in the component:
```js
function Car(myobj) {
  return (
    <h2>I am a {myobj.brand}!</h2>
  );
}
```


## Pass Multiple Properties

You can send as many properties as you want.

Every attribute is sent to the Car component as object properties.

Example
Send multiple properties to the Car component:
```js
createRoot(document.getElementById('root')).render(
  <Car brand="Ford" model="Mustang" color="red" />
);
```
All properties are received in the Car component inside the props object:

Example
Use the property values in the Car component:
```js
function Car(props) {
  return (
    <h2>I am a {props.color} {props.brand} {props.model}!</h2>
  );
}
```

## Different Data Types

React props can be of any data type, including variables, numbers, strings, objects, arrays, and more.

Strings can be sent inside quotes as in the examples above, but numbers, variables, and objects need to be sent inside curly brackets.

Example
Numbers has to be sent inside curly brackets to be treated as numbers:
```js
createRoot(document.getElementById('root')).render(
  <Car year={1969} />
);
```
Example
Variables has to be sent inside curly brackets:
```js
let x = "Ford";

createRoot(document.getElementById('root')).render(
  <Car brand={x} />
);
```

Example
Objects and Arrays has to be sent inside curly brackets:
```js
let x = [1964, 1965, 1966];
let y = {name: "Ford", model: "Mustang"};

createRoot(document.getElementById('root')).render(
  <Car years={x} carinfo={y} />
);
```

## Object Props

The component treats objects like objects, and you can use the dot notation to access the properties.

Example
Use the dot notation to access object properties:
```js
function Car(props) {
  return (
    <>
      <h2>My {props.carinfo.name} {props.carinfo.model}!</h2>
      <p>It is {props.carinfo.color} and it is from {props.carinfo.year}!</p>
    </>
  );
}

const carInfo = {
  name: "Ford",
  model: "Mustang",
  color: "red",
  year: 1969
};

createRoot(document.getElementById('root')).render(
  <Car carinfo={carInfo} />
);

```

## Array Props

Array props can be accessed using the indexes.

Example
Use the indexes to access array properties:

```js
function Car(props) {
  return (
    <h2>My car is a {props.carinfo[0]} {props.carinfo[1]}!</h2>
  );
}

const carInfo = ["Ford", "Mustang"];

createRoot(document.getElementById('root')).render(
  <Car carinfo={carInfo} />
);
```

## Pass Props from Component to Component

Attributes are also how you pass data from one component to another, as parameters.

Example
Send the brand attribute from the Garage component to the Car component:
```js
function Car(props) {
  return (
    <h2>I am a {props.brand}!</h2>
  );
}

function Garage() {
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
    </>
  );
}

createRoot(document.getElementById('root')).render(
  <Garage />
);

```

# React Destructuring Props

## Destructuring Props
You can limit the properties a component receives by using destructuring.

Example
The component knows it only need the color property, so in the function definition, it only specifies that:
```js
function Car({color}) {
  return (
    <h2>My car is {color}!</h2>
  );
}

createRoot(document.getElementById('root')).render(
  <Car brand="Ford" model="Mustang" color="red" year={1969} />
);
```
Note: React uses curly brackets to destructure props: {color}.

You can also destruct the properties you need inside the component.

This way, the component receives all the properties, but the destructuring makes sure it only uses the ones it needs.

Example
The component receives all the properties, but uses destructuring to limit the properties inside the component.
```js
function Car(props) {
  const {brand, model} = props;
  return (
    <h2>I love my {brand} {model}!</h2>
  );
}

createRoot(document.getElementById('root')).render(
  <Car brand="Ford" model="Mustang" color="red" year={1969} />
);
```


## Destructuring ...rest
When you don't know how many properties you will receive, you can use the ...rest operator.

Meaning: you can specify the properties you need, and the rest will be stored in an object.

Example
The component specifies the color and the brand, but the rest is stored in an object like this:
```{ model: "Mustang", year: 1969 }```.
```js
function Car({color, brand, ...rest}) {
  return (
    <h2>My {brand} {rest.model} is {color}!</h2>
  );
}

createRoot(document.getElementById('root')).render(
  <Car brand="Ford" model="Mustang" color="red" year={1969} />
);
```
## Default Values
With Destructuring, you can set default values for props.

If a property has no value, the default value will be used.

Example
Set the default color value to "blue":
```js
function Car({color = "blue", brand}) {
  return (
    <h2>My {color} {brand}!</h2>
  );
}

createRoot(document.getElementById('root')).render(
  <Car brand="Ford" />
);
```

# React Props Children
## Props Children

In React, you can send the content between the opening and closing tags of a component, to another component.

This can be accessed in the other component using the ``` props.children ``` property.

Example
From the Parent component, send the content between the opening and closing tags of the Son and Daughter components:
```js
function Son(props) {
  return (
    <div style={{background: 'lightgreen'}}>
      <h2>Son</h2>
      <div>{props.children}</div>
    </div>
  );
}

function Daughter(props) {
  const {brand, model} = props;
  return (
    <div style={{background: 'lightblue'}}>
      <h2>Daughter</h2>
      <div>{props.children}</div>
    </div>
  );
}

function Parent() {
  return (
    <div>
      <h1>My two Children</h1>
      <Son>
        <p>
          This was written in the Parent component,
          but displayed as a part of the Son component
        </p>
      </Son>
      <Daughter>
        <p>
          This was written in the Parent component,
          but displayed as a part of the Daughter component
        </p>
      </Daughter>
    </div>
  );
}

createRoot(document.getElementById('root')).render(
  <Parent />
);

```





🎉 CONGRATULATIONS ! 🎉


