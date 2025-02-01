# **JavaScript Tutorial 1: Basics of JavaScript**

## **Introduction to JavaScript**

### **What is JavaScript?**
JavaScript (JS) is a versatile, high-level programming language primarily used for web development. It allows developers to create interactive web pages, manipulate HTML and CSS, and build complex applications.

### **Why Learn JavaScript?**
- It is the most popular programming language for web development.
- Works on all modern browsers.
- Essential for front-end and back-end development (Node.js).
- Used in mobile and desktop application development.

### **How JavaScript Works in Browsers**
JavaScript runs in the browser as a scripting language. The browser has a built-in JavaScript engine that interprets and executes JavaScript code.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Example</title>
    <script>
        console.log("Hello, JavaScript!");
    </script>
</head>
<body>
    <h1>JavaScript Basics</h1>
</body>
</html>
```

---
## **Setting Up the Environment**

### **Using the Browser Console**
1. Open any modern web browser (Chrome, Firefox, Edge, Safari).
2. Press `F12` or `Ctrl + Shift + I` to open Developer Tools.
3. Navigate to the "Console" tab.
4. Type `console.log("Hello, JavaScript!");` and press Enter.

### **Using Node.js**
1. Download and install [Node.js](https://nodejs.org/).
2. Open the terminal or command prompt.
3. Type `node` to enter the interactive mode.
4. Run JavaScript commands like `console.log("Hello, Node.js!");`

---
## **Variables in JavaScript**

### **What are Variables?**
Variables store data values that can be used and manipulated throughout a program.

### **Declaring Variables**
JavaScript provides three ways to declare variables:

1. **var** (old way, function-scoped)
2. **let** (new way, block-scoped)
3. **const** (constant, cannot be reassigned)

#### **Example:**
```javascript
var name = "Alice"; // Old way
let age = 25; // Modern way
const country = "USA"; // Constant value

console.log(name, age, country);
```

#### **Differences:**
| Feature | var | let | const |
|---------|-----|-----|-------|
| Scope | Function | Block | Block |
| Reassignment | Allowed | Allowed | Not Allowed |
| Hoisting | Yes (initialized as `undefined`) | Yes (not initialized) | Yes (not initialized) |

---
## **Data Types in JavaScript**
JavaScript has **primitive** and **non-primitive** data types.

### **Primitive Data Types**
1. **String** - Represents text values.
2. **Number** - Represents both integer and floating-point numbers.
3. **Boolean** - `true` or `false` values.
4. **Null** - Represents an intentional empty value.
5. **Undefined** - Represents a variable that has been declared but not assigned a value.
6. **Symbol** - Unique and immutable values.
7. **BigInt** - Handles very large numbers.

#### **Example:**
```javascript
let name = "Alice"; // String
let age = 30; // Number
let isStudent = false; // Boolean
let salary = null; // Null
let country; // Undefined
let uniqueID = Symbol("id"); // Symbol
let bigNumber = 123456789012345678901234567890n; // BigInt

console.log(name, age, isStudent, salary, country, uniqueID, bigNumber);
```

### **Non-Primitive Data Types**
- Objects
- Arrays
- Functions

---
## **Operators in JavaScript**
JavaScript supports various types of operators:

### **1. Arithmetic Operators**
Used to perform mathematical operations.
```javascript
let a = 10, b = 5;
console.log(a + b); // Addition
console.log(a - b); // Subtraction
console.log(a * b); // Multiplication
console.log(a / b); // Division
console.log(a % b); // Modulus
console.log(a ** b); // Exponentiation
```

### **2. Comparison Operators**
Used to compare two values.
```javascript
console.log(10 > 5); // true
console.log(10 < 5); // false
console.log(10 == "10"); // true (loose equality)
console.log(10 === "10"); // false (strict equality)
console.log(10 != 5); // true
console.log(10 !== "10"); // true
```

### **3. Logical Operators**
Used to combine boolean expressions.
```javascript
console.log(true && false); // false (AND)
console.log(true || false); // true (OR)
console.log(!true); // false (NOT)
```

### **4. Assignment Operators**
Used to assign values to variables.
```javascript
let x = 10;
x += 5; // x = x + 5
x -= 3; // x = x - 3
x *= 2; // x = x * 2
x /= 2; // x = x / 2
console.log(x);
```

### **5. Bitwise Operators**
Used to perform bitwise operations.
```javascript
console.log(5 & 1); // AND
console.log(5 | 1); // OR
console.log(5 ^ 1); // XOR
console.log(~5); // NOT
console.log(5 << 1); // Left Shift
console.log(5 >> 1); // Right Shift
```

### **6. Ternary Operator**
A shorthand for `if-else` conditions.
```javascript
let age = 18;
let status = (age >= 18) ? "Adult" : "Minor";
console.log(status); // Adult
```

---
## **Type Conversion & Type Coercion**

### **Type Conversion** (Explicit)
Manually converting one data type to another.
```javascript
let num = "42";
console.log(Number(num)); // Converts to number
console.log(String(42)); // Converts to string
console.log(Boolean(1)); // Converts to true
```

### **Type Coercion** (Implicit)
JavaScript automatically converts data types.
```javascript
console.log("5" + 2); // "52" (string concatenation)
console.log("5" - 2); // 3 (numeric conversion)
```

---
### **Conclusion**
This tutorial covered the foundational concepts of JavaScript, including variables, data types, operators, and type conversion. Mastering these basics will help in understanding more advanced JavaScript topics in the upcoming lessons.

