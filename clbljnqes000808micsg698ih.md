# PHP Basics: All the ways to remove a key from a PHP array

In PHP, there are several ways to remove a key from an array. Here are some examples:

Using the `unset()` function:

```
$array = ['a', 'b', 'c'];

unset($array[1]);
```
This code removes the element with the key `1` from the `$array` array.

Using the `array_splice()` function:

```
$array = ['a', 'b', 'c'];

array_splice($array, 1, 1);
```
This code removes the element at index `1` from the `$array` array.

Using the `array_filter()` function:

```
$array = ['a', 'b', 'c'];

$array = array_filter($array, function($key) {
    return $key != 1;
}, ARRAY_FILTER_USE_KEY);
```
This code creates a new array that contains all elements from the `$array` array except for the element with the key `1`.

Using the `array_map()` function:

```
$array = ['a', 'b', 'c'];

$array = array_map(function($key, $value) {
    if ($key != 1) {
        return $value;
    }
}, array_keys($array), $array);
```
This code creates a new array that contains all elements from the `$array` array except for the element with the key `1`.

Using the `array_reduce()` function:

```
$array = ['a', 'b', 'c'];

$array = array_reduce(array_keys($array), function($result, $key) use ($array) {
    if ($key != 1) {
        $result[$key] = $array[$key];
    }
    return $result;
}, []);
```
This code creates a new array that contains all elements from the `$array` array except for the element with the key `1`.