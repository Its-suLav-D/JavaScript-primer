# Modern JavaScript

## Arrow Function

A more concise function syntax, particularly useful for replacing short anonymous functions. The basic syntax for an arrow function is:

```
(param1, param2) => {
    clapHand(param1, param2);
    return 'This worked';
}
```

However, if an arrow function only requires one line, then the curly braces and return keywords can be removed. Additionally, when these are used inline such as for a call to the array map function, the semicolon must be removed. Finally, if there is only one parameter, the parantheses around the parameter can also be removed. For example, this code will create and array with the values doubled:

```
[1,2,3,4].map(num => num * 2);

```

There are few constratins to arrow functions which will be explored througouht the course. The most important of these is that arrow fucntions do not have their own <mark> this </mark> binding. Additionally,arrow functions cannot be used as a constructors or generators.

## Destructuring Assignment

> Array Destructuring

```
const [fist, second] = [1,2,3];
console.log(first) // 1
console.log(second) // 2

```

> When destructuring object it can also be renamed

```
const car = {
    color: white,
    model: Dodge,
    vin: 123123123123,
    engine: []
}

const {color: dodgeColor, model: isDodge} = car

console.log(dodgeColor) // white
console.log(isDodge) // model

```

> Destructuring can also be used in a function parameter, for example

```
function displayName({name}) {
    console.log(name)
}

```

## Rest Operator

A javascript operator using ... for condensing multiple elements into a single array. This uses the same synatx as the spread operator, but funtionality is essentially the opposite.

Rest syntax can be used in both arrays and objects to get all of the values not being destructured. For example:

```

const floffy = ["Hey", "Floppy", "is", "my", "best friend", "."]
const [firstWord, secondWord, ...rem] = floffy // ..rem is ["is", "my", "best friend", "."]

// Rest on Object

const {key1, key2, ...rem} = car //  ...rem is {vin: value, engine:[]}

```

## Spread Operator

In JavaScript, the spread operator (...) is a syntax that allows you to expand an iterable object (such as an array or a string) into a list of its individual elements. It is often used in combination with other features such as destructuring and the rest/spread operator (...).

Here is an example of how to use the spread operator:

``` 
let array1 = [1, 2, 3];
let array2 = [...array1, 4, 5];

console.log(array2); // Output: [1, 2, 3, 4, 5]
```
In this example, the spread operator is used to expand the elements of the array1 into a list, which is then combined with the 4 and 5 elements to create a new array, array2.

The spread operator can also be used to spread the elements of an array into the arguments of a function, like this:

```
function sum(a, b, c) {
  return a + b + c;
}

let array = [1, 2, 3];

console.log(sum(...array)); // Output: 6

```
In this example, the spread operator is used to spread the elements of the array into the arguments of the sum function, which adds them together and returns the result.

## Template Literal 

In JavaScript, a template literal is a way to define a string that spans multiple lines and can contain expressions. Template literals are surrounded by backticks (`), rather than single or double quotes.

Here is an example of a template literal that spans multiple lines and includes an expression:

```
const name = 'Bob';
const age = 30;

const message = `Hello, my name is ${name} and I am ${age} years old.`;
// Output: "Hello, my name is Bob and I am 30 years old."
```
In this example, the name and age variables are interpolated into the string using the ${} syntax. This is known as string interpolation.

Template literals also allow you to define strings that span multiple lines, which can be useful for creating longer, more readable strings.

```
const html = `
<div>
  <h1>Hello, World!</h1>
  <p>This is a paragraph</p>
</div>
`;

```
Template literals were introduced in JavaScript as part of the ES6 (ECMAScript 6) specification. They provide a more powerful and flexible way to define strings compared to traditional string literals.

## Null Coalescing 

In JavaScript, the null coalescing operator (??) is a logical operator that returns the first operand if it exists and is not null, or the second operand if the first operand is either null or undefined. It is a shorthand way of writing a conditional expression that checks for null or undefined.

Here is an example of using the null coalescing operator:

```
const user = { name: 'Bob' };

const username = user.name ?? 'Guest';
// Output: "Bob"
``` 
In this example, the username variable is assigned the value of user.name if it exists and is not null, or the string 'Guest' if user.name is either null or undefined.

Here is the same example written using a conditional expression:

```
const username = user.name !== null && user.name !== undefined ? user.name : 'Guest';

```
The null coalescing operator can be useful when you want to provide a default value for a variable that might be null or undefined. It can also be used to simplify code by reducing the need for nested conditional expressions.

The null coalescing operator was introduced in JavaScript as part of the ES2020 (ECMAScript 2020) specification. It is supported in modern browsers and can be used with transpilers like Babel to support older browsers.

## Optional Chaining 

In JavaScript, optional chaining is a feature that allows you to access an object's properties, methods, or elements without having to check for null or undefined values. It is a shorthand way of writing a series of checks to see if an object, property, or element exists before trying to access it.

Here is an example of using optional chaining to access an object's property:

```
const user = { name: 'Bob' };

const username = user?.name;
// Output: "Bob"

```
In this example, the username variable is assigned the value of user.name if user exists and is not null or undefined. If user is null or undefined, the value of username will be undefined.

Here is the same example written without optional chaining:

```
let username;
if (user && user.name) {
  username = user.name;
}
``` 
Optional chaining can be useful when you want to access properties or elements of an object that may not exist, or when you are working with data that may be null or undefined. It can also help to simplify code by reducing the need for nested conditional statements.

Optional chaining was introduced in JavaScript as part of the ES2020 (ECMAScript 2020) specification. It is supported in modern browsers and can be used with transpilers like Babel to support older browsers.


## Short Circuit Evaulation 

In JavaScript, short-circuit evaluation is a feature that allows you to use logical operators (such as && and ||) to evaluate expressions and determine the value of a boolean expression. It is called "short-circuit" evaluation because the second operand is only evaluated if the first operand is not sufficient to determine the value of the expression.

Here is an example of short-circuit evaluation using the && operator:

```
const user = { name: 'Bob' };

const username = user && user.name;
// Output: "Bob"
```
In this example, the username variable is assigned the value of user.name if user exists and is not null or undefined. If user is null or undefined, the value of username will be undefined. This is because the && operator only evaluates the second operand (user.name) if the first operand (user) is truthy.

Here is the same example written without short-circuit evaluation:

```
let username;
if (user) {
  username = user.name;
}
```
Short-circuit evaluation can be useful for reducing the number of conditional statements in your code, and for simplifying complex boolean expressions.

> Note that short-circuit evaluation is only possible with the && and || operators. It is not possible with the & and | operators, which always evaluate both operands regardless of the value of the first operand.

|| operator only needs one expression to be true, if the left side is true then the right side will not be evaluated. This is quite the opposite of the && operator. For example, 
```
true || myFunc() // doesn't call myFunc
false || myFunc() // calls myFunc 

```