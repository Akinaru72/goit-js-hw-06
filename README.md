# Homework #6

## Instructions

1. Create a repository **`goit-js-hw-06`** and clone it to your computer.
2. In the `goit-js-hw-06` folder, create the project structure as shown in the image below.

![Project preview](assets/goit-js-06.jpg)

> **Attention!** The names of files and folders, as well as their nesting structure, must match the specified schema. Otherwise, the work will not be accepted.

3. Read each task and complete it in the corresponding file.
4. Make sure your code is formatted using **Prettier**, and there are no errors or warnings in the console when opening the live page of the task.
5. Submit your homework for review.

**Submission format:**  
The homework must include two links:

- to the source files,
- to the live page on GitHub Pages.

---

## Task 1. User Account

Complete this task in the file **`task-1.js`**.

Before leaving, the developer broke the original code for managing user accounts in our food delivery service.  
Perform a **refactoring of the `customer` object's methods**, adding the missing `this` references when accessing the object’s properties.

Use this starter code and perform the refactoring. Method calls have been added after the object declaration.  
The console will display the results of their execution. Please do not change anything there.

```javascript
const customer = {
  username: "Mango",
  balance: 24000,
  discount: 0.1,
  orders: ["Burger", "Pizza", "Salad"],

  // Change code below this line
  getBalance() {
    return this.balance;
  },
  getDiscount() {
    return this.discount;
  },
  setDiscount(value) {
    this.discount = value;
  },
  getOrders() {
    return this.orders;
  },
  addOrder(cost, order) {
    this.balance -= cost - cost * this.discount;
    this.orders.push(order);
  },
  // Change code above this line
};

customer.setDiscount(0.15);
console.log(customer.getDiscount()); // 0.15
customer.addOrder(5000, "Steak");
console.log(customer.getBalance()); // 19750
console.log(customer.getOrders()); // ["Burger", "Pizza", "Salad", "Steak"]
```

Leave this code for mentor review.

---

What the mentor will pay attention to during the review:

- The variable `customer` is declared
- The value of the variable `customer` is an object with properties and methods
- Calling `customer.getDiscount()` returns the current value of the `discount` property
- Calling `customer.setDiscount(0.15)` updates the value of the `discount` property
- Calling `customer.getBalance()` returns the current value of the `balance` property
- Calling `customer.getOrders()` returns the current value of the `orders` property
- Calling `customer.addOrder(5000, "Steak")` adds `"Steak"` to the array of the `orders` property and updates the balance
- The `getBalance` method of the `customer` object uses `this`
- The `getDiscount` method of the `customer` object uses `this`
- The `setDiscount` method of the `customer` object uses `this`
- The `getOrders` method of the `customer` object uses `this`
- The `addOrder` method of the `customer` object uses `this`

---

## Task 2. Storage

Complete this task in the file `task-2.js`.

Create a class `Storage` that will create objects for managing a product warehouse. The class expects only one argument — an initial array of products, which is stored in the created object in the private property `items`.

Declare the following class methods:

- `getItems()` — returns the array of current products in the private property `items`
- `addItem(newItem)` — takes a new product `newItem` and adds it to the array of products in the private property `items` of the object
- `removeItem(itemToRemove)` — takes a string with the name of the product `itemToRemove` and removes it from the array of products in the private property `items` of the object

Take the code below with the instance initialization and method calls and place it after the class declaration to check correctness. The console will display the results of their execution. Please do not change anything.

```javascript
const storage = new Storage(["Nanitoids", "Prolonger", "Antigravitator"]);
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator"]

storage.addItem("Droid");
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator", "Droid"]

storage.removeItem("Prolonger");
console.log(storage.getItems()); // ["Nanitoids", "Antigravitator", "Droid"]

storage.removeItem("Scaner");
console.log(storage.getItems()); // ["Nanitoids", "Antigravitator", "Droid"]
```

Leave this code for mentor review.

---

What the mentor will pay attention to during the review:

- The class `Storage` is declared
- In the class `Storage`, the method `getItems` is declared
- In the class `Storage`, the method `addItem` is declared
- In the class `Storage`, the method `removeItem` is declared
- The property `items` in the class `Storage` is declared as private
- The method `getItems` returns the value of the private property `items` of the class instance that calls it
- The method `addItem` changes the value of the private property `items` of the class instance that calls it
- The method `removeItem` changes the value of the private property `items` of the class instance that calls it
- As a result of calling `new Storage(["Nanitoids", "Prolonger", "Antigravitator"])`, the value of the variable `storage` is an object
- The object `storage` does not have a public property `items`
- The first call to `storage.getItems()` immediately after instance initialization returns the array `["Nanitoids", "Prolonger", "Antigravitator"]`
- The second call to `storage.getItems()` after calling `storage.addItem("Droid")` returns the array `["Nanitoids", "Prolonger", "Antigravitator", "Droid"]`
- The third call to `storage.getItems()` after calling `storage.removeItem("Prolonger")` returns the array `["Nanitoids", "Antigravitator", "Droid"]`
- The fourth call to `storage.getItems()` after calling `storage.removeItem("Scaner")` returns the array `["Nanitoids", "Antigravitator", "Droid"]`

---

## Task 3. String Constructor

Complete this task in the file `task-3.js`.

Write a class `StringBuilder` that takes one parameter `initialValue` — an arbitrary string that is stored in the private property `value` of the object being created.

Declare the following class methods:

- `getValue()` — returns the current value of the private property `value`
- `padEnd(str)` — takes the parameter `str` (string) and adds it to the end of the private property `value` of the object that calls this method
- `padStart(str)` — takes the parameter `str` (string) and adds it to the beginning of the private property `value` of the object that calls this method
- `padBoth(str)` — takes the parameter `str` (string) and adds it to both the beginning and the end of the private property `value` of the object that calls this method

Take the code below with instance initialization and method calls and place it after the class declaration to check correctness. The console will display the results of their execution. Please do not change anything.

```javascript
const builder = new StringBuilder(".");
console.log(builder.getValue()); // "."
builder.padStart("^");
console.log(builder.getValue()); // "^."
builder.padEnd("^");
console.log(builder.getValue()); // "^.^"
builder.padBoth("=");
console.log(builder.getValue()); // "=^.^="
```

Leave this code for mentor review.

---

What the mentor will pay attention to during the review:

- The class `StringBuilder` is declared
- The property `value` in the class `StringBuilder` is declared as private
- In the class `StringBuilder`, the method `getValue` is declared
- The method `getValue` returns the value of the private property `value` of the class instance that calls it
- In the class `StringBuilder`, the method `padEnd` is declared
- The method `padEnd` changes the value of the private property `value` of the class instance that calls it
- In the class `StringBuilder`, the method `padStart` is declared
- The method `padStart` changes the private property `value` of the class instance that calls it
- In the class `StringBuilder`, the method `padBoth` is declared
- The method `padBoth` changes the value of the private property `value` of the class instance that calls it
- As a result of calling `new StringBuilder(".")`, the value of the variable

---

**Live page: [GitHub Pages](https://akinaru72.github.io/goit-js-hw-05/)**
