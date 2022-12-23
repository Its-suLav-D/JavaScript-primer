# HTTP Requests 

HTTP (Hypertext Transfer Protocol) is a protocol used to send and receive data over the internet. It is the foundation of the World Wide Web, and is used by web browsers and servers to communicate with each other.

In JavaScript, you can use the XMLHttpRequest object or the fetch() function to make HTTP requests to a server. These requests can be used to retrieve data from a server, or to send data to a server for processing.

To make an HTTP request in JavaScript, you first create an instance of XMLHttpRequest or call fetch(), and then specify the type of request you want to make (e.g. GET, POST, PUT, DELETE) and the URL of the server you want to send the request to. You can also specify additional options, such as the data you want to send with the request or the headers you want to include.

Once the request has been sent, the server will process it and send back a response. In JavaScript, you can use event listeners or Promises to handle the response and take appropriate action based on the data received.

For example, you might use an HTTP request to retrieve a list of products from an e-commerce API, or to send a form submission to a server for processing. HTTP requests are a key part of modern web development, and are used in many different types of applications.


--- --------------------------------

## Fetch() Method - Preferred 

The fetch() function in JavaScript is a modern, Promise-based API for making HTTP requests. It provides a simple and flexible way to retrieve data from a server, and is supported in all modern browsers.

When you call fetch(), you can pass a number of options to customize the request. These options are specified as an object in the second argument to fetch(). Some of the options you can specify include:

    - method: The HTTP method to use for the request (e.g. GET, POST, PUT, DELETE).
    - headers: An object containing headers to send with the request.
    - body: The body of the request. This can be a string, a Blob, a FormData object, or any other object that can be used as the body of an HTTP request.
    - mode: The mode to use for the request (e.g. "cors", "no-cors", "same-origin").
    - cache: The cache mode to use for the request (e.g. "default", "no-cache", "reload", "force-cache", "only-if-cached").
    - credentials: The credentials mode to use for the request (e.g. "omit", "same-origin", "include").
    - redirect: The redirect mode to use for the request (e.g. "follow", "error", "manual").

Here's an example of how to use the fetch() function with some of these options:

```

fetch('http://example.com/api/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    name: 'John',
    age: 30
  }),
  mode: 'cors',
  cache: 'no-cache',
  credentials: 'include',
  redirect: 'follow'
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```
This example makes a POST request to the /api/data endpoint, with a JSON-formatted body and the specified headers and options. The response is then parsed as JSON and logged to the console.

--- 

## XMLHttpRequest 

XMLHttpRequest is a built-in object in JavaScript that allows you to send HTTP requests to a server and receive responses. It is a fundamental part of the web, and is used by web browsers and servers to communicate with each other.

To use XMLHttpRequest, you first create an instance of the object, and then call its open() method to specify the type of request you want to make (e.g. GET, POST, PUT, DELETE) and the URL of the server you want to send the request to. You can also specify additional options, such as the data you want to send with the request or the headers you want to include.

Once the request has been opened, you can call the send() method to actually send the request to the server. The server will then process the request and send back a response, which you can handle using event listeners or callback functions.

Here's an example of how to use XMLHttpRequest to send a GET request and log the response:
```
const request = new XMLHttpRequest();
request.open('GET', 'http://example.com/api/data');
request.onload = () => {
  console.log(request.response);
};
request.send();

```

This example creates a new XMLHttpRequest object, opens a GET request to the /api/data endpoint, and sets an onload event listener to log the response to the console. When the send() method is called, the request is sent to the server, and the response is logged when it is received.

XMLHttpRequest is a powerful and flexible API, and is widely used in modern web development. It is supported in all modern browsers.

--- 

## Fetch with Async / Await 

```
async function getData() {
  try {
    const response = await fetch('http://example.com/api/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

getData();

```

In this example, the getData() function is defined as async, which means it returns a Promise that is resolved when the function is complete. The await keyword is used to wait for the Promise returned by fetch() to resolve, and the try and catch blocks are used to handle any errors that may occur.

The fetch() function is called with the URL of the server to send the request to, and the response is passed to the response.json() function to parse the response as JSON. The resulting data is then logged to the console.

If an error occurs at any point (e.g. if the server returns a 404 error or the response cannot be parsed as JSON), it will be caught in the catch block and logged to the console.

Using async and await can make it easier to write asynchronous code that is easier to read and understand, as it allows you to write code that looks and behaves more like synchronous code.