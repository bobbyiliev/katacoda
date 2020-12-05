If you have ever done any programming you are probably already familiar with arrays. But just in case that you are not a developer, unlike variables, arrays can hold several values under one name.

You can initialize an array by assigning values devided by space and enclosed in `()`. Example:

```
my_array=("value 1" "value 2" "value 3" "value 4")
```{{execute}}

To access the elements in the array, you need to reference them by their numeric index.

Note: keep in mind that you need to use curly brackets.

* Access a single element, this would output: value 2
```
echo ${my_array[1]}
```{{execute}}

* This would return the last element: value 4
```
echo ${my_array[-1]}
```{{execute}}

* As with command line arguments using `@` will return all arguments in the array, as follows: `value 1 value 2 value 3 value 4`

```
echo ${my_array[@]}
```{{execute}}

* Prepending the array with a hash sign (`#`) would output the total number of elements in the array, in our case it is `4`:

```
echo ${#my_array[@]}
```{{execute}}

Make sure to test this and practice it at your end with different values.