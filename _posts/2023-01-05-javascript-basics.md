---
layout: post
title: "JavaScript Basics"
date: 2023-01-02 02:51:00 -500
categories: coding
tags: windows coding javascript
image:
  path: /assets/2023-01-05-JavaScript-basics/JS-Basic.jpg
---

# JavaScript Basics

In this guide, we'll cover fundamental concepts of JavaScript, including variables, data types, operators, control flow, and functions.

## Variables

Variables are used to store data values. In JavaScript, you can declare variables using `var`, `let`, or `const`.

```javascript
// Variable declaration
var name = "John";
let age = 30;
const PI = 3.14;
```

## Data Types

JavaScript has several primitive data types:

- Number: Represents numeric values.
- String: Represents textual data.
- Boolean: Represents true/false values.
- Undefined: Represents the absence of a value.
- Null: Represents the intentional absence of any value.
- Symbol (ES6): Represents a unique identifier.

```javascript
let num = 10;
let str = "Hello";
let bool = true;
let undef;
let n = null;
let sym = Symbol("foo");
```

## Operators

JavaScript supports various operators:

- Arithmetic Operators: +, -, *, /, %.
- Comparison Operators: ==, ===, !=, !==, <, >, <=, >=.
- Logical Operators: && (AND), || (OR), ! (NOT).
- Assignment Operators: =, +=, -=, *=, /=.
- Ternary Operator: condition ? expr1 : expr2.

```javascript
let x = 10;
let y = 5;

// Arithmetic Operators
let sum = x + y;
let diff = x - y;
let product = x * y;
let quotient = x / y;
let remainder = x % y;

// Comparison Operators
let isEqual = x === y;
let isGreater = x > y;

// Logical Operators
let isBothTrue = (x > 0) && (y < 10);
let isEitherTrue = (x > 0) || (y > 10);

// Ternary Operator
let result = (x > y) ? "x is greater" : "y is greater";
```

## Control Flow

Control flow statements determine the order in which statements are executed.

- Conditional Statements: if, else if, else.
- Switch Statement: Executes a block of code depending on different cases.
- Loops: for, while, do...while.

```javascript
let num = 10;

// Conditional Statements
if (num > 0) {
    console.log("Positive");
} else if (num < 0) {
    console.log("Negative");
} else {
    console.log("Zero");
}

// Switch Statement
let day = "Monday";
switch (day) {
    case "Monday":
        console.log("Start of the week");
        break;
    case "Friday":
        console.log("End of the week");
        break;
    default:
        console.log("Midweek");
}

// Loops
for (let i = 0; i < 5; i++) {
    console.log(i);
}

let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

## Functions
Functions are blocks of reusable code that perform a specific task.

```javascript
// Function Declaration
function greet(name) {
    return "Hello, " + name + "!";
}

// Function Expression
let square = function(x) {
    return x * x;
};

// Arrow Function (ES6)
let cube = (x) => {
    return x * x * x;
};

console.log(greet("John"));
console.log(square(4));
console.log(cube(3));
```

These are the fundamental concepts of JavaScript that every developer should understand to start building applications.