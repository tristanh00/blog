---
title: "Delving Deeper into JavaScript Standards: ECMAScript 6 and ECMAScript 2020"
datePublished: Wed Jun 07 2023 19:15:29 GMT+0000 (Coordinated Universal Time)
cuid: clim3auxm000309l2fypj2db6
slug: delving-deeper-into-javascript-standards-ecmascript-6-and-ecmascript-2020-es11
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/920d8f2ca07e98cbc6fc8a1608fc7725.jpeg
tags: tutorial, programming-blogs, javascript, web-development, beginners

---

JavaScript, an integral part of the modern web, is an ever-evolving language with its standards maintained by the ECMAScript specification.

Over the years, different versions have been released, each bringing new features and improvements that enhance the language's power and usability.

In this post, we'll dive deeper into ECMAScript 6 (also known as ES6 or ECMAScript 2015) and ECMAScript 2020 (ES11 / ES2020) to better understand their offerings.

### ECMAScript 6 (ES6)

Released in 2015, ES6 marked a significant update to JavaScript, featuring a vast array of new features that transformed the language's landscape.

**Classes:** ES6 introduced classes, providing a much-needed syntactic sugar over JavaScript's prototypal inheritance. They provide a more intuitive and familiar way of defining object constructors and prototype methods for those coming from class-based languages.

**Arrow Functions:** This feature brought a more concise way of defining functions, especially anonymous ones. They also lexically bind the `this` value, thus solving a common problem in JavaScript related to 'this' context.

**Promises:** ES6 brought Promises to JavaScript, providing a more structured way of dealing with asynchronous operations. Promises represent eventual completion or failure of an asynchronous operation and its resulting value.

**Modules:** With ES6, JavaScript got built-in modules. This gave developers a standard way to organize code into modules and manage dependencies using import and export statements.

### ECMAScript 2020 (ES2020)

Fast forward to 2020, the ECMAScript 2020 release further refined JavaScript with these key features:

**Optional Chaining:** This operator (?.) allows for safer access to nested object properties without checking the existence of each layer. It short-circuits and returns undefined if it hits a nullish value (null or undefined).

**Nullish Coalescing:** The nullish coalescing operator (??) provides a way to set default values when dealing with nullish values, unlike the logical OR operator (||) which considers all falsy values.

**BigInt:** The BigInt data type was introduced to represent integers larger than the Number type can handle, which is useful when dealing with large integers.

**Promise.allSettled:** While ES6 introduced Promises, ES2020 took it a step further with Promise.allSettled. This method waits for all promises to settle, regardless of whether they fulfill or reject, providing a comprehensive status.

**Dynamic Import:** This feature enables modules to be loaded dynamically at runtime, offering opportunities for code-splitting and lazy-loading, improving application performance.

### Browser Support

Both ES6 and ES2020 are well-supported in modern browsers, although the degree of support varies. As of writing, Google Chrome, Mozilla Firefox, Microsoft Edge, and Apple Safari support most of the features of ES2020 and ES6. However, when targeting a broad audience, it's wise to use tools like Babel to transpile your code to ES5 to ensure backward compatibility with older browsers.

### The Most Common JavaScript Standards in Use Today

As the landscape of web development evolves, developers are continually leveraging new features offered by the latest JavaScript standards.

However, not all environments (like older browsers) support the newest standards, so developers often choose to use a mix of different versions or use transpilers to ensure compatibility. Below are some of the most commonly used JavaScript standards today.

**ECMAScript 5 (ES5):** ES5 is the oldest standard that is still widely used today. Released in 2009, it is supported by virtually all browsers, making it a safe choice for broad compatibility. ES5 introduced key features such as `strict mode`, `accessor properties`, and native `JSON` support.

**ECMAScript 6 (ES6):** Also known as ECMAScript 2015, ES6 is one of the most pivotal updates to JavaScript, introducing features like `classes`, `modules`, `promises`, and `arrow functions`. Despite being released in 2015, some older browsers do not fully support it. Developers often use tools like Babel to transpile ES6 code into ES5 to ensure backward compatibility.

**ECMAScript 2016 (ES7) and ECMAScript 2017 (ES8):** These versions are commonly used and brought in useful features like `async/await` (ES8), and `Array.prototype.includes` (ES7). However, like ES6, they may require transpiling for older browser support.

**ECMAScript 2019 (ES10) and ECMAScript 2020 (ES11):** These versions continue to be more widely adopted as more developers leverage their advanced features, and browser support continues to improve. Notable additions in these versions include `flat` and `flatMap` array methods, `Object.fromEntries`, `BigInt`, `Optional Chaining`, and `Nullish Coalescing`.

In general, the choice of ECMAScript version often comes down to balancing the benefits of new features with the need for broad browser compatibility.

Developers typically use the most recent version they can that still ensures compatibility with their users' browsers.

As such, it's common to see developers working in ES6+ environments but transpiling down to ES5 for production builds.  
  
I hope these comparisons come in useful when making your choice of which JavaScript standard to follow, and as always, happy coding! :)