# Class 

A class is a blueprint for creating objects that have the same properties and methods. Classes are a feature of the ECMAScript 2015 (ES6) version of JavaScript, and provide a way to define reusable and modular code that can be used to create objects with similar characteristics.

Classes are defined using the class keyword, followed by the name of the class and a pair of curly braces. The body of the class can contain methods, which are functions that define the behavior of the class, and properties, which are variables that hold data associated with the class.

Here is an example of a simple class that defines a Person class with a name property and a greet() method:

```
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}


```
---

## Pillars of a class  

1. Constructor: The constructor is a special method that is called when a new object is created from the class. It is used to initialize the object and to set up any required properties or state. The constructor is defined using the constructor keyword, and is invoked using the new operator.

2. Properties: Properties are variables that hold data associated with the class. They can be defined as instance properties, which are unique to each object created from the class, or as static properties, which are shared by all objects created from the class. Properties are defined using the this keyword, and can be accessed and modified using the dot notation or the square bracket notation.

3. Methods: Methods are functions that define the behavior of the class. They can be defined as instance methods, which are unique to each object created from the class, or as static methods, which are shared by all objects created from the class. Methods are defined using the function syntax, and can be called on objects using the dot notation or the square bracket notation.

---

## Pillars of Object-Oriented-Programming

1. Encapsulation: Encapsulation is the process of bundling data and methods that operate on that data within a single unit, or object. It allows you to hide the implementation details of a class from other parts of your code, and to expose only the interface that is necessary for interacting with the object. Encapsulation helps to improve the maintainability and reusability of your code, and to prevent unintended side effects from external changes.

```
class Person {
constructor(name, age) {
    this._name = name;
    this._age = age;
}

get name() {
    return this._name;
}

set name(newName) {
    this._name = newName;
}

get age() {
    return this._age;
}

set age(newAge) {
    this._age = newAge;
}
}

const john = new Person('John', 30);

console.log(john.name); // Output: "John"
console.log(john.age); // Output: 30

john.name = 'Jane';
john.age = 35;

console.log(john.name); // Output: "Jane"
console.log(john.age); // Output: 35

```
    In this example, the Person class has a name property and an age property, which are private variables that are defined using the underscore notation (_name and _age). The class also has get and set methods for accessing and modifying these properties, which are defined using the get and set keywords.

    By using the get and set methods, you can control how the name and age properties are accessed and modified, and you can hide the implementation details of these properties from the rest of your code. For example, you can add validation or formatting logic to the set methods, or you can use the get methods to compute derived values from the name and age properties.


2. Abstraction: Abstraction is the process of exposing only the relevant and essential features of an object, and hiding the implementation details. It allows you to focus on the essential characteristics of an object, and to ignore the unnecessary or irrelevant details. Abstraction helps to simplify the design and implementation of your code, and to make it more flexible and adaptable to change.
```
class PaymentMethod {
  constructor(name) {
    this.name = name;
  }

  charge(amount) {
    throw new Error('charge() method must be implemented by a subclass');
  }
}

class CreditCard extends PaymentMethod {
  constructor(name, cardNumber, expirationDate) {
    super(name);
    this.cardNumber = cardNumber;
    this.expirationDate = expirationDate;
  }

  charge(amount) {
    // Charge the credit card using the cardNumber and expirationDate
  }
}

class PayPal extends PaymentMethod {
  constructor(name, email, password) {
    super(name);
    this.email = email;
    this.password = password;
  }

  charge(amount) {
    // Charge the PayPal account using the email and password
  }
}

class Cash extends PaymentMethod {
  charge(amount) {
    // Nothing to do, the payment has already been made in cash
  }
}

const paymentMethod = new CreditCard('John', '4111 1111 1111 1111', '01/23');
paymentMethod.charge(100);

```
    In this example, the PaymentMethod class is an abstract class that defines a common interface for different types of payment methods. It has a name property and a charge() method, which is an abstract method that does not have a concrete implementation.

    The CreditCard, PayPal, and Cash classes are subclasses of the PaymentMethod class, and they all implement the charge() method with a concrete implementation. The CreditCard class has additional properties for storing the card number and expiration date, the PayPal class has additional properties for storing the email and password, and the Cash class does not have any additional properties.

    By using abstraction, you can define a common interface for different types of payment methods, and you can hide the implementation details of each payment method behind the interface. This allows you to create more flexible and adaptable code, and to create more reusable and modular components.

    For example, you can create a function that takes a payment method as an argument, and uses the charge() method to process the payment, without knowing the specific type of the payment method:
    ```
    function processPayment(paymentMethod, amount) {
        paymentMethod.charge
    }); 

    ```

