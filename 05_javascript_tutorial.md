# **JavaScript Tutorial 5: Asynchronous JavaScript**

## **1. Synchronous vs Asynchronous Programming**

### **Synchronous Programming**
Synchronous programming means the code is executed line by line, and each operation waits for the previous one to complete before executing.

#### **Example:**
```javascript
console.log("Start");
console.log("Middle");
console.log("End");
```
**Output:**
```
Start
Middle
End
```

### **Asynchronous Programming**
In asynchronous programming, tasks run independently, and operations do not block the execution of other tasks. JavaScript achieves this using callbacks, promises, and async/await.

#### **Example:**
```javascript
console.log("Start");
setTimeout(() => {
    console.log("Asynchronous Task");
}, 2000);
console.log("End");
```
**Output:**
```
Start
End
Asynchronous Task (after 2 seconds)
```

---

## **2. Callbacks**
A callback is a function passed as an argument to another function, which gets executed later.

#### **Example:**
```javascript
function greet(name, callback) {
    console.log("Hello, " + name);
    callback();
}
function done() {
    console.log("Callback function executed");
}
greet("Alice", done);
```
**Output:**
```
Hello, Alice
Callback function executed
```

---

## **3. Promises**
Promises are an improvement over callbacks for handling asynchronous operations.

### **States of a Promise:**
- **Pending**: Initial state, neither fulfilled nor rejected.
- **Fulfilled**: The operation was completed successfully.
- **Rejected**: The operation failed.

#### **Creating a Promise:**
```javascript
const myPromise = new Promise((resolve, reject) => {
    let success = true;
    setTimeout(() => {
        if (success) {
            resolve("Task completed");
        } else {
            reject("Task failed");
        }
    }, 2000);
});

myPromise
    .then(result => {
        console.log(result);
        return "Next step";
    })
    .then(nextResult => {
        console.log(nextResult);
    })
    .catch(error => console.log(error))
    .finally(() => console.log("Promise execution completed"));
```
**Output:**
```
Task completed (after 2 seconds)
Next step
Promise execution completed
```

#### **Using Callbacks inside `.then()`**
```javascript
function asyncTask() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Task completed");
        }, 2000);
    });
}

asyncTask()
    .then(result => {
        console.log(result);
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve("Second task completed");
            }, 2000);
        });
    })
    .then(secondResult => {
        console.log(secondResult);
    });
```
**Output:**
```
Task completed (after 2 seconds)
Second task completed (after 4 seconds in total)
```

---

## **4. Async/Await**
Async/Await is a cleaner way to handle promises and makes asynchronous code look synchronous.

#### **Example:**
```javascript
async function fetchData() {
    try {
        let response = await new Promise(resolve => setTimeout(() => resolve("Data fetched"), 2000));
        console.log(response);
    } catch (error) {
        console.log("Error occurred", error);
    }
}
fetchData();
```
**Output:**
```
Data fetched (after 2 seconds)
```

---

## **5. Event Loop and Microtasks**
The event loop allows JavaScript to handle asynchronous tasks efficiently.

### **Order of Execution:**
1. Execute synchronous code.
2. Process microtasks (e.g., promise callbacks).
3. Process macrotasks (e.g., setTimeout callbacks).

#### **Example:**
```javascript
console.log("Start");
setTimeout(() => console.log("setTimeout executed"), 0);
Promise.resolve().then(() => console.log("Promise resolved"));
console.log("End");
```
**Output:**
```
Start
End
Promise resolved
setTimeout executed
```

---

## **6. Error Handling in Async Code**
Handling errors in asynchronous operations ensures smooth execution and better debugging.

### **Using `.catch()` in Promises:**
```javascript
myPromise
    .then(result => console.log(result))
    .catch(error => console.log("Caught error:", error));
```
**Output:**
```
Caught error: Task failed
```

### **Using `try-catch` in Async/Await:**
```javascript
async function fetchData() {
    try {
        let response = await fetch("invalid-url");
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.log("Error fetching data:", error);
    }
}
fetchData();
```
**Output:**
```
Error fetching data: TypeError: Failed to fetch
```

---

## **Interview Questions and Answers**

1. **What is the difference between synchronous and asynchronous programming?**
   - Synchronous programming executes tasks sequentially, while asynchronous programming allows tasks to run independently.

2. **What are callbacks in JavaScript?**
   - A function passed as an argument to another function to be executed later.

3. **What are promises in JavaScript?**
   - Promises represent a future value and allow handling asynchronous tasks more efficiently.

4. **What is the difference between `.then()` and `async/await`?**
   - `.then()` handles promises using callbacks, while `async/await` makes asynchronous code look synchronous.

5. **What is the event loop in JavaScript?**
   - The event loop is responsible for handling asynchronous tasks and managing execution order.

By mastering asynchronous JavaScript, you’ll be able to write efficient, non-blocking code and confidently explain concepts in interviews!

