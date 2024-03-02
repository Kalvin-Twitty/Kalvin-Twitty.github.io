---
layout: post
title: "Node.js Basics"
date: 2023-01-03 02:51:00 -500
categories: coding
tags: windows coding javascript node windows linux ubuntu
image:
  path: /assets/2023-01-03-nodejs-basics/What-is-node.png
---

# Node.js Basics

In this guide, we'll provide an overview of Node.js, including how to set up a Node.js environment, work with modules, and use npm (Node Package Manager).

## What is Node.js?

Node.js is an open-source, cross-platform JavaScript runtime environment that allows you to run JavaScript code on the server-side. It uses the V8 JavaScript engine from Google Chrome to execute code outside the browser.

## Setting up a Node.js Environment

1. **Installation**: Visit the [official Node.js website](https://nodejs.org/) and download the installer for your operating system. Follow the installation instructions provided.

2. **Checking Installation**: Open a terminal or command prompt and run the following command to verify that Node.js and npm are installed:

    ```bash
    node -v
    npm -v
    ```

    This will display the installed Node.js version and npm version.

## Working with Modules

Node.js uses a module system to organize code into reusable components. Each file in Node.js is treated as a module. You can create your own modules and import built-in or third-party modules using the `require` function.

1. **Creating a Module**: Create a new JavaScript file (e.g., `myModule.js`) and define a function or variable:

    ```javascript
    // myModule.js
    const greeting = "Hello, ";

    function greet(name) {
        console.log(greeting + name);
    }

    module.exports = greet;
    ```

2. **Using a Module**: In another file, use the `require` function to import the module and access its functionality:

    ```javascript
    // main.js
    const myModule = require('./myModule');

    myModule('John');
    ```

## Using npm (Node Package Manager)

npm is the default package manager for Node.js, allowing you to install, manage, and share JavaScript packages and libraries.

1. **Initializing a Project**: Navigate to your project directory in the terminal and run the following command to create a `package.json` file:

    ```bash
    npm init
    ```

    Follow the prompts to set up your project details.

2. **Installing Packages**: Use the `npm install` command to install packages locally. For example, to install the Express.js framework:

    ```bash
    npm install express
    ```

3. **Using Installed Packages**: After installing a package, you can require it in your code just like any other module:

    ```javascript
    const express = require('express');
    ```

4. **Managing Dependencies**: Update dependencies listed in `package.json` by running:

    ```bash
    npm update
    ```

    This will update packages to their latest versions based on the version constraints specified in `package.json`.

Node.js, with its module system and npm, provides a powerful platform for building scalable and efficient server-side applications using JavaScript.
