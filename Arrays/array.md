# Arrays 
In JavaScript, an array is an ordered collection of data items, which can be of any data type. Arrays are a very useful data structure in programming, and they are used to store and manage large amounts of data efficiently.

## Creating Arrays 

There are bunch of ways to create an array in javascript. Below are some of the examples to acheive it. 

```
const arr = [10] 

The Array constructor is a function that creates and initializes an array object. It is used to create an array with a specified length, or to create an array from an array-like object or iterable.

const arr = Array(341) // Create empty Array [ <341 empty items> ]
const arr = Array(341, 2) // Creates Array of length 2 [341, 2]
const arr = new Array(341)

const arr = ['CSE'] 
const arr = Array('CSE') // Creats Array of length 1 ['CSE']
const arr = new Array('CSE', 'Love') // Creeats Array of length 2 ['CSE', 'Love']
```

Array.of() is a static method that creates a new Array instance with a variable number of arguments, regardless of the number of arguments or their type.

The Array.of() method is similar to the Array constructor, but it creates an array with the given arguments as its elements, rather than creating an empty array with a specified length.
```
const arr = Array.of(341) // Creates Array of Length 1 [ 341 ]
const arr = Array.of('CSE', 341) // Creates Array of Length 2 ['CSE', 341]

```

Array.from() is a static method that creates a new, shallow-copied Array instance from an array-like or iterable object. It takes an iterable object, like an array, or a string, and returns a new Array object with the elements of the iterable.

Here is an example of using Array.from() to create an array from a string:

```
const arr = Array.from('CSE 341')
console.log(arr) // ['C','S', 'E', ' ', '3', '4', '1']
```

## Methods available for working with arrays  

1. Push() 

push() is a method that adds one or more elements to the end of an array and returns the new length of the array.

Here is an example of using push() to add an element to an array:

```
const arr = [1, 2, 3];
arr.push(4);
console.log(arr); // [1, 2, 3, 4]


```

2. Pop() 

pop() is a method that removes the last element from an array and returns the removed element.

Here is an example of using pop() to remove the last element from an array:

```
const arr = [1, 2, 3];
const last = arr.pop();
console.log(last); // 3
console.log(arr); // [1, 2]

```

3. Shift() 

shift() is a method that removes the first element from an array and returns the removed element.

Here is an example of using shift() to remove the first element from an array:

```
const arr = [1, 2, 3];
const first = arr.shift();
console.log(first); // 1
console.log(arr); // [2, 3]

```

4. unShift() 

unshift() is a method that adds one or more elements to the beginning of an array and returns the new length of the array.

Here is an example of using unshift() to add an element to the beginning of an array:

```
const arr = [1, 2, 3];
arr.unshift(0);
console.log(arr); // [0, 1, 2, 3]

```

splice() is a method that adds, removes, or replaces elements in an array. It takes three arguments: the index at which to start making changes, the number of elements to remove (if any), and the elements to add (if any). It returns an array containing the removed elements.

Here are some of the examples to remove, add, and copy  
```
// Remove an element from an array
const arr = [1, 2, 3, 4, 5];
const removed = arr.splice(2, 1);
console.log(removed); // [3]
console.log(arr); // [1, 2, 4, 5]


// Add an element 

const arr = [1, 2, 3, 4, 5];
arr.splice(2, 0, 3.5);
console.log(arr); // [1, 2, 3.5, 3, 4, 5]


// Create a shallow copy. It takes two arguments, the start index and the end index(exclusive)
const arr = [1, 2, 3, 4, 5];
const copy = arr.slice();
console.log(copy); // [1, 2, 3, 4, 5]

// Create a subarray from the middle of the array
const subarray = arr.slice(1, 4);
console.log(subarray); // [2, 3, 4]

// Create a subarray from the end of the array
const subarray2 = arr.slice(-2);
console.log(subarray2); // [4, 5]

// Create a subarray from the beginning of the array
const subarray3 = arr.slice(0, 2);
console.log(subarray3); // [1, 2]


```

5. concat() 

concat() is a method that returns a new array that consists of the elements in the original array, followed by the elements of one or more additional arrays or values. It does not modify the original array.

Here are some of the examples:

```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const merged = arr1.concat(arr2);
console.log(merged); // [1, 2, 3, 4, 5, 6]


const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const arr3 = [7, 8, 9];
const merged = arr1.concat(arr2, arr3, 10, 11, 12);
console.log(merged); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

```

