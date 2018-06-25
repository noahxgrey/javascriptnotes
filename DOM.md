# DOM
#### a tree like representation of the contents of a web page - a tree of "nodes" with different relationships depending on how they're arranged in the HTML document. "Family Tree" When working with DOM, you use the "selectors" to target nodes you want to work with. Can use a combination of CSS - style selectors and relationship properties to target the nodes you want. 

### DOM Methods
#### When your HTML code is parsled by a web browser, it is converted to the DOM as was mentioned above. These nodes are objects that have many properties and methods attached to them. These properties and methods are the primary toold we are going to use to manipulate our webpage with JavasScript.

#### QuerySelectors
```javascript
element.querySelector(selector) // returns reference to the first match of (). You can select multiple. add "all" at the end of Selector
```
#### Element Creation
```javascript
document.createElement(tagName[options]) // creates a new element of tag type tagName. [options] means you can add some optional parameters to the function. Don't worry about that ATM

const div = document.createElement("div"); // this does not put new element into DOM - creates it in memory so that you can manipulate the element (styles, ids, text, etc) before placing it on the page.
// place element into DOM by:
parentNode.appendChild(childNode) // appends childNode as last child of parentNode
parentNode.insertBefore(newNode, referenceNode) // inserts newNode into parentNode before referenceNode
```

#### Remove Elements
```javascript
parentNode.removeChild(child) // removes child from parentNode
```

#### Altering Elements
```javascript
const div = document.createElement("div"); // creates a new div referenced in the variable "div"
div.style.color = "blue";
div.style.cssText = "color: blue; background: white";
div.setAttribute("style", "color: blue ; background: white");
```

#### Editing Attributes
```javascript
div.setAttribute("id", "theDiv"); // if id exists update it to "theDiv" else create an id with the value "theDiv"
div.getAttribute("id"); // returns value of specified attribute
div.removeAttribute("id"); // removes specified attribute
```

#### Working with classes
```javascript
div.classList.add("new"); // adds class "new" to your new div
div.classList.remove("new"); // removes "new" class from div
div.classList.toggle("active"); // if div doesn't have a class "active" then add it, or if it does, remove it. (It is often standard (and more clean) to toggle a css style rather than adding and removing inline CSS)
```

#### Adding text content
```javascript
div.textContent = "Hello world!"; // creates a text node containing "Hello World" and inserts into div
```

#### Adding HTML content
```javascript
div.innerHTML = "<span> Hello World! </span>"; // renders the HTML inside div
//text content is preferable, innerHTML should be used sparingly
```

## JavaScript does not alter your HTML, but the DOM - your HTML file will look the same, but the JavaScript changes what the broswer renders.

### Events
#### Events are how you make magic happen on your pages. Events are actions that occur on your webpage such as mouse-clicks, & using javascript we can make our webpage listen and react to these events.
#### # ways to go about this: you can attach functions attributes directly on your HTML elements, you can se the "on_event_" property on the DOM object in your JavaScript, or you can attach event listeners to the nodes in your JavaScript. Event listeners are the preferred method, but you will regulary see the others in use.

#### Event Listener Method (3)
```html
<button id = "btn">Click Me Too</button>
```
```javascript
let btn = document.querySelector("#btn");
btn.addEventListener("click" () => {
    alert("Hello World");
});
// We maintain separation of concerns, and we also allow multiple event listeners if need arise.
```
