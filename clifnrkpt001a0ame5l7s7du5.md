---
title: "Javascript Basics: All about data types."
datePublished: Sat Jun 03 2023 07:13:58 GMT+0000 (Coordinated Universal Time)
cuid: clifnrkpt001a0ame5l7s7du5
slug: javascript-basics-all-about-data-types
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1670949045196/schthcNNp.jpeg
tags: variables, javascript, web-development, beginner, beginners

---

In JavaScript, a `data type` is a classification of the type of value that a variable or expression can hold. There are several data types in JavaScript, including:

Numbers: for numeric values.  
For example:

```plaintext
let x = 5;
```

Strings: for textual data.  
For example:

```plaintext
let name = "John Doe";
```

Booleans: for true/false values.  
For example:

```plaintext
let isValid = true;
```

Null: for null values, which represent the absence of a value.  
For example:

```plaintext
let x = null;
```

Undefined: for variables that have been declared but not yet assigned a value. For example:

```plaintext
let x;
console.log(x); // Output: undefined
```

Object: for complex data structures.  
For example:

```plaintext
let user = {
  name: "John Doe",
  age: 30
};
```

Note that the data types in JavaScript are dynamic, which means that a variable can hold values of different data types at different times.  
For example:

```plaintext
let x = 5;
console.log(typeof x); // Output: number

x = "Hello";
console.log(typeof x); // Output: string
```

In the code above, the `typeof` operator is used to check the data type of the `x` variable.  
At first, `x` is a `number`, but after it is assigned the `string` value `"Hello"`, its data type becomes a `string`.