<div align="center">
  <h1> Conditional Rendering</h1>

</div>

# Conditional Rendering

As we can understand from the term, conditional rendering is a way to render different JSX or component at different condition. We can implement conditional rendering using regular if and else statement, ternary operator and &&. Let's implement a different conditional rendering.

## Conditional Rendering using If and Else statement

We can use the if JavaScript operator to decide which component to render.

Example:
We'll use these two components:

```js
function MissedGoal() {
  return <h1>MISSED!</h1>;
}

function MadeGoal() {
  return <h1>Goal!</h1>;
}
```

Try changing the isGoal attribute to true:

```js
createRoot(document.getElementById('root')).render(
  <Goal isGoal={true} />
);
```


## Logical && Operator

Another way to conditionally render a React component is by using the && operator.

In the example below, the heading will only be rendered if the props.brand property is not empty:

Example:
The right side of && will only be rendered if the left side is true:


```js
function Car(props) {
  return (
    <>
      {props.brand && <h1>My car is a {props.brand}!</h1>}
    </>
  );
}

createRoot(document.getElementById('root')).render(
  <Car brand="Ford" />
);
```

If props.brand evaluates to true, the expression after && will render.

Try emptying the brand property:

```js
createRoot(document.getElementById('root')).render(
  <Car />
);
```

## Ternary Operator

Another way to conditionally render elements is by using a ternary operator.

```js
condition ? true : false
```

We will go back to the goal example.

Example:
Return the MadeGoal component if isGoal is true, otherwise return the MissedGoal component:

```js
function Goal(props) {
  const isGoal = props.isGoal;
  return (
    <>
      { isGoal ? <MadeGoal/> : <MissedGoal/> }
    </>
  );
}

createRoot(document.getElementById('root')).render(
  <Goal isGoal={false} />
);
```

