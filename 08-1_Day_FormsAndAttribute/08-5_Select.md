<div align="center">
  <h1> React Forms - Select</h1>
 
</div>



# React Forms - Select

## Select

A drop down list, or a select box, in React is also a bit different from HTML.

In HTML, the selected value in the drop down list is defined with the selected attribute:

HTML:
```html
<select>
  <option value="Ford">Ford</option>
  <option value="Volvo" selected>Volvo</option>
  <option value="Fiat">Fiat</option>
</select>
```

In React, the selected value is defined with a value attribute on the select tag:

Example:
React uses the value attribute to control the select box:

```js
function MyForm() {
  const [myCar, setMyCar] = useState("Volvo");

  const handleChange = (event) => {
    setMyCar(event.target.value)
  }

  return (
    <form>
      <select value={myCar} onChange={handleChange}>
        <option value="Ford">Ford</option>
        <option value="Volvo">Volvo</option>
        <option value="Fiat">Fiat</option>
      </select>
    </form>
  )
}

```

By making these changes to the <select> element, React is able to handle it as any other input element.




