<div align="center">
  <h1> React Submit Forms</h1>
 
</div>



# React Submit Forms

You can control the submit action by adding an event handler in the onSubmit attribute for the <form>:
Example:
Add a submit button and an event handler in the onSubmit attribute:


```js
import { useState } from 'react';
import { createRoot } from 'react-dom/client';

function MyForm() {
  const [name, setName] = useState("");

  function handleChange(e) {
    setName(e.target.value);
  }

  function handleSubmit(e) {
    e.preventDefault();
    alert(name);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>Enter your name:
        <input
          type="text" 
          value={name}
          onChange={handleChange}
        />
      </label>
      <input type="submit" />
    </form>
  )
}

createRoot(document.getElementById('root')).render(
  <MyForm />
);
```