3. Inheritance: Inheritance is a mechanism that allows one class to inherit the properties and methods of another class. It allows you to create a hierarchy of classes, where more specialized classes can inherit the characteristics and behavior of more general classes. Inheritance allows you to reuse and modify the code of existing classes, and to create new classes that are derived from existing ones.

```
class VendingMachine {
  constructor(name, location) {
    this.name = name;
    this.location = location;
    this.inventory = [];
  }

  addProduct(product) {
    this.inventory.push(product);
  }

  getInventory() {
    return this.inventory;
  }
}

class SoftDrinkVendingMachine extends VendingMachine {
  constructor(name, location) {
    super(name, location);
  }

  dispenseProduct(product) {
    const index = this.inventory.indexOf(product);
    if (index !== -1) {
      this.inventory.splice(index, 1);
      console.log(`Dispensing ${product.name}...`);
    } else {
      console.log(`Sorry, ${product.name} is out of stock.`);
    }
  }
}

class SoftDrink {
  constructor(name, flavor) {
    this.name = name;
    this.flavor = flavor;
  }
}

const vendingMachine = new SoftDrinkVendingMachine('Soda Machine', 'Lobby');
vendingMachine.addProduct(new SoftDrink('Coke', 'Cola'));
vendingMachine.addProduct(new SoftDrink('Sprite', 'Lemon-Lime'));

console.log(vendingMachine.getInventory());
// Output: [{ name: 'Coke', flavor: 'Cola' }, { name: 'Sprite', flavor: 'Lemon-Lime' }]

vendingMachine.dispenseProduct(new SoftDrink('Coke', 'Cola'));
// Output: "Dispensing Coke..."

console.log(vendingMachine.getInventory());
// Output: [{ name: 'Sprite', flavor: 'Lemon-Lime' }]

vendingMachine.dispenseProduct(new SoftDrink('Coke', 'Cola'));
// Output: "Sorry, Coke is out of stock."

```
    In this example, the VendingMachine class is a base class that defines a common interface for vending machines. It has a name property, a location property, and an inventory property that stores an array of products. It also has addProduct() and getInventory() methods for adding and accessing the products in the inventory.

    The SoftDrinkVendingMachine class is a subclass of the VendingMachine class, and it inherits the name, location, and inventory properties from the base class. It also has a dispenseProduct() method that dispenses a product from the inventory, if it is available
4. Polymorphism: Polymorphism is the ability of a single interface to operate on multiple data types. It allows you to write code that can handle different types of objects in a uniform way, without the need to know the specific type of each object at runtime. Polymorphism allows you to write more flexible and adaptable code, and to create more reusable and modular components.

