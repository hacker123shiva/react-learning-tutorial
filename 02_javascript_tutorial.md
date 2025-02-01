# **JavaScript Tutorial 2: Control Flow and Loops**

## **1. Conditional Statements**

Conditional statements allow us to execute different code based on conditions.

### **1.1 if Statement**

The `if` statement executes a block of code only if a specified condition is `true`.

#### **Syntax:**

```javascript
if (condition) {
  // Code to execute if condition is true
}
```

#### **Example:**

```javascript
let age = 18;
if (age >= 18) {
  console.log('You are eligible to vote.');
}
```

### **1.2 if-else Statement**

The `if-else` statement provides an alternative block of code if the condition is `false`.

#### **Syntax:**

```javascript
if (condition) {
  // Code to execute if condition is true
} else {
  // Code to execute if condition is false
}
```

#### **Example:**

```javascript
let number = 10;
if (number % 2 === 0) {
  console.log('Even number');
} else {
  console.log('Odd number');
}
```

### **1.3 if-else if-else Statement**

The `if-else if-else` statement allows us to check multiple conditions sequentially.

#### **Syntax:**

```javascript
if (condition1) {
  // Code to execute if condition1 is true
} else if (condition2) {
  // Code to execute if condition2 is true
} else {
  // Code to execute if none of the conditions are true
}
```

#### **Example:**

```javascript
let score = 85;
if (score >= 90) {
  console.log('Grade: A');
} else if (score >= 80) {
  console.log('Grade: B');
} else if (score >= 70) {
  console.log('Grade: C');
} else {
  console.log('Fail');
}
```

### **1.4 switch Statement**

The `switch` statement evaluates an expression and executes the corresponding `case` block.

#### **Syntax:**

```javascript
switch (expression) {
  case value1:
    // Code to execute if expression === value1
    break;
  case value2:
    // Code to execute if expression === value2
    break;
  default:
  // Code to execute if no case matches
}
```

#### **Example:**

```javascript
let day = 'Monday';
switch (day) {
  case 'Monday':
    console.log('Start of the week');
    break;
  case 'Friday':
    console.log('Weekend is near');
    break;
  default:
    console.log('Another day');
}
```

---

## **2. Loops in JavaScript**

Loops allow us to execute a block of code multiple times.

### **2.1 for Loop**

The `for` loop runs a block of code a specified number of times.

#### **Syntax:**

```javascript
for (initialization; condition; increment / decrement) {
  // Code to execute
}
```

#### **Example:**

```javascript
for (let i = 1; i <= 5; i++) {
  console.log('Iteration: ' + i);
}
```

### **2.2 while Loop**

The `while` loop runs as long as the specified condition is `true`.

#### **Syntax:**

```javascript
while (condition) {
  // Code to execute
}
```

#### **Example:**

```javascript
let count = 1;
while (count <= 5) {
  console.log('Count: ' + count);
  count++;
}
```

### **2.3 do-while Loop**

The `do-while` loop runs at least once before checking the condition.

#### **Syntax:**

```javascript
do {
  // Code to execute
} while (condition);
```

#### **Example:**

```javascript
let num = 1;
do {
  console.log('Number: ' + num);
  num++;
} while (num <= 5);
```

---

## **3. Break and Continue Statements**

### **3.1 break Statement**

The `break` statement exits a loop immediately.

#### **Example:**

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    break;
  }
  console.log('Iteration: ' + i);
}
```

### **3.2 continue Statement**

The `continue` statement skips the current iteration and moves to the next.

#### **Example:**

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log('Iteration: ' + i);
}
```

---

## **4. Exception Handling in JavaScript**

Exception handling allows us to manage errors gracefully.

### **4.1 try-catch Block**

The `try` block contains the code that may cause an error, and the `catch` block handles the error.

#### **Syntax:**

```javascript
try {
  // Code that may throw an error
} catch (error) {
  // Code to handle the error
}
```

#### **Example:**

```javascript
try {
  let result = 10 / 0;
  console.log(result);
} catch (error) {
  console.log('An error occurred: ' + error);
}
```

### **4.2 finally Block**

The `finally` block executes after `try-catch`, regardless of the outcome.

#### **Example:**

```javascript
try {
  let value = undefinedVariable; // This will throw an error
} catch (error) {
  console.log('Error caught: ' + error.message);
} finally {
  console.log('Execution completed.');
}
```

### **4.3 throw Statement**

The `throw` statement allows us to manually generate an error.

#### **Example:**

```javascript
function divide(a, b) {
  if (b === 0) {
    throw new Error('Division by zero is not allowed.');
  }
  return a / b;
}

try {
  console.log(divide(10, 0));
} catch (error) {
  console.log('Caught an error: ' + error.message);
}
```

---

### **Conclusion**

This tutorial covered control flow, loops, and exception handling in JavaScript. Understanding these concepts helps in writing efficient, error-free programs. Keep practicing with different scenarios to strengthen your knowledge!
