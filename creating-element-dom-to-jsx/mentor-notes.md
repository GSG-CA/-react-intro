# Creating elements, from DOM to JSX

Task: Use the DOM, `React.createElement()` and JSX methods to create a div, including an h1 and a paragraph.
The h1 should have a class of red and onclick function console logging "Hello World".

### 1. Using DOM

```js
const root = document.getElementById("root");
const divDOM = document.createElement("div");
const h1DOM = document.createElement("h1");
const pDOM = document.createElement("p");

h1DOM.innerText = "Hello World";
h1DOM.classList.add("red");
h1DOM.addEventListener("click", () => console.log("Hello world"));

pDOM.innerText = "I am just a text";

divDOM.appendChild(h1DOM);
divDOM.appendChild(pDOM);
root.appendChild(divDOM);
```

### 2. Using `React.createElement()`

This method takes the element name, attributes, and children.

```js
const h1React = React.createElement(
  "h1",
  {
    className: "red",
    onClick: () => {
      console.log("Hello world");
    }
  },
  "Hello World"
);

const pReact = React.createElement("p", null, "I am just a text");
const divReact = React.createElement("div", {}, h1React, pReact);

ReactDOM.render(divReact, document.getElementById("root"));
```

### 3. Using JSX

```js
const jsx = (
  <div>
    <h1
      className="red"
      onClick={() => {
        console.log("Hello world");
      }}
    >
      Hello world
    </h1>
    <p>I am just a text</p>
  </div>
);

ReactDOM.render(jsx, document.getElementById("root"));
```
