# PHP Basics: echo(), print(), print_r(), var_dump() statements

In PHP, the `echo` and `print` statements are used to output data to the screen or to a file. They are similar in that they both send output to the browser, but there are a few key differences between them.

The `echo` statement is used to output one or more strings of text. It can take multiple arguments and output them all at once, separated by commas.

 Here is an example of how it works:
`echo "Hello, world!";`

In this example, the `echo` statement is used to output the string `"Hello, world!"` to the screen.

The `print` statement is similar to the `echo` statement, but it can only output a single string of text. It is often used when you want to output the result of a function or expression. 

Here is an example:
```
$result = 5 + 5;
print "The result is $result";
```
In this example, the print statement is used to output the result of the `$result` variable, which is the result of the expression 5 + 5.

In addition to the echo and print statements, PHP also has the `var_dump()` and `print_r()` functions, which are used to output the contents of a variable. The var_dump() function outputs the data type and value of a variable, while the `print_r()` function outputs the value of a variable in a more readable format. 

Here is an example of how they work:
```
$myArray = array(1, 2, 3);

var_dump($myArray);
// Output: array(3) { [0]=> int(1) [1]=> int(2) [2]=> int(3) }

print_r($myArray);
// Output: Array ( [0] => 1 [1] => 2 [2] => 3 )
```
In this example, the `var_dump()` and `print_r()` functions are used to output the contents of the `$myArray` variable. 

The `var_dump()` function outputs the data type and value of each element in the array, while the `print_r()` function outputs the value of each element in a more readable format. 

These functions are often used for debugging purposes to help you see the contents of a variable and understand how it is being used in your code.