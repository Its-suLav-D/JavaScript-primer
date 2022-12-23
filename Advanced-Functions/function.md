# Functions 

In JavaScript, a function is a block of code that can be defined and called by a name. Functions are a fundamental building block of the language, and are used to perform reusable tasks or to abstract complex logic.

---

## Pure and Impure Functions 

a pure function is a function that always returns the same output for a given set of inputs, and has no side effects. This means that a pure function does not modify any variables outside of its own scope, and does not make any external requests or perform any other actions that could affect the state of the program.

Here is an example of a pure function:

```
function add(a, b) {
  return a + b;
}

const sum = add(1, 2);
console.log(sum); // Output: 3


```

On the other hand, an impure function is a function that has side effects or depends on variables outside of its own scope. This means that an impure function may return different output for the same set of inputs, or may modify variables or perform other actions that affect the state of the program.

Here is an example of an impure function:

```
let counter = 0;

function incrementCounter() {
  counter++;
}

incrementCounter();
console.log(counter); // Output: 1
incrementCounter();
console.log(counter); // Output: 2


```

> Note: Pure functions are generally considered to be easier to test and debug, as they do not depend on external state and always produce the same output for a given set of inputs. Impure functions, on the other hand, may be more difficult to test and debug, as they may have unexpected side effects and may produce different output for the same set of inputs.


--- 

## Factory Functions 


 factory function is a function that returns a new object or value, typically based on some input or configuration. Factory functions are often used to create objects or values that are similar, but not exactly the same, and can be a useful way to encapsulate complex logic or reduce duplication in your code.

Here is an example of a simple factory function that returns a new object with a name property:

```
function createPerson(name) {
  return {
    name: name
  };
}

```

const person1 = createPerson('John');
const person2 = createPerson('Mary');

console.log(person1.name); // Output: "John"
console.log(person2.name); // Output: "Mary"

In this example, the createPerson() function takes a single argument, name, and returns a new object with a name property set to the value of the name argument. The function is called twice with different arguments, resulting in two different objects being created.

Factory functions can be used to create a wide variety of objects or values, and can be especially useful when you need to create multiple similar objects or values that may have slightly different properties or behaviors.

More Exammples: A factory function that generates graduates 

```
function createGraduate(name, degree) {
  return {
    name: name,
    degree: degree,
    sayHello: function() {
      console.log(`Hello, my name is ${this.name} and I have a degree in ${this.degree}.`);
    }
  };
}

function createGraduates(schoolName, graduates) {
  return graduates.map(graduate => createGraduate(graduate.name, graduate.degree));
}

const schoolGraduates = createGraduates('My School', [
  { name: 'John', degree: 'Computer Science' },
  { name: 'Mary', degree: 'Business Administration' },
  { name: 'Alice', degree: 'Art History' }
]);

schoolGraduates.forEach(graduate => graduate.sayHello());

// Output:
// "Hello, my name is John and I have a degree in Computer Science."
// "Hello, my name is Mary and I have a degree in Business Administration."
// "Hello, my name is Alice and I have a degree in Art History."

```

> Classes and Factory Functions Relation 

```
class Student{
    constructor(name, degree)
    {
        this.name = name; 
        this.degree= degree;
    }
    sayHello()
    {
         console.log(`Hello, my name is ${this.name} and I have a degree in ${this.degree}.`);
    }
}

function createGraduate(name, degree)
{
    return new Student(name, degree);
}

const student1 = createGraduate('Sulav', 'Machine Learning');
const student2 = createGraduate('Sam', 'CIT')

student1.sayHello(); 
student2.sayHello(); 

```

---

## Callback Functions 

A callback function is a function that is passed as an argument to another function, and is executed after the outer function has completed. Callback functions are a common pattern in JavaScript, and are used to handle asynchronous events or to perform additional tasks after a function has completed.

Here is an example of a simple callback function:

```
function greet(name, callback) {
  console.log(`Hello, ${name}!`);
  callback();
}

function sayGoodbye() {
  console.log('Goodbye!');
}

greet('John', sayGoodbye);
// Output: "Hello, John!"
//         "Goodbye!"

```
In this example, the greet() function takes a name and a callback function as arguments, and logs a greeting message to the console. It then calls the callback function. The sayGoodbye() function is passed as the callback function, and is executed after the greet() function has completed.

Callback functions are often used in JavaScript to handle asynchronous events, such as when making HTTP requests or waiting for a user to interact with a page. For example:

```
function makeRequest(url, callback) {
  // Make the request and get the response

```

Here are few more examples of callback function:

1. Handling User Input 

    ```
    function handleInput(event, callback) {
    console.log(`You entered: ${event.target.value}`);
    callback();
    }

    function clearInput() {
    document.getElementById('input').value = '';
    }

    document.getElementById('input').addEventListener('input', event => handleInput(event, clearInput));


    ```
    In this example, the handleInput() function takes an event object and a callback function as arguments, and logs the value of the input element to the console. It then calls the callback function. The clearInput() function is passed as the callback function, and is executed after the handleInput() function has completed.