> the main difference between the concat() and push() methods is that concat() returns a new array, while push() modifies the original array and returns the new length of the array.



6. indexOf() and lastIndexOf()

The indexOf() method searches for an element from the start of the array, and returns the first index at which the element can be found. If the element is not found, it returns -1.

Here is an example of how to use the indexOf() method:

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let index = array.indexOf(5);
console.log(index); // Output: 4
```

The lastIndexOf() method, on the other hand, searches for an element from the end of the array, and returns the last index at which the element can be found. If the element is not found, it returns -1.

Here is an example of how to use the lastIndexOf() method:

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let index = array.lastIndexOf(5);
console.log(index); // Output: 4

```
Both the indexOf and lastIndexOf methods accept a second argument, which specifies the index at which the search should start. For example: 

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];

let index = array.indexOf(5, 3);

console.log(index); // Output: 4

index = array.lastIndexOf(5, 6);

console.log(index); // Output: 4

```

7. find() and findIndex()

The find() and findIndex() methods in JavaScript are used to search for an element in an array that satisfies a given condition.

The find() method returns the first element in the array that satisfies the condition, or undefined if no such element is found.

Here is an example of how to use the find() method:

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];

let element = array.find(function(value) {
  return value > 5;
});
console.log(element); // Output: 6
```

The findIndex() method, on the other hand, returns the index of the first element in the array that satisfies the condition, or -1 if no such element is found.

Here is an example of how to use the findIndex() method:

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];

let index = array.findIndex(function(value) {
  return value > 5;
});
console.log(index); // Output: 5
```
Both the find() and findIndex() methods accept a callback function as an argument, which is called for each element in the array. The callback function should return a boolean value indicating whether the element satisfies the condition.

You can also use the find() and findIndex() methods with arrow functions, like this:

```
let array = [1, 2, 3, 4, 5, 6, 7, 8, 9];

let element = array.find(value => value > 5);

console.log(element); // Output: 6

let index = array.findIndex(value => value > 5);

console.log(index); // Output: 5
```

8. join()

The join() method in JavaScript is a method of the Array object that allows you to join all the elements of an array into a single string.

You can use the join() method by calling it on an array, and passing a string as an argument. The string will be used as a separator between the elements of the array in the resulting string. If you omit the separator argument, the elements will be separated by a comma.

Here is an example of how to use the join() method:
```
let array = ['I', 'love', 'JavaScript'];

let string = array.join(', ');

console.log(string); // Output: "I, love, JavaScript"

```
You can also use the join() method with an empty string as a separator, like this:

```
let array = ['I', 'love', 'Js'];

let string = array.join('');

console.log(string); // Output: "IloveJs"

Example 2. Joining an array of objects with a semicolon

let array = [{a: 1}, {b: 2}, {c: 3}];

let string = array.join('; ');

console.log(string); // Output: "[object Object]; [object Object]; [object Object]"
```
> Keep in mind that the join() method only works with arrays. If you try to use it on a non-array value, you will get an error.


9. split()

The split() method in JavaScript is a method of the String object that allows you to split a string into an array of substrings based on a specific separator.

You can use the split() method by calling it on a string, and passing a separator string as an argument. The split() method will split the string at each occurrence of the separator, and return an array of substrings. If you omit the separator argument, the split() method will split the string at each occurrence of a whitespace character (such as a space, tab, or newline).

Here is an example of how to use the split() method:

```
let string = "apple, banana, orange";

let array = string.split(', ');

console.log(array); // Output: ['apple', 'banana', 'orange']


Example 2. Use Regular Expression as a separator 

let string = "apple.banana.orange";

let array = string.split(/\./);

console.log(array); // Output: ['apple', 'banana', 'orange']

```



## Iterating Over Arrays

Along with traditional ways i.e (for,while,do while) of iterating over array, we can leverage es6 array methods to make our life easier. 

1. forEach()

forEach(): The forEach() method in JavaScript is a method of the Array object that allows you to iterate over the elements of an array and perform a specific action on each element. It does not return a new array, but instead operates on the original array.

Here is an example of how to use the forEach() method:

```
let array = [1, 2, 3, 4, 5];

array.forEach(function(value) {
  console.log(value);
});
// 1
// 2
// 3
// 4 
// 5 
```

2. map() 

map(): The map() method in JavaScript is a method of the Array object that allows you to transform the elements of an array into a new array. It returns a new array that is the result of calling a specific function on each element of the original array.

Here is an example of how to use the map() method:

```
let array = [1, 2, 3, 4, 5];