```
class Shape {
  constructor(color) {
    this.color = color;
  }

  draw() {
    throw new Error('draw() method must be implemented by a subclass');
  }
}

class Circle extends Shape {
  constructor(color, radius) {
    super(color);
    this.radius = radius;
  }

  draw() {
    console.log(`Drawing a ${this.color} circle with radius ${this.radius}...`);
  }
}

class Rectangle extends Shape {
  constructor(color, width, height) {
    super(color);
    this.width = width;
    this.height = height;
  }

  draw() {
    console.log(`Drawing a ${this.color} rectangle with width ${this.width} and height ${this.height}...`);
  }
}

function drawShapes(shapes) {
  shapes.forEach(shape => shape.draw());
}

const shapes = [new Circle('red', 5), new Rectangle('blue', 10, 20)];
drawShapes(shapes);
// Output: "Drawing a red circle with radius 5..."
//         "Drawing a blue rectangle with width 10 and height 20..."


```

    In this example, the Shape class is a base class that defines a common interface for different types of shapes. It has a color property and a draw() method, which is an abstract method that does not have a concrete implementation.

    The Circle and Rectangle classes are subclasses of the Shape class, and they both implement the draw() method with their own concrete implementation. The Circle class has additional properties for storing the radius, and the Rectangle class has additional properties for storing the width and height.

    The drawShapes() function is a polymorphic function that takes an array of shapes as an argument, and uses the draw() method of each shape to draw it. Because the draw() method has different implementations for different types of shapes, the function can draw different types of shapes in a polymorphic way.

    By using polymorphism, you can create a flexible and adaptable code, and you can create more reusable and modular components. You can define a common interface for different types of objects, and you can use the interface to interact with the objects in a polymorphic way, without knowing their specific type. This allows you to create more flexible and adaptable code, and to create more reusable and modular components.

These pillars form the foundation of the object-oriented programming (OOP) model in JavaScript, and allow you to organize and structure your code in a way that is flexible, reusable, and maintainable. By using encapsulation, abstraction, inheritance, and polymorphism, you can create a clear and consistent interface for interacting with objects, and create objects with similar characteristics and behavior.


A real world Example that leverages all the OOPs concept 

```
class Vehicle {
  constructor(make, model) {
    this._make = make;
    this._model = model;
  }
  
  get make() {
    return this._make;
  }
  
  set make(make) {
    this._make = make;
  }
  
  get model() {
    return this._model;
  }
  
  set model(model) {
    this._model = model;
  }
  
  start() {
    console.log(`Starting vehicle: ${this._make} ${this._model}`);
  }
  
  stop() {
    console.log(`Stopping vehicle: ${this._make} ${this._model}`);
  }
}

class Car extends Vehicle {
  constructor(make, model, numDoors) {
    super(make, model);
    this._numDoors = numDoors;
  }
  
  get numDoors() {
    return this._numDoors;
  }
  
  set numDoors(numDoors) {
    this._numDoors = numDoors;
  }
  
  start() {
    console.log(`Starting car: ${this._make} ${this._model}`);
  }
}

class Motorcycle extends Vehicle {
  start() {
    console.log(`Starting motorcycle: ${this._make} ${this._model}`);
  }
}

const car = new Car('Toyota', 'Camry', 4);
car.start();  // Output: "Starting car: Toyota Camry"
car.stop();   // Output: "Stopping vehicle: Toyota Camry"

const motorcycle = new Motorcycle('Honda', 'Civic');
motorcycle.start();  // Output: "Starting motorcycle: Honda Civic"
motorcycle.stop();   // Output: "Stopping vehicle: Honda Civic"

const vehicle = new Vehicle('Ford', 'F-150');
vehicle.start();  // Output: "Starting vehicle: Ford F-150"
vehicle.stop();   // Output: "Stopping vehicle: Ford F-150"

const vehicles = [car, motorcycle, vehicle];
for (const v of vehicles) {
  console.log(`Make: ${v.make}, Model: ${v.model}`);
}

```

In this example, we have a base Vehicle class that has a make and a model and can be started and stopped. The Vehicle class also has getters and setters to allow for encapsulation of the _make and _model properties.

We then have two subclasses: Car and Motorcycle, both of which inherit from Vehicle using the extends keyword. The Car class has an additional numDoors property, and both the Car and Motorcycle classes override the start method from the Vehicle class to provide their own implementation.

Finally, we create instances of each of the classes and demonstrate polymorphism by storing them in an array and calling the same methods on each of them.