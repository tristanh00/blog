---
title: "Demystifying Asynchronous JavaScript for Beginners"
datePublished: Sat Jun 03 2023 07:24:48 GMT+0000 (Coordinated Universal Time)
cuid: clifo5i0f002f09jnex6220jk
slug: demystifying-asynchronous-javascript-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/690dd3cd0d052bcc8fb12f08119ff423.jpeg
tags: javascript, asynchronous, web-development, html5, beginners

---

In this post, we'll take a deep dive into understanding asynchronous JavaScript.  
  
We'll learn about the traditional ways of handling asynchronous operations in JavaScript, like **callbacks** and **Promises**, and then we'll look at how `async` and `await` can make our code more readable and maintainable.

## **Synchronous vs Asynchronous JavaScript**

JavaScript is single-threaded, which means it can only do one thing at a time. To make the most of this limitation and avoid blocking the main thread (the only thread JavaScript has), JavaScript uses an asynchronous approach.

In synchronous programming, operations occur one after another. In JavaScript, this would mean that if we have three functions - `first()`, `second()`, and `third()` - they will be executed in the exact order they are called:

```javascript
first(); 
second(); 
third();
```

However, suppose the `first()` function involves a time-consuming task, like fetching data from a server or a database. The problem is that in a synchronous setup, `second()` and `third()` won't execute until `first()` has finished its job.  
  
This is where asynchronous JavaScript comes to the rescue!

## **Callbacks**

The initial method JavaScript provided for handling asynchronous operations was through the use of callbacks.

A callback is a function passed into another function as an argument, which is then invoked inside the outer function to complete some action.

```javascript
function first(callback) { 
    setTimeout(function() { 
        console.log('first function done');
        callback(); 
    }, 500); 
} 

function second() { 
    console.log('second function done'); 
}

first(second);
```

In this example, `first()` is taking `second()` as a callback. `second()` only runs after `first()` completes.

While callbacks can handle basic asynchronous operations, they can lead to "callback hell" when operations depend on the results of each other. The code can quickly become nested and difficult to read.

## **Promises**

Promises were introduced to solve the problem of callback hell and make asynchronous code easier to manage.

A Promise in JavaScript is an object representing the eventual completion or failure of an asynchronous operation. Promises can be in one of three states: pending, fulfilled, or rejected.

Here's an example of the previous code, rewritten with Promises:

```typescript
function first() { 
    return new Promise(function(resolve, reject) { 
        setTimeout(function() {
            console.log('first function done'); 
            resolve(); 
        }, 500); 
    }); 
} 

function second() {
    console.log('second function done'); 
} 

first().then(second);
```

Here, `first()` returns a Promise that resolves after a timeout. Only after the Promise resolves does `second()` run.

## **Async/Await**

`Async` and `await` were introduced in ES8, and they are essentially syntactic sugar over Promises that make our asynchronous code look and behave a little more like synchronous code.

An `async` function is a function that knows how to expect the possibility of the `await` keyword being used to invoke asynchronous code.

The `await` keyword is used to pause the execution of the function and wait for the Promise's resolution or rejection. It can only be used inside an `async` function.

Here's the previous code, rewritten with async/await:

```typescript
function first() { 
    return new Promise(function(resolve, reject) { 
        setTimeout(function() {
            console.log('first function done'); 
            resolve(); 
        }, 500); 
    }); 
} 
async function second() {
    await first(); 
    console.log('second function done'); 
} 
second();
```

In the example, `second()` is an `async` function that waits for `first()` to complete before running its code. The `await` keyword makes `second()` wait without blocking the main thread.

## **Conclusion**

Asynchronous JavaScript is a fundamental part of the language, and understanding how to work with it can greatly improve your ability to write efficient, fast, non-blocking code. By progressing from callbacks to Promises and then to async/await, you can write code that is much easier to understand and maintain.

Hopefully, this guide has helped demystify asynchronous JavaScript for you. Happy coding!