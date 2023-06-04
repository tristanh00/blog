---
title: "PHP Basics: Conditionals - if/else/elseif statements"
datePublished: Sat Dec 10 2022 04:00:01 GMT+0000 (Coordinated Universal Time)
cuid: clbhes357000608lb6mc3dvv1
slug: php-conditionals-if-else-elseif-statements
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1670644973606/IdBJ7FK0C.jpeg
tags: tutorial, web-development, php, webdev, beginners

---

A conditional statement in PHP is a control flow statement that allows you to execute a block of code based on the result of a logical expression. In other words, a conditional statement allows you to make decisions in your code by checking if a certain condition is true or false.

The most commonly used conditional statement in PHP is the if-else statement. This statement takes the following form:

```typescript
if (condition) {
    // code to execute if condition is true
} else {
    // code to execute if condition is false
}
```

In this example, the `if` keyword is followed by a logical expression in parentheses. If the expression evaluates to true, the code block inside the if statement will be executed. If the expression evaluates to false, the code inside the else block will be executed instead.

Here is an example of how an if-else statement might be used in PHP:

```typescript
$x = 10;

if ($x > 5) {
    echo "x is greater than 5";
} else {
    echo "x is not greater than 5";
}
```

In this code, the if statement checks if the value of the `$x` variable is greater than `5`. Since the value of `$x` is `10`, the code inside the if block will be executed, and the message `"x is greater than 5"` will be displayed.

In addition to the `if-else` statement, PHP also has other conditional statements that can be used in different situations. For example, the `elseif` statement allows you to chain multiple conditional statements together.

Here is an example of how it works:

```typescript
if (condition1) {
  // code to be executed if condition1 is true
} else if (condition2) {
  // code to be executed if condition1 is false and condition2 is true
} else {
  // code to be executed if both condition1 and condition2 are false
}
```

The `else if` statement is useful when you want to test multiple conditions and only execute certain code if one of those conditions is met.

In the example above, if `condition1` is true, the code inside the first if block will be executed. If `condition1` is false but `condition2` is true, the code inside the else if block will be executed. If both `condition1` and `condition2` are false, the code inside the else block will be executed.

In summary, conditional statements in PHP are control flow statements that allow you to make decisions in your code by checking if a certain condition is true or false. They are an essential part of any programming language, and they are used to execute different blocks of code based on the result of a logical expression.