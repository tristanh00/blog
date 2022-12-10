# PHP Basics: Return Statement

In PHP, the `return` statement is used to return a value from a function. It terminates the execution of the function and sends the specified value back to the calling code. 

Here is an example of how it works:

```
function add($x, $y) {
  $sum = $x + $y;
  return $sum;
}
```
`$result = add(2, 3); // $result will be equal to 5`
In this example, the add() function takes two parameters, `$x` and `$y`, and adds them together to calculate the sum. The return statement is used to return the value of the `$sum` variable to the calling code. In this case, the function will return the value 5 to the calling code, which can then be stored in a variable or used in some other way.

The `return` statement is often used in combination with `if` statements to control the flow of a function. For example, you might use an `if` statement to check the input parameters and only return a value if the input is valid. 

Here is an example:

```
function add($x, $y) {
  if (is_numeric($x) && is_numeric($y)) {
    $sum = $x + $y;
    return $sum;
  } else {
    return null;
  }
}
```

`$result = add(2, 3); // $result will be equal to 5`
`$result = add("hello", "world"); // $result will be equal to null`

In this example, the `add()` function checks if the input parameters `$x` and `$y` are numeric using the `is_numeric()` function. If they are numeric, the function calculates the sum and returns it. If they are not numeric, the function returns `null`. This allows you to control the output of the function based on the input and ensure that you are always returning a valid value.