---
title: Have You Heard of Hoisting?
description: Understand how hoisting works, its implications on scopes, and use cases.
slug: have-you-heard-of-hoisting
date: 2025-01-09 00:00:00+0000
tags:
  - Javascript
  - frontend
categories:
  - Programming
  - front-End
  - Javascript
---


Have you ever come across code where a variable seemed to be used before its declaration and felt confused about what was happening? That’s **hoisting**  in JavaScript!
 Let’s explore this basic concept, how scopes matter to it, and its implications.


---

## **Scope: A Context for Hoisting**
Before we talk about what **hoisting** is, we first need to understand a bit more about scopes. In JavaScript, the scope is the context where a variable can be accessed or used.
There are three main types of scope:

## **Types of Scope**

### **Global Scope**

Variables declared outside any function or block are in the global scope, accessible from anywhere in the code.

**Example:**

```javascript
var globalVar = "I’m in the global scope!";
function showGlobal() {
  console.log(globalVar); 
}
showGlobal();

/*
The output of the above code is: "I’m in the global scope!"
*/
```

### **Local (or Function) Scope**

Variables declared inside a function can only be accessed within that function.

**Example:**

```javascript
function myFunction() {
  let localVar = "I’m in the local scope!";
  console.log(localVar); // "I’m in the local scope!"
}
myFunction();
console.log(localVar); // ReferenceError: localVar is not defined
```

### **Block Scope**

Introduced in ES6, variables declared with `let` or `const` inside a block {} are limited to that block.

**Example:**

```javascript
if (true) {
  let blockVar = "I’m in the block scope!";
  console.log(blockVar); // "I’m in the block scope!"
}
console.log(blockVar); // ReferenceError: blockVar is not defined
```

---

Now that we understand scope, let’s dive deeper into **Hoisting**.

## **What is Hoisting?**

 **Hoisting** is a JavaScript behavior that allows you to use a function or variable before it’s declared. This happens because the hoisting mechanism lifts declarations to the top of their scope, making them accessible before they are defined in the code. For a more detailed explanation, you can find one [here](https://developer.mozilla.org/pt-BR/docs/Glossary/Hoisting).

Now that you have an explanation, let’s look at some examples.

### **Examples of Hoisting**

#### **With Variable**

```javascript
myVariable = 3; // Initialize myVariable
console.log("This will be 3:", myVariable); // Output is 3
var myVariable; // Declare myVariable for hoisting
```

Here, the variable `myVariable` was "hoisted" to the top of the code, which is why the console log output is `3`.

---

#### **With Function**

```javascript
fullName("Jane", "Doe");

function fullName(name, lastName) {
  console.log(`My name is ${name} ${lastName}`);
}
/*
The output of the above code is: "My name is Jane Doe"
*/

```
Even if we call the function in our code before the function is written, the code still works.

#### **With `let` and `const`**

```javascript
console.log(myVariable); // ReferenceError: Cannot access 'myVariable' before initialization
console.log(myConstVariable); // SyntaxError: Missing initializer in const declaration

let myVariable = "Hello, World!";
const myConstVariable = "Hello, World!";

```

Unlike `var`, variables declared with `let` or `const` are hoisted but remain in a “**Temporal Dead Zone (TDZ)**” until they are declared.

#### **What is the Temporal Dead Zone?**

The TDZ is the period between a variable’s creation and its declaration in the code. During the TDZ, the variable exists but hasn’t been initialized yet, and accessing it in this interval throws a ReferenceError. The TDZ primarily affects variables declared with `let` and `const`, as they adhere to their scopes, unlike `var`.

---

## **Possible Use Cases**

 **Hoisting**  itself isn’t a technique or feature you choose to use directly but rather a JavaScript behavior. So, the question isn’t about using **hoisting** but understanding how it works to avoid pitfalls and leverage specific situations.

### **When it Makes Sense**

1. **Legacy Scripts with var**  
In older projects that still use `var`, hoisting can be useful for understanding how variables are treated. However, it’s not recommended to adopt `var` in new projects, as it’s prone to confusion and bugs.

2. **Older Libraries and Frameworks**  
If you work with libraries or frameworks that haven’t adopted modern standards (like ES6), understanding hoisting is crucial for debugging and avoiding errors.

3. **Code Prototypes and Learning**  
When learning JavaScript, hoisting can help you understand how the language handles variables and functions under the hood. However, it’s important to learn best practices early on, like always declaring variables before using them.

---

### **When it Doesn’t Make Sense**

1. **Novos Projetos Modernos**  
With `let` and `const`, hoisting becomes less relevant because these variables cannot be used before their declaration. This creates a more predictable and less error-prone approach.

2. **Best Practices and Readability**  
Although hoisting allows you to run code before its declaration, it’s not a recommended practice as it can make code confusing for other developers (or even for yourself in the future).

---

## **Is Hoisting Still Relevant Today?**

Does hoisting still make sense today? Yes, no, maybe… hahaha!
All jokes aside, hoisting is still useful in specific situations, such as using function declarations and maintaining legacy projects. However, in modern projects, the scenario is different.
Here are some tips to handle variables and avoid issues:

- Prefer `let` and `const`.
- Declare variables at the beginning of the scope where they will be used.
- Avoid relying on the implicit behavior of hoisting to ensure more readable and predictable code.

While the direct use of the hoisting concept is becoming less common, understanding how it works remains an essential skill for every JavaScript developer.  
After all, knowledge is never too much, right? :)
