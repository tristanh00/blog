# Javascript Basics: Common errors and error handling.

JavaScript has several types of errors that can occur while running a script. Here are some common error types and their causes:

1. **SyntaxError**: This error can occur when you forget to include a semicolon at the end of a line of code, or if you use a keyword incorrectly. For example:
    

```javascript
let x = 10 let y = 20 let sum = x + y  // missing semicolon will cause a SyntaxError
```

```javascript
let myfunction = function() {  
// forgot to include the function keyword before function console.log("Hello, World!") 
}
```

1. **ReferenceError**: This error can occur when you try to access a variable that has not been declared or has not been assigned a value. For example:
    

```javascript
console.log(x)  // x has not been declared, so this will cause a ReferenceError
```

```javascript
let y console.log(y)  // y has been declared, but it has not been assigned a value, so this will cause a ReferenceError
```

1. **TypeError**: This error can occur when you try to perform an operation on a value with an incompatible type. For example:
    

```javascript
let x = 10 let y = "hello" let sum = x + y  // cannot add a number and a string, so this will cause a TypeError
```

```javascript
let myArray = [1, 2, 3] 
console.log(myArray.length())  // the length property of an array is not a function, so this will cause a TypeError
```

1. **RangeError**: This error can occur when you try to pass a number as an argument to a function that is outside of the function's acceptable range of values. For example:
    

```javascript
function setTimeout(callback, timeout) { 
    if (timeout < 0) { 
        throw new RangeError("timeout must be greater than or equal to 0") 
    } // rest of the function code goes here 
} 
setTimeout(function() { console.log("Hello, World!") }, -1000)  // this will cause a RangeError
```

1. **URIError**: This error can occur when you try to encode or decode a URI that is malformed. For example:
    

```javascript
decodeURI("%")  // % is not a valid URI character, so this will cause a URIError
```

1. **EvalError**: This error can occur when the `eval()` function is used incorrectly. For example:
    

```javascript
eval("console.log('Hello, World!')")  // eval should only be used to evaluate strings of JavaScript code, so this will cause an EvalError
```

1. **EvalError**: This error can occur when the global `eval()` function is used in a way that is not allowed. For example:
    

```javascript
let x = 10 eval("x = 20")  // eval is not allowed to modify variables in the global scope, so this will cause an EvalError
```

These are just a few of the most common error types in JavaScript. It is important to handle errors properly in your code to ensure that your scripts run smoothly and avoid potential issues.

## Error Handling

Error handling in JavaScript is done using the `try` and `catch` statements.

Here's an example of how to use `try` and `catch` to handle an error:

```javascript
try { // code that may throw an error 
} catch(error) { 
// code to handle the error 
}
```

The `try` block contains code that may throw an error, and the `catch` block contains code that will be executed if an error is thrown. The `error` parameter is a reference to the error object that was thrown.

For example:

```javascript
try { 
    let x = y + 1; 
    // this will cause a ReferenceError because y is not defined 
} catch(error) { 
    console.error(error); 
    // logs the error object 
}
```

You can also use the `finally` block to execute code regardless of whether an error was thrown or not. The `finally` block will always be executed after the `try` and `catch` blocks, whether an error was thrown or not.

```javascript
try { 
    let x = y + 1; 
    // this will cause a ReferenceError because y is not defined 
} catch(error) { 
    console.error(error); 
    // logs the error object 
} finally { 
    console.log('This will always be executed'); 
}
```

You can also throw your own errors by using the `throw` statement.

```javascript
try { 
    throw new Error('Something went wrong'); 
} catch(error) { 
    console.error(error); 
    // logs the error object 
}
```

It's generally a good practice to include error handling in your code to avoid unexpected behavior and to provide meaningful feedback to users if something goes wrong.