# Generators and Iterators 

A generator is a special type of function that can be paused and resumed at any time, allowing you to execute code in a controlled, sequential manner. Generators are defined using the function* syntax, and can be used to create iterators or to implement asynchronous programming techniques.

Here is an example to implement a async task queue 

```
function* runTasks(tasks) {
  for (let task of tasks) {
    yield executeTask(task);
  }
}

function executeTask(task) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log(`Executing task: ${task}`);
      resolve();
    }, 1000);
  });
}

const tasks = ['Task 1', 'Task 2', 'Task 3'];
const taskRunner = runTasks(tasks);

function runNextTask() {
  let result = taskRunner.next();
  if (!result.done) {
    result.value.then(() => runNextTask());
  }
}

runNextTask();


```

In this example, the runTasks() generator function takes an array of tasks as an argument, and yields a promise for each task that is returned by the executeTask() function. The executeTask() function simulates the execution of a task by returning a promise that resolves after a 1 second delay.

The runNextTask() function uses the generator object returned by the runTasks() generator function to execute the tasks in sequence. It calls the next() method on the generator object to retrieve the next task, and waits for the task's promise to resolve before calling itself again to execute the next task. This process continues until all tasks have been executed, or until the generator function has completed.

Generators can be a useful tool for creating asynchronous programs that are easy to understand and maintain. They can help you write code that is more modular and reusable, and can make it easier to manage the flow of data in your programs.

More Examples

```
function* greetStudents(students) {
  for (let student of students) {
    yield `Hello, ${student.name}! You are enrolled in CSE 341.`;
    yield `Your assignment for this week is ${student.assignment}.`;
  }
}

const students = [
  { name: 'John', assignment: 'Homework 1' },
  { name: 'Mary', assignment: 'Homework 2' },
  { name: 'Alice', assignment: 'Homework 3' },
  { name: 'Bob', assignment: 'Homework 4' }
];

const studentGreeting = greetStudents(students);

console.log(studentGreeting.next().value); // Output: "Hello, John! You are enrolled in CSE 341."
console.log(studentGreeting.next().value); // Output: "Your assignment for this week is Homework 1."
console.log(studentGreeting.next().value); // Output: "Hello, Mary! You are enrolled in CSE 341."
console.log(studentGreeting.next().value); // Output: "Your assignment for this week is Homework 2."
console.log(studentGreeting.next().value); // Output: "Hello, Alice! You are enrolled in CSE 341."
console.log(studentGreeting.next().value

```

---

## Iterator 

An iterator is an object that allows you to access and iterate over the elements of a collection, such as an array or an object. An iterator has a next() method that returns the next element in the collection, along with a done property that indicates whether the iterator has reached the end of the collection.

Iterators are typically used with the for-of loop, which automatically calls the next() method on the iterator and terminates the loop when the done property is true.

Here is an example of using an iterator to iterate over the elements of an array:

```
const fruits = ['apple', 'banana', 'mango'];

const fruitIterator = fruits[Symbol.iterator]();
console.log(fruitIterator.next()); // Output: { value: "apple", done: false }
console.log(fruitIterator.next()); // Output: { value: "banana", done: false }
console.log(fruitIterator.next()); // Output: { value: "mango", done: false }
console.log(fruitIterator.next()); // Output: { value: undefined, done: true }


```

In this example, the fruits array has a built-in iterator that can be accessed using the Symbol.iterator symbol. The iterator's next() method returns an object with a value property that holds the current element in the array, and a done property that indicates whether the iterator has reached the end of the array.

You can also create your own iterators