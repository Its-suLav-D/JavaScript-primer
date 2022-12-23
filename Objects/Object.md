# Objects 

Objects are core data structure in javascript. Particularly, it is an unorded collection of key-value pairs. You can use objects to store data, ogranize code, and represent real-world entities. It is crucial to retain that Object are reference values

In javascript, values can be either primite values or reference values: 

Reference values, are complex data types that represent a reference to a value, rather than the value itself. The referenve values in JavaScript are: 

    - Objects (arrays, function, and classes)
    - Maps 
    - Sets 
    - WeakMaps 
    - WeakSets 

Here is an example of an object in JavaScript:

```
let object = {
  key1: 'value1',
  key2: 'value2',
  key3: 'value3'
};


```

In this example, the object has three properties: key1, key2, and key3. Each property has a corresponding value, which can be a primitive data type (such as a string or number), or a more complex data type (such as an array or another object).

You can access the properties of an object using dot notation or bracket notation, like this:

```
console.log(object.key1); // Output: 'value1'
console.log(object['key2']); // Output: 'value2'

```
You can also add, remove, or modify the properties of an object using dot notation or bracket notation, like this:

```
object.key4 = 'value4';
delete object.key3;
object['key2'] = 'new value';

```
Objects are often used to store data in the form of key-value pairs. For example, you might use an object to represent a person, like this:

```
let person = {
  name: 'John',
  age: 10,
  occupation: 'developer'
};

```
You can also use objects to store functions, which are known as methods. For example:

```
let calculator = {
  add: function(x, y) {
    return x + y;
  },
  subtract: function(x, y) {
    return x - y;
  }
};

console.log(calculator.add(1, 2)); // Output: 3
console.log(calculator.subtract(5, 3)); // Output: 2

```

> Objects are fundamental part of javascript and are used extensively in modern JavaScript Programming.


## Object Spread Operator 

The spread operator (...) in JavaScript can be used with objects to create a new object that combines the properties of the original object with additional properties or values. This is often referred to as object spreading or object rest/spread syntax.

Here is an example of how to use the spread operator with an object:

```
let object1 = {
  key1: 'value1',
  key2: 'value2'
};

let object2 = {
  key3: 'value3',
  ...object1
};

console.log(object2);
// Output: {key3: "value3", key1: "value1", key2: "value2"}
```

In this example, the object2 is created by spreading the properties of object1 into a new object. The result is an object that contains the properties of both object1 and object2.

You can also use the spread operator to override properties of the original object, like this:

``` 
let object1 = {
  key1: 'value1',
  key2: 'value2'
};

let object2 = {
  ...object1,
  key1: 'new value'
};

console.log(object2);
// Output: {key1: "new value", key2: "value2"}
``` 
In this example, the key1 property of object1 is overridden by the key1 property of object2.

You can also use the spread operator to merge multiple objects into a single object, like this:

```
let object1 = {
  key1: 'value1'
};

let object2 = {
  key2: 'value2'
};

let object3 = {
  key3: 'value3'
};

let mergedObject = {
  ...object1,
  ...object2,
  ...object3
};

console.log(mergedObject);
// Output: {key1: "value1", key2: "value2", key3: "value3"}


```

## Object Assign 

Object.assign() is a method in JavaScript that is used to copy the values of all enumerable own properties from one or more source objects to a target object. It returns the target object.

Here are some examples of how to use Object.assign():

``` 
let object1 = {
  key1: 'value1',
  key2: 'value2'
};

let object2 = {
  key3: 'value3'
};

let targetObject = Object.assign({}, object1, object2);

console.log(targetObject);
// Output: {key1: "value1", key2: "value2", key3: "value3"}

Example 2. 

let object1 = {
  key1: 'value1'
};

let object2 = {
  key2: 'value2'
};

let object3 = {
  key3: 'value3'
};

let mergedObject = Object.assign({}, object1, object2, object3);

console.log(mergedObject);
// Output: {key1: "value1", key2: "value2", key3: "value3"}


```
>  It is a useful method for copying and merging objects in JavaScript, and it is often used in combination with other features such as destructuring and the rest/spread operator (...).

## Object destructing 

Object destructuring is a syntax in JavaScript that allows you to extract properties from an object and assign them to variables. It is a convenient way to extract data from objects and can be used in combination with other features such as the spread operator (...) and the rest/spread operator (...).

Here is an example of object destructuring:

```
let object = {
  key1: 'value1',
  key2: 'value2',
  key3: 'value3'
};

let {key1, key2} = object;

console.log(key1); // Output: 'value1'
console.log(key2); // Output: 'value2'
```


You can also use object destructuring to assign the extracted properties to variables with different names, like this:

```
let {key1: newKey1, key2: newKey2} = object;

console.log(newKey1); // Output: 'value1'
console.log(newKey2); // Output: 'value2'
```
You can also use object destructuring in combination with the spread operator (...) to extract some properties and spread the rest into a new object, like this:

```
let {key1, ...rest} = object;

console.log(key1); // Output: 'value1'
console.log(rest); // Output: {key2: "value2", key3: "value3"}
```

## Understanding this keyword 

In JavaScript, the this keyword refers to the current object that is being executed. It is a special keyword that is used to access properties and methods of the current object.

The value of this depends on how the function is called, and it can change depending on the context.

Here is an example of how this is used in a simple function:

```
function greet() {
  console.log(`Hello, ${this.name}!`);
}

let person = {
  name: 'John',
  greet: greet
};

person.greet(); // Output: "Hello, John!"
```
In this example, the greet function is called as a method of the person object, so the value of this inside the function is the person object. As a result, the name property of the person object is accessed and logged to the console.

