---
title: "Javascript Basics: A Deep Dive into Arrays for Beginners"
datePublished: Sat Jun 03 2023 08:02:00 GMT+0000 (Coordinated Universal Time)
cuid: clifphcgv000f09mn1r9o3m64
slug: javascript-basics-a-deep-dive-into-arrays-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/yXrl2lkGJ-k/upload/73f3507d77d3aaab1d5ba682ea526d90.jpeg
tags: javascript, web-development, webdev, html5, typescript

---

In JavaScript, an array is a single variable used to store different elements.

It's an object that can store multiple values of the same or different data types sequentially using a special syntax.

This post will introduce you to the essentials of JavaScript arrays and how to work with them.

## **Creating JavaScript Arrays**

An array is defined using square brackets `[]`, and you can access the elements of the array by referring to the index number.

```typescript
let fruits = ["apple", "banana", "mango"]; 
console.log(fruits[0]); // Outputs: apple
```

In the above example, we create an array called `fruits` that contains three strings.  
  
**Important**: Arrays are zero-indexed, which means the first element is at position 0.

## **Adding or Modifying Array Elements**

JavaScript arrays are mutable, meaning you can add or change elements after the array is created.

```typescript
let fruits = ["apple", "banana", "mango"]; 

fruits[1] = "blueberry"; // Change second element 
fruits[3] = "strawberry"; // Add fourth element 

console.log(fruits); // Outputs: ["apple", "blueberry", "mango", "strawberry"]
```

In the above example, we replaced "banana" with "blueberry" and added "strawberry" to the end of the array.

## **Array Properties and Methods**

### **The length Property**

The `length` property returns the number of elements in an array.

```typescript
let fruits = ["apple", "banana", "mango"]; 
console.log(fruits.length); // Outputs: 3
```

### **The push() and pop() Methods**

The `push()` method adds a new element to the end of an array and returns the new length of the array.

```typescript
let fruits = ["apple", "banana", "mango"]; 
fruits.push("strawberry"); // Adds strawberry to the end 

console.log(fruits); 
// Outputs: ["apple", "banana", "mango", "strawberry"]
```

The `pop()` method removes the last element from an array and returns that element.

```typescript
let fruits = ["apple", "banana", "mango"]; 
let lastFruit = fruits.pop(); // Removes mango from the end 

console.log(lastFruit); // Outputs: mango 
console.log(fruits); // Outputs: ["apple", "banana"]
```

### **The shift() and unshift() Methods**

The `shift()` method works much like `pop()`, but instead of removing the last element, it removes the first one.

```typescript
let fruits = ["apple", "banana", "mango"]; 

let firstFruit = fruits.shift(); // Removes apple from the front 
console.log(firstFruit); // Outputs: apple 
console.log(fruits); // Outputs: ["banana", "mango"]
```

The `unshift()` method adds one or more elements to the beginning of an array and returns the new length of the array.

```typescript
let fruits = ["apple", "banana", "mango"]; 

fruits.unshift("strawberry"); // Adds strawberry to the front 
console.log(fruits); 
// Outputs: ["strawberry", "apple", "banana", "mango"]
```

## **Looping Through Arrays**

To iterate through all the elements of an array, you can use a `for` loop.

```typescript
let fruits = ["apple", "banana", "mango"]; 

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]); 
}
```

In this example, the loop starts from `i=0` and continues until `i` is less than the length of the array, which is the index of the last element.

## **Conclusion**

Arrays are a fundamental part of JavaScript and understanding them is crucial for managing data in your programs.

They provide a way to store multiple values in a single variable, with a host of built-in methods and properties to help you manipulate and navigate through them.

Keep exploring arrays, as they form the bedrock for more complex data structures and types.