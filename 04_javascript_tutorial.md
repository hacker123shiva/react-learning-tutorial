# **JavaScript Tutorial 4: Objects and Arrays**

## **1. Objects in JavaScript**

Objects in JavaScript are collections of properties, where each property is a key-value pair. Objects allow us to store, manipulate, and retrieve data in a structured way. Unlike primitive data types (such as numbers and strings), objects can hold multiple values.

### **1.1 Object Creation and Properties**
Objects can be created in multiple ways: using object literals, constructors, or the `Object.create` method.

#### **Example 1: Object Literal**
This is the most common way to create an object.
```javascript
const person = {
    name: "Alice",
    age: 25,
    city: "New York"
};
console.log(person.name); // Output: Alice
console.log(person["city"]); // Output: New York
```

#### **Example 2: Object Constructor**
```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}
const person1 = new Person("Bob", 30);
console.log(person1.name); // Output: Bob
```

#### **Example 3: Object.create Method**
```javascript
const personPrototype = {
    greet: function() {
        console.log("Hello, " + this.name);
    }
};
const person2 = Object.create(personPrototype);
person2.name = "Charlie";
person2.greet(); // Output: Hello, Charlie
```

### **1.2 Object Methods and the `this` Keyword**
Objects can have functions as properties. These are called methods. The `this` keyword refers to the object that the method belongs to.

#### **Example:**
```javascript
const car = {
    brand: "Toyota",
    model: "Corolla",
    getCarInfo: function() {
        return this.brand + " " + this.model;
    }
};
console.log(car.getCarInfo()); // Output: Toyota Corolla
```

### **1.3 Prototypes and Inheritance**
JavaScript is prototype-based, meaning objects can inherit properties and methods from other objects.

#### **Example:**
```javascript
function Animal(name) {
    this.name = name;
}
Animal.prototype.speak = function() {
    return this.name + " makes a sound";
};
const dog = new Animal("Dog");
console.log(dog.speak()); // Output: Dog makes a sound
```

### **1.4 Object Destructuring**
Destructuring allows us to extract values from objects easily.

#### **Example:**
```javascript
const student = { name: "Charlie", grade: "A" };
const { name, grade } = student;
console.log(name); // Output: Charlie
console.log(grade); // Output: A
```

---

## **2. Arrays in JavaScript**
An array is a collection of ordered elements that can store multiple values. Arrays are dynamic and can hold different data types.

### **2.1 Creating and Accessing Arrays**
#### **Example:**
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
console.log(fruits[0]); // Output: Apple
console.log(fruits.length); // Output: 3
```

### **2.2 Array Methods**
Arrays come with built-in methods for adding, removing, and manipulating elements.

#### **Example: push and pop**
```javascript
let numbers = [1, 2, 3];
numbers.push(4); // Adds to end
console.log(numbers); // Output: [1, 2, 3, 4]
numbers.pop(); // Removes last element
console.log(numbers); // Output: [1, 2, 3]
```

#### **Example: shift and unshift**
```javascript
numbers.unshift(0); // Adds to beginning
console.log(numbers); // Output: [0, 1, 2, 3]
numbers.shift(); // Removes first element
console.log(numbers); // Output: [1, 2, 3]
```

### **2.3 Iteration over Arrays**

#### **Example: forEach**
```javascript
let colors = ["red", "blue", "green"];
colors.forEach(color => console.log(color));
```

#### **Example: map**
```javascript
let numbersDoubled = numbers.map(num => num * 2);
console.log(numbersDoubled); // Output: [2, 4, 6]
```

#### **Example: filter**
```javascript
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2]
```

#### **Example: reduce**
```javascript
let sum = numbers.reduce((total, num) => total + num, 0);
console.log(sum); // Output: 6
```

### **2.4 Array Destructuring**
Array destructuring allows quick extraction of values from an array.

#### **Example:**
```javascript
const fruitsArray = ["Apple", "Banana", "Cherry"];
const [first, second] = fruitsArray;
console.log(first); // Output: Apple
console.log(second); // Output: Banana
```

---

## **Interview Questions and Answers**

1. **What is the difference between an object and an array in JavaScript?**
   - Objects store key-value pairs, while arrays store ordered elements.

2. **What is prototypal inheritance?**
   - Objects in JavaScript inherit properties and methods from other objects via prototypes.

3. **What is the purpose of the `this` keyword in JavaScript?**
   - `this` refers to the object that is executing the function.

4. **How do you iterate over an array in JavaScript?**
   - Using loops (`for`, `forEach`) or array methods like `map`, `filter`, and `reduce`.

5. **What is object destructuring in JavaScript?**
   - A syntax that allows extracting properties from an object into separate variables.

By mastering objects and arrays, you’ll gain essential skills for handling data in JavaScript applications!