let newArray = array.map(function(value) {
  return value * 2;
});

console.log(newArray); // Output: [2, 4, 6, 8, 10]

Example 2.  Using map() to extract the first letter of each element in an array

let array = ['apple', 'banana', 'orange'];

let newArray = array.map(function(value) {
  return value[0];
});

console.log(newArray); // Output: ['a', 'b', 'o']

```

3. reduce()

The reduce() method in JavaScript is a method of the Array object that allows you to reduce the elements of an array to a single value. It applies a specific function to each element of the array, and returns a single value that is the result of the function.

Here is an example of how to use the reduce() method:

```
let array = [1, 2, 3, 4, 5];

let sum = array.reduce(function(accumulator, value) {
  return accumulator + value;
}, 0);

console.log(sum); // Output: 15

// Example2. Find Maximum value in array 

let array = [5, 2, 3, 1, 4];

let max = array.reduce(function(accumulator, value) {
  return Math.max(accumulator, value);
}, -Infinity);

console.log(max); // Output: 5


```

4. filter()

The filter() method in JavaScript is a method of the Array object that allows you to filter the elements of an array based on a specific condition. It returns a new array that contains only the elements of the original array that satisfy the condition.

Here is an example of how to use the filter() method:

```
let array = [1, 2, 3, 4, 5];

let newArray = array.filter(function(value) {
  return value % 2 === 0;
});

console.log(newArray); // Output: [2, 4]
```

5. sort()

The sort() method in JavaScript is a method of the Array object that allows you to sort the elements of an array. It modifies the original array and returns it.

Here is an example of how to use the sort() method:

```
let array = [5, 2, 3, 1, 4];

array.sort();

console.log(array); //

```

## Spread Operator on Array

The spread operator (...) in JavaScript is a syntax that allows you to expand an iterable (such as an array or string) into individual elements.

Here are some examples of how to use the spread operator:

```
// Example 1: Adding elements to an array

let array1 = [1, 2, 3];
let array2 = [4, 5, 6];

let combinedArray = [...array1, ...array2];

console.log(combinedArray); // Output: [1, 2, 3, 4, 5, 6]

// Example 2: Passing elements of an array as arguments to a function

let array = [1, 2, 3];

let max = Math.max(...array);

console.log(max); // Output: 3

// Example 3: Copying an array

let array1 = [1, 2, 3];
let array2 = [...array1];

console.log(array2); // Output: [1, 2, 3]

```

## Destructuring Arrays 

Destructuring in JavaScript is a syntax that allows you to unpack values from arrays, or properties from objects, into distinct variables.

Here are some examples of how to use destructuring with an array:

```
let array = [1, 2, 3, 4, 5];

let [a, b, c] = array;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(c); // Output: 3

You can also use destructuring with the rest operator (...) to capture the remaining elements of the array. For example:

```
```
let array = [1, 2, 3, 4, 5];

let [a, b, ...rest] = array;

console.log(a); // Output: 1
console.log(b); // Output: 2
console.log(rest); // Output: [3, 4, 5]

```
You can also use destructuring to assign default values to variables, like this:

```
let array = [1];

let [a, b = 2] = array;

console.log(a); // Output: 1
console.log(b); // Output: 2

```

> I have found spread and destructuring super useful as it prevents from long nasty chaining 


## Set 

A Set in JavaScript is a collection of unique values. It is similar to an array, but the values in a Set are not indexed, and the values must be unique.

You can create a Set by calling the Set constructor and passing an iterable (such as an array) as an argument, like this:

```
let set = new Set([1, 2, 3, 4, 5]);
```

You can also create an empty Set by calling the Set constructor without any arguments, like this:

```
let set = new Set();
You can add values to a Set using the add() method, like this:

set.add(1);
set.add(2);
set.add(3);
```

You can remove values from a Set using the delete() method, like this:

```
set.delete(2);
```

You can check if a Set contains a specific value using the has() method, like this:

```
set.has(2); // Output: false
set.has(3); // Output: true
```

You can iterate over the values in a Set using a for...of loop, like this:

```
for (let value of set) {
  console.log(value);
}
```

You can also use the size property to get the number of values in a Set, like this:

```
console.log(set.size); // Output: 2
``` 