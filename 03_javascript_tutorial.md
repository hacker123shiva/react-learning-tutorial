# **JavaScript Tutorial 3: Functions and Scope**

## **1. Functions in JavaScript**
Functions are reusable blocks of code designed to perform a specific task. They enhance code modularity and reusability, making programs more structured and maintainable. JavaScript functions allow the execution of the same logic multiple times without redundancy.

Functions can be categorized into various types, including function declarations, expressions, and arrow functions. They also accept parameters and return values that allow dynamic data processing.

### **1.1 Function Declaration**
A function declaration defines a named function that can be called anywhere in the script, thanks to JavaScript’s hoisting mechanism. This means the function can be invoked even before it is defined in the code.

#### **Syntax:**
```javascript
function functionName(parameters) {
    // Code to execute
    return result; // (optional)
}
```
#### **Example:**
```javascript
function greet(name) {
    return "Hello, " + name + "!";
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

### **1.2 Function Expression**
A function expression assigns an anonymous function to a variable. Unlike function declarations, function expressions are not hoisted, meaning they cannot be called before they are defined.

#### **Example:**
```javascript
const greet = function(name) {
    return "Hello, " + name + "!";
};
console.log(greet("Alice")); // Output: Hello, Alice!
```

---

## **2. Arrow Functions**
Arrow functions provide a more concise syntax for writing functions. They automatically bind `this` from their surrounding context, making them especially useful in object-oriented programming and event handlers.

Arrow functions do not have their own `this`, `arguments`, `super`, or `new.target`, making them different from regular functions. They are particularly useful for callback functions and array manipulations.

#### **Example:**
```javascript
const add = (a, b) => a + b;
console.log(add(5, 3)); // Output: 8
```

---

## **3. Function Parameters and Arguments**
JavaScript allows default parameters, enabling a function to be invoked without passing all expected arguments.

#### **Example:**
```javascript
function sum(a, b = 5) {
    return a + b;
}
console.log(sum(3)); // Output: 8, as b defaults to 5
```

---

## **4. Return Statements**
The `return` statement stops function execution and specifies the value to be returned to the function caller.

#### **Example:**
```javascript
function multiply(a, b) {
    return a * b;
}
console.log(multiply(4, 5)); // Output: 20
```

---

## **5. Callback Functions**
A callback function is a function passed as an argument to another function, allowing for greater flexibility in asynchronous operations like API calls, event handling, and timers.

#### **Example:**
```javascript
function processUser(name, callback) {
    console.log("Processing user: " + name);
    callback();
}
function welcome() {
    console.log("Welcome to the system!");
}
processUser("Alice", welcome);
// Output: 
// Processing user: Alice
// Welcome to the system!
```

---

## **6. Closures**
A closure is a function that retains access to its outer function’s variables even after the outer function has finished execution.

#### **Example:**
```javascript
function counter() {
    let count = 0;
    return function() {
        count++;
        console.log(count);
    };
}
const increment = counter();
increment(); // Output: 1
increment(); // Output: 2
```

---

## **7. Immediately Invoked Function Expressions (IIFE)**
An IIFE is a function that executes immediately after its definition.

#### **Examples:**
```javascript
// Basic IIFE
(function() {
    console.log("IIFE executed!");
})();
// Output: IIFE executed!

// IIFE with Parameters
(function(name) {
    console.log("Hello, " + name + "!");
})("Alice");
// Output: Hello, Alice!

// IIFE for Private Scope
const counter = (function() {
    let count = 0;
    return {
        increment: function() {
            count++;
            console.log(count);
        },
        decrement: function() {
            count--;
            console.log(count);
        }
    };
})();
counter.increment(); // Output: 1
counter.increment(); // Output: 2
counter.decrement(); // Output: 1
```

---

## **8. Scope in JavaScript**
Scope determines where variables and functions are accessible in a JavaScript program.

#### **Example:**
```javascript
let globalVar = "I am global";
function testScope() {
    let localVar = "I am local";
    console.log(globalVar);
}
testScope(); // Output: I am global
console.log(localVar); // Error: localVar is not defined
```

---

## **9. Hoisting**
Hoisting is JavaScript’s default behavior of moving declarations to the top before execution.

#### **Example:**
```javascript
console.log(greet());
function greet() {
    return "Hello!";
}
// Output: Hello!
```

However, the following would cause an error:
```javascript
console.log(x);
let x = 10; // ReferenceError: Cannot access 'x' before initialization
```

---

## **Interview Questions and Answers Summary**
1. **What is the difference between function declaration and function expression?**
   - Function declarations are hoisted, function expressions are not.

2. **How do arrow functions differ from regular functions?**
   - They do not have their own `this` and cannot be used as constructors.

3. **What is a closure in JavaScript?**
   - A function that retains access to variables from its outer scope.

4. **Why use an IIFE?**
   - To execute code immediately and avoid polluting the global scope.

5. **What is hoisting?**
   - JavaScript moves function and variable declarations to the top before execution.

By mastering these concepts, you’ll be able to handle functions and scope efficiently and confidently explain them in interviews!

