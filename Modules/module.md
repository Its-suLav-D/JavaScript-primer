# Module

A module is a self-contained piece of code that exports a specific set of features or values, and can be imported and used by other modules. Modules allow you to organize your code into reusable chunks and can help you to better manage the dependencies and interactions between different parts of your application.

There are several ways to create and use modules in JavaScript. One common approach is to use the export and import statements, which are part of the ECMAScript (ES) module system.

Here is an example of exporting a value from a module:
```
// math.js

export const PI = 3.14;

export function calculateCircumference(radius) {
  return 2 * PI * radius;
}

```

In this example, the math.js module exports the PI constant and the calculateCircumference() function, which can be imported and used by other modules.

Here is an example of importing a value from a module:
```
// main.js

import { PI, calculateCircumference } from './math';

console.log(PI); // Output: 3.14
console.log(calculateCircumference(5)); // Output: 31.4
```
In this example, the main.js module imports the PI constant and the calculateCircumference() function from the math module, and uses them to perform some calculations.

You can also use the export default statement to specify a default export for a module, which can be imported using the import statement without the curly braces. For example:
```
// math.js

export default function add(x, y) {
  return x + y;
}
```

```
// main.js

import add from './math';

console.log(add(2, 3)); // Output: 5

```

In this example, the math.js module exports a default function that can be imported and used by the main.js module without the need to specify a named export.

Modules can help you to organize and modularize your code, and can make it easier to manage dependencies and interactions between different parts of your application. They can also help you to create reusable components that can be shared and imported by multiple modules, making it easier to build and maintain complex applications.

---

## Immediately-invoked Function Expression (IIFE 

In JavaScript, an immediately-invoked function expression (IIFE) is a function that is defined and immediately executed, without being stored in a variable or assigned to a property. IIFEs are often used to create private scopes, to hide variables and functions from the global scope, and to prevent name collisions with other variables and functions.

An IIFE is defined using the function expression syntax, followed by parentheses and a pair of curly braces. The function is invoked by adding a pair of parentheses after the function definition.

```
(function() {
  let secret = '123456';

  function getSecret() {
    return secret;
  }

  function setSecret(newSecret) {
    secret = newSecret;
  }

  window.secretModule = {
    getSecret: getSecret,
    setSecret: setSecret
  };
})();

console.log(secretModule.getSecret()); // Output: "123456"
secretModule.setSecret('abcdef');
console.log(secretModule.getSecret()); // Output: "abcdef"


```
In this example, the IIFE creates a private scope and defines the secret variable and the getSecret() and setSecret() functions. It then exports these functions to the global scope by assigning them to the secretModule object, which can be accessed by other parts of the application.

The secret variable is not accessible from the global scope, and cannot be modified directly. Instead, it can only be accessed and modified using the getSecret() and setSecret() functions, which are exported by the IIFE. This allows you to create a secure, private scope for storing sensitive data, and to control access to that data using well-defined interfaces.

IIFEs can be a useful tool for organizing and modularizing your code, and for creating private scopes that can help you to manage dependencies and interactions between different parts of your application. They can also help you to prevent name collisions and to keep