2. HTTP Request 

    ```
    function makeRequest(url, callback) {
    fetch(url)
        .then(response => response.json())
        .then(data => callback(data));
    }

    function displayData(data) {
    console.log(data);
    }

    makeRequest('http://example.com/api/data', displayData);

    ```
    In this example, the makeRequest() function takes a URL and a callback function as arguments, and makes an HTTP request using the fetch() function. When the response is received, it is parsed as JSON and passed to the callback function. The displayData() function is passed as the callback function, and is executed after the makeRequest() function has completed, with the received data as an argument.

3. Executing After Delay

    ```
    function doSomethingAfterDelay(callback, delay) {
        setTimeout(callback, delay);
    }

    function sayHello() {
        console.log('Hello!');
    }

    doSomethingAfterDelay(sayHello, 1000);
    // Output: "Hello!" (after a 1 second delay)

    ```

--- 

## Closure 

A closure is a function that has access to the variables and scope of its outer function, even after the outer function has completed. Closures are created when a function is defined inside another function, and allow the inner function to access the variables and scope of the outer function.

Here is an example of a closure in JavaScript:

```
function outerFunction(x) {
  let y = x;

  function innerFunction() {
    console.log(y);
  }

  return innerFunction;
}

const inner = outerFunction(5);
inner(); // Output: 5

```

In this example, the outerFunction() function takes a single argument, x, and defines a variable y with the value of x. It then defines an innerFunction() function, which logs the value of y to the console. The outerFunction() function returns the innerFunction() function, which is assigned to a variable called inner.

When the inner() function is called, it has access to the variables and scope of the outerFunction(), even though the outerFunction() has already completed. In this case, the innerFunction() logs the value of y, which is 5.

Closures are often used in JavaScript to create private variables or to create functions with specific context or state. For example, you might use a closure to create a function that has access to a specific set of data, or to create a function that can only be called a certain number of times. Closures can help you write more modular, reusable code, and can be a powerful tool in your JavaScript programming toolkit.


Here are few more examples to understand closure

```
function createClassGreeting(className) {
  const students = ['John', 'Mary', 'Alice', 'Bob'];

  return function() {
    students.forEach(student => console.log(`Hello, ${student}! You are enrolled in ${className}.`));
  };
}

const greetCSE341Students = createClassGreeting('CSE 341');
greetCSE341Students();

// Output:
// "Hello, John! You are enrolled in CSE 341."
// "Hello, Mary! You are enrolled in CSE 341."
// "Hello, Alice! You are enrolled in CSE 341."
// "Hello, Bob! You are enrolled in CSE 341."


```

In this example, the createClassGreeting() function takes a class name as an argument, and defines an array of students. It returns a function that iterates over the array of students and logs a greeting message to the console for each student.

The returned function has access to the className and students variables through the closure, even after the createClassGreeting() function has completed. When the returned function is called, it uses the className and students variables to generate the greeting messages for each student.
---

## Currying 

Currying is the process of transforming a function with multiple arguments into a sequence of functions that each take a single argument. This is often used to create more specialized or reusable functions by binding some of the arguments to the function ahead of time.

Here is an example of a function that uses currying:

function add(x) {
  return function(y) {
    return x + y;
  }
}

const add10 = add(10);
console.log(add10(5));  // Output: 15
console.log(add10(15));  // Output: 25

In this example, the add function takes a single argument x and returns a new function that takes a single argument y. When the returned function is called with an argument, it adds x and y together and returns the result.

We can then use currying to create a new function add10 by calling add with the argument 10. This creates a new function that will always add 10 to its argument. We can then call add10 with different arguments to get the result of adding 10 to those arguments.

Currying can be useful for creating specialized functions or for partial application of arguments to a function. It can also be used to create more readable and expressive code by breaking down a function into smaller, more focused functions.

More Exmaple

```
const fetchData = endpoint => params => {
  return fetch(`${endpoint}?${new URLSearchParams(params)}`)
    .then(response => response.json());
};

const fetchUserData = fetchData('https://my-api.com/users');
const fetchProductData = fetchData('https://my-api.com/products');

fetchUserData({id: 123}).then(user => console.log(user));
fetchProductData({id: 456}).then(product => console.log(product));


```
In this example, we have a fetchData function that takes an endpoint as its first argument and returns a new function that takes params as its argument. When the returned function is called with params, it makes a request to the specified endpoint with the provided parameters and returns the JSON response.

We can then use currying to create specialized versions of the fetchData function for fetching user data and product data by calling the fetchData function with the corresponding endpoint. We can then call these specialized functions with the desired parameters to make requests for specific data.

This approach allows us to reuse the same fetch logic for different endpoints, while also making it easier to read and understand the code by breaking it down into smaller, more focused functions.