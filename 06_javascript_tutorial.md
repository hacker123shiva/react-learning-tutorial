# **JavaScript Tutorial 5: DOM Manipulation & Events**

## Understanding the Document Object Model (DOM)

### **Definition:**
The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a webpage as a tree of objects, where each node corresponds to an HTML element.

### **Theory:**
- The DOM allows JavaScript to interact with and modify a webpage dynamically.
- The document is structured hierarchically (like a tree) where `document` is the root.
- DOM elements can be selected, modified, and manipulated using JavaScript.

### **Example & Output:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Example</title>
</head>
<body>
    <h1 id="title">Hello, DOM!</h1>
    <script>
        console.log(document.title); // Outputs: DOM Example
    </script>
</body>
</html>
```
**Output:** Console displays: `DOM Example`

## Selecting Elements

### **Definition:**
Selecting elements in the DOM means retrieving references to specific HTML elements so they can be manipulated.

### **Theory:**
JavaScript provides several methods to select elements in the DOM:
1. **`document.getElementById("id")`** - Selects an element by its ID.
2. **`document.getElementsByClassName("class")`** - Selects elements by class name.
3. **`document.getElementsByTagName("tag")`** - Selects elements by tag name.
4. **`document.querySelector("selector")`** - Selects the first matching element.
5. **`document.querySelectorAll("selector")`** - Selects all matching elements.

### **Example & Output:**
```html
<p id="demo">This is a paragraph.</p>
<button onclick="changeText()">Click Me</button>

<script>
    function changeText() {
        document.getElementById("demo").innerText = "Text Changed!";
    }
</script>
```
**Output:** When the button is clicked, the paragraph text changes to: `Text Changed!`

## Modifying HTML & CSS

### **Definition:**
Modifying HTML & CSS means dynamically changing the content, structure, or styles of a webpage using JavaScript.

### **Theory:**
- `element.innerText` modifies only the text inside an element.
- `element.innerHTML` allows inserting HTML.
- `element.style.property = "value";` modifies CSS properties.
- `element.classList.add/remove/toggle("class-name");` manages CSS classes dynamically.

### **Example & Output:**
```html
<p id="text">Hello, world!</p>
<button onclick="changeStyle()">Change Style</button>

<script>
    function changeStyle() {
        let p = document.getElementById("text");
        p.style.color = "blue";
        p.style.fontSize = "20px";
    }
</script>
```
**Output:** When the button is clicked, the paragraph turns blue with a font size of 20px.


## Event Bubbling

### **Definition:**
Event bubbling is a process where an event starts from the target element and propagates up to its ancestors in the DOM hierarchy.

### **Theory:**
- When an event occurs on an element, it first triggers on that element and then propagates up to its parent elements.
- Event bubbling can be stopped using `event.stopPropagation()`.

### **Example & Output:**
```html
<div id="outer" style="padding: 20px; background-color: lightgray;">
    <div id="inner" style="padding: 20px; background-color: lightblue;">
        <button id="btn">Click Me</button>
    </div>
</div>

<script>
    document.getElementById("outer").addEventListener("click", function() {
        alert("Outer Div Clicked!");
    });

    document.getElementById("inner").addEventListener("click", function() {
        alert("Inner Div Clicked!");
    });

    document.getElementById("btn").addEventListener("click", function(event) {
        alert("Button Clicked!");
        event.stopPropagation(); // Stops event from bubbling up
    });
</script>
```
**Output:** Clicking the button shows `Button Clicked!` alert. Clicking the inner div shows `Inner Div Clicked!`. Clicking the outer div shows `Outer Div Clicked!`.

## Event Delegation

### **Definition:**
Event delegation is a technique where a single event listener is added to a parent element to handle events on dynamically added child elements.

### **Theory:**
- Useful when working with dynamically created elements.
- Reduces the number of event listeners, improving performance.
- Uses `event.target` to determine which child element was clicked.

### **Example & Output:**
```html
<ul id="parent-list">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
<button onclick="addItem()">Add Item</button>

<script>
    document.getElementById("parent-list").addEventListener("click", function(event) {
        if (event.target.tagName === "LI") {
            alert("You clicked " + event.target.innerText);
        }
    });

    function addItem() {
        let li = document.createElement("li");
        li.innerText = "New Item";
        document.getElementById("parent-list").appendChild(li);
    }
</script>
```
**Output:** Clicking any existing or newly added list item shows an alert with its text.

## Creating & Removing Elements

### **Definition:**
JavaScript can dynamically add or remove elements from the DOM to create interactive webpages.

### **Theory:**
- `document.createElement(tagName)` creates a new element.
- `element.appendChild(childNode)` adds a new element inside another.
- `element.removeChild(childNode)` removes an element.

### **Example & Output:**
```html
<button onclick="addItem()">Add Item</button>
<ul id="myList"></ul>

<script>
    function addItem() {
        let li = document.createElement("li");
        li.innerText = "New Item";
        document.getElementById("myList").appendChild(li);
    }
</script>
```
**Output:** Clicking the button adds a new list item dynamically.

## Working with Forms

### **Definition:**
Form handling involves capturing user input and performing validations before submission.

### **Theory:**
- `element.value` retrieves user input.
- `event.preventDefault()` stops form submission.
- JavaScript can check input values and display error messages.

### **Example & Output:**
```html
<form onsubmit="return validateForm()">
    <input type="text" id="name" placeholder="Enter name">
    <button type="submit">Submit</button>
</form>
<script>
    function validateForm() {
        let name = document.getElementById("name").value;
        if (name === "") {
            alert("Name cannot be empty");
            return false;
        }
        return true;
    }
</script>
```
**Output:** If the input is empty, an alert appears saying: `Name cannot be empty.`

## Interview Questions & Answers

### **1. What is the DOM?**
**Answer:** The DOM (Document Object Model) is a programming interface that allows JavaScript to manipulate HTML and CSS dynamically.

### **2. How does `getElementById` differ from `querySelector`?**
**Answer:** `getElementById` selects an element by ID, whereas `querySelector` allows selecting elements using CSS selectors.

### **3. Explain event delegation.**
**Answer:** Event delegation is a technique where a single event listener is added to a parent element instead of multiple child elements to improve efficiency.

### **4. What is event bubbling?**
**Answer:** Event bubbling is a process where an event starts from the target element and propagates up to its ancestors.

### **5. How do you dynamically add an element in JavaScript?**
**Answer:** Using `document.createElement`, `appendChild`, or `insertAdjacentHTML`.

### **6. How do you prevent form submission in JavaScript?**
**Answer:** Using `event.preventDefault()` inside an event listener.

### **6. How do you stop event bubbling?**
**Answer:** By using `event.stopPropagation()` inside the event handler.

### **7. Why is event delegation useful?**
**Answer:** It improves performance by reducing the number of event listeners and allows handling dynamically added elements.


 