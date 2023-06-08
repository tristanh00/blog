---
title: "JavaScript Arrays: How to Delete / Remove Array Keys & Value"
datePublished: Thu Jun 08 2023 16:07:17 GMT+0000 (Coordinated Universal Time)
cuid: clinc0p0m00000alfhx337g9c
slug: javascript-arrays-how-to-delete-remove-array-keys-value
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686240514576/43004189-ef43-4d5f-9fff-1c67e78f0213.png
tags: tutorial, javascript, web-development, beginners, proper

---

### Introduction

In JavaScript, arrays are critical data structures that offer a multitude of possibilities. One operation that you may need to perform when working with arrays is the removal of keys or indices. There are several methods to accomplish this task, each suited to different scenarios and needs. In this article, we'll delve into various techniques to remove an array key in JavaScript.

1. ### Using the `delete` keyword
    

The `delete` operator allows you to remove a key and its associated value from an array. However, it does not affect the length of the array. The key's place is still retained in the array, but it becomes `undefined`.

```javascript
let array = ['one', 'two', 'three'];
delete array[1];
console.log(array); // Output: ['one', undefined, 'three']
```

1. ### Using `splice()`
    

The `splice()` method can be used to add/remove items to/from an array and returns the removed item(s). This method changes the original array, meaning it actually removes the key and the length of the array is modified.

```javascript
let array = ['one', 'two', 'three'];
array.splice(1, 1);
console.log(array); // Output: ['one', 'three']
```

In the above example, `splice()` takes two parameters. The first is the index at which to start changing the array, and the second is the number of elements to remove.

1. ### Using `filter()`
    

The `filter()` method creates a new array with all elements that pass the test provided by the given function. It's a non-destructive way of removing an item from an array based on a condition.

```javascript
let array = ['one', 'two', 'three'];
array = array.filter((item, index) => index !== 1);
console.log(array); // Output: ['one', 'three']
```

In this example, the filter function is used to create a new array that includes all elements for which the provided filtering function returns `true`. The function is a test that checks each index and only returns `true` if the index is not equal to 1.

1. ### Using `pop()` and `shift()`
    

The `pop()` and `shift()` methods can be used to remove keys from the end and the beginning of the array, respectively.

`pop()` removes the last element from an array and returns that element. This method changes the length of the array.

```javascript
let array = ['one', 'two', 'three'];
array.pop();
console.log(array); // Output: ['one', 'two']
```

`shift()` removes the first element from an array and returns that removed element. This method changes the length of the array.

```javascript
let array = ['one', 'two', 'three'];
array.shift();
console.log(array); // Output: ['two', 'three']
```

### Conclusion

Arrays are flexible and versatile structures in JavaScript that can be manipulated using various methods.

Whether you need to remove elements by index, value, or condition, JavaScript has a method that can help.

While `delete`, `splice()`, `pop()`, and `shift()` modify the original array, `filter()` offers a non-destructive alternative by creating a new array.

Choose the method that best suits your specific requirements, and ensure to understand its implications on your array's structure.