The value of this can also be determined by how the function is called. For example:

``` 
let object = {
  name: 'John'
};

function greet() {
  console.log(`Hello, ${this.name}!`);
}

greet.call(object); // Output: "Hello, John!"

```
In this example, the call() method is used to call the greet function with a specific value for this. The call() method accepts an object as its first argument, which is used as the value of this inside the function.

The value of this can also be bound to a specific value using the bind() method:

``` 
let object = {
  name: 'John'
};

function greet() {
  console.log(`Hello, ${this.name}!`);
}

let boundGreet = greet.bind(object);
boundGreet(); // Output: "Hello, John!"
``` 
In this example, the bind() method is used to create a new function, boundGreet, that has its value of this permanently bound to the object.


> We used few keywords like call, apply and bind, lets explore what each of them works 

1. Call()

    The call() method takes a function and an argument list (a comma-separated list of arguments) as its arguments, and calls the function with the specified arguments and the value of this set to the first argument.

    Here is an example of how to use the call() method:

    ```
    let object = {
    name: 'John'
    };

    function greet(greeting) {
    console.log(`${greeting}, ${this.name}!`);
    }

    greet.call(object, 'Hello'); // Output: "Hello, John!"

    ```
    In this example, the call() method is used to call the greet function with the object as the value of this and the 'Hello' string as the greeting argument.

2. Apply()

    The apply() method is similar to the call() method, but it takes a function and an array of arguments as its arguments, rather than a list of arguments.

    Here is an example of how to use the apply() method:

    ``` 
    let object = {
    name: 'John'
    };

    function greet(greeting) {
    console.log(`${greeting}, ${this.name}!`);
    }

    greet.apply(object, ['Hello']); // Output: "Hello, John!"
    ```

3. Bind()

In JavaScript, the bind() method is a function method that creates a new function with a specific value for this. The new function is called a bound function.

The bind() method takes an object as its first argument, which becomes the value of this inside the bound function. It also accepts additional arguments that are passed to the bound function as arguments when it is called.

Here is an example of how to use the bind() method:

```
let object = {
  name: 'John'
};

function greet(greeting) {
  console.log(`${greeting}, ${this.name}!`);
}

let boundGreet = greet.bind(object, 'Hello');
boundGreet(); // Output: "Hello, John!"

```

In this example, the bind() method is used to create a new function, boundGreet, that has its value of this permanently bound to the object. The 'Hello' string is also passed as an argument to the bind() method, and it becomes the first argument of the bound function when it is called.

The bind() method is often used to create functions with a fixed value of this, which can be useful in cases where you need to pass a function as a callback or when you want to bind a method to an object.

Keep in mind that the bind() method does not call the function immediately. It only creates a new function that can be called later. To call the function immediately, you can use the call() or apply() methods.

For example:

```
let object = {
  name: 'John'
};

function greet(greeting) {
  console.log(`${greeting}, ${this.name}!`);
}

greet.call(object, 'Hello'); // Output: "Hello, John!"

```

## This and Arrow Function 

In JavaScript, the value of this inside an arrow function is determined by the surrounding context. Arrow functions do not have their own this value, so the value of this inside an arrow function is the same as the value of this in the surrounding context.

Here is an example of an arrow function that uses the this keyword:

```
let object = {
  name: 'John',
  greet: () => {
    console.log(`Hello, ${this.name}!`);
  }
};

object.greet(); // Output: "Hello, undefined!"
``` 
In this example, the greet method is an arrow function that uses the this keyword to access the name property of the surrounding object. However, because arrow functions do not have their own this value, the value of this inside the function is undefined.

To fix this, you can use a regular function instead of an arrow function:

``` 
let object = {
  name: 'John',
  greet: function() {
    console.log(`Hello, ${this.name}!`);
  }
};

object.greet(); // Output: "Hello, John!"

```
In this example, the greet method is a regular function that has its own this value, which is determined by the surrounding context. As a result, the name property of the object is accessed correctly.

> Keep in mind that arrow functions are often used as a concise syntax for functions, but they have some differences in behavior compared to regular functions, such as the way they handle the this keyword. It is important to understand these differences and use the appropriate type of function for your specific needs.

## Getters and Setters on Object 


In JavaScript, getters and setters are methods that allow you to get and set the value of an object property, respectively. They are a convenient way to define custom behavior for getting and setting the value of a property, and they can be used to create read-only or write-only properties, as well as to validate or transform the value of a property.

Here is an example of how to use getters and setters:

```
let object = {
  _property: 'value',
  get property() {
    return this._property;
  },
  set property(value) {
    this._property = value;
  }
};

console.log(object.property); // Output: "value"
object.property = 'new value';
console.log(object.property); // Output: "new value"
```
In this example, the property getter and setter are defined as methods with the get and set keywords, respectively. The getter is used to get the value of the _property property, and the setter is used to set the value of the _property property.

To use a getter or setter, you can use the property name as if it were a normal property, without calling the method. For example, object.property is used to get the value of the property getter, and object.property = value is used to set the value of the property setter.

Getters and setters can be used to create read-only or write-only properties by omitting the getter or setter, respectively. For example:

```
let object = {
  _property: 'value',
  get property() {
    return this._property;
  }
};

console.log(object.property); // Output: "value"
object.property = 'new value';
console.log(object.property); // Output: "value"
```

In this example, the property getter is defined, but the property setter is omitted, which makes the property a read-only property.

