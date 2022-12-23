# DOM Manipulation 

DOM manipulation refers to the process of modifying the structure, content, or style of an HTML or XML document using a programming language, typically JavaScript. The Document Object Model (DOM) is a programming interface for HTML and XML documents that represents the structure of a document as a tree of objects, with each object representing an element in the document.

Here are some examples of DOM manipulation using JavaScript:

    - Adding, deleting, or modifying elements in the document
    - Changing the text or attribute values of elements
    - Changing the styles of elements using CSS
    - Handling events such as clicks, hover, or form submissions

DOM manipulation is an important part of web development, as it allows you to dynamically update the content and layout of a webpage based on user input or other events. It is typically used in combination with other technologies such as HTML, CSS, and JavaScript libraries or frameworks to create interactive and responsive websites and applications.

There are a lot of functions and properties realted to dom manipulation,but these are some of the more common ones. 

### Getting Elements 

1. document.getElementById(id): Gets a single element based on its attribute 

```
<!-- HTML document -->
<p id="my-paragraph">Hello, World!</p>

<script>
  // Retrieve the element with the "my-paragraph" ID
  const paragraph = document.getElementById('my-paragraph');

  // Output the text of the element
  console.log(paragraph.innerText); // Output: "Hello, World!"
</script>


```



2. document.querySelector(selector): Gets a single element based on a selector. If multiple elements match the selector, return the first one. 

```
<!-- HTML document -->
<p>Hello, World!</p>
<p>Hello, DOM!</p>

<script>
  // Select the first `p` element
  const paragraph = document.querySelector('p');

  // Output the text of the element
  console.log(paragraph.innerText); // Output: "Hello, World!"
</script>


```


3. document.querySelectorAll(selector): Gets all elements matching a selector as a NodeList 

```
<!-- HTML document -->
<p>Hello, World!</p>
<p>Hello, DOM!</p>

<script>
  // Select all `p` elements
  const paragraphs = document.querySelectorAll('p');

  // Output the text of the elements
  paragraphs.forEach(paragraph => console.log(paragraph.innerText));
  // Output: "Hello, World!", "Hello, DOM!"
</script>
 
```

4. document.getElementsByTagName(tagName): Gets all elements with a specific tag as an HTML Collection. 

```
<!-- HTML document -->
<p>Hello, World!</p>
<p>Hello, DOM!</p>

<script>
  // Select all `p` elements
  const paragraphs = document.getElementsByTagName('p');

  // Output the text of the elements
  for (let i = 0; i < paragraphs.length; i++) {
    console.log(paragraphs[i].innerText);
  }
  // Output: "Hello, World!", "Hello, DOM!"
</script>


```

5. document.getElementsByClassName(className): Gets all elements with a specific class as an HTML collection. 

```
<!-- HTML document -->
<p class="error">An error occurred</p>
<div class="error">Something went wrong</div>

<script>
  // Select all elements with the "error" class
  const errors = document.getElementsByClassName('error');

  // Output the text of the elements
  for (let i = 0; i < errors.length; i++) {
    console.log(errors[i].innerText);
  }
  // Output: "An error occurred", "Something went wrong"
</script>

```

### Setting Attributes 

1. element.setAttribute('attribute', 'value'): Sets an HTML attribute to a specific value 

```
<!-- HTML document -->
<a id="my-link">Click here</a>

<script>
  // Retrieve the element
  const link = document.getElementById('my-link');

  // Set the `href` attribute
  link.setAttribute('href', 'https://www.example.com');
</script>


```

2. element.textContent: Used to get a text content of an element. 

```
<!-- HTML document -->
<p>Hello, <strong>World</strong>!</p>

<script>
  // Retrieve the element
  const paragraph = document.querySelector('p');

  // Get the text content of the element
  const text = paragraph.textContent;

  // Output the text content
  console.log(text); // Output: "Hello, World!"
</script>

```

3. element.getAttribute: used to get or set the value of an attribute on an element. It takes the name of the attribute as an argument, and returns the value of the attribute if it exists, or null if it does not.

```
<!-- HTML document -->
<a id="my-link" href="https://www.example.com">Click here</a>

<script>
  // Retrieve the element
  const link = document.getElementById('my-link');

  // Get the value of the `href` attribute
  const href = link.getAttribute('href');

  // Output the value of the attribute
  console.log(href); // Output: "https://www.example.com"
</script>

```

4. element.classList: used to manipulate the element's class names. It is a DOMTokenList object that provides methods for adding, removing, and checking for the presence of class names on an element.

```
<!-- HTML document -->
<div id="my-div">This is a div</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Add the "error" class to the element
  div.classList.add('error');
</script>


```

### Adding and Removing Elements 

1. document.createElement(tagName): Creates a new HTML element.  It takes the tag name of the element to be created as an argument, and returns a new element with that tag name.


```
<!-- HTML document -->
<div id="my-div"></div>

<script>
  // Create a new `p` element
  const paragraph = document.createElement('p');

  // Set the text content of the element
  paragraph.textContent = 'Hello, World!';

  // Append the element to the document
  document.getElementById('my-div').appendChild(paragraph);
</script>

// Result 

<div id="my-div">
  <p>Hello, World!</p>
</div>


```

2. document.createTextNode(text): Creates a text node as an alternative to settting textContent. It takes a string of text as an argument, and returns a new text node with that text.
```
<!-- HTML document -->
<div id="my-div"></div>

<script>
  // Create a new text node
  const textNode = document.createTextNode('Hello, World!');

  // Append the text node to the document
  document.getElementById('my-div').appendChild(textNode);
</script>

// Result 


<div id="my-div">Hello, World!</div>


```
3. document.createDocumentFragment(): A document fragment is a lightweight, in-memory representation of a part of a document. It can be used to build up a document structure in memory, and then insert the entire structure into the document at once, rather than inserting each element individually. This can be more efficient and performant than repeatedly inserting elements into the document one at a time.

```
<!-- HTML document -->
<div id="my-div"></div>

<script>
  // Create a new document fragment
  const fragment = document.createDocumentFragment();

  // Create some elements and text nodes
  const h1 = document.createElement('h1');
  h1.textContent = 'Hello, World!';
  const p = document.createElement('p');
  p.textContent = 'This is a paragraph.';
  const textNode = document.createTextNode('And this is some text.');

  // Append the elements and text nodes to the fragment
  fragment.appendChild(h1);
  fragment.appendChild(p);
  fragment.appendChild(textNode);

  // Append the fragment to the document
  document.getElementById('my-div').appendChild(fragment);

</script>

```



4. element.appendChild(element): Appends an element to the end of the contents of another element 
```
<!-- HTML document -->
<div id="my-div">
  <p>This is a paragraph.</p>
</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Create a new element
  const h1 = document.createElement('h1');
  h1.textContent = 'Hello, World!';

  // Append the element to the end of the div
  div.append(h1);
</script>

// Result 
<div id="my-div">
  <p>This is a paragraph.</p>
  <h1>Hello, World!</h1>
</div>


```
6. element.prepend(node1): Prepends an element to the beginning of the contents of another element 
```
<!-- HTML document -->
<div id="my-div">
  <p>This is a paragraph.</p>
</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Create a new element
  const h1 = document.createElement('h1');
  h1.textContent = 'Hello, World!';

  // Prepend the element to the beginning of the div
  div.prepend(h1);
</script>

//  Result 
<div id="my-div">
  <h1>Hello, World!</h1>
  <p>This is a paragraph.</p>
</div>

```
7. element.remove(): Removes the element from the DOM

```
<!-- HTML document -->
<div id="my-div">
  <p>This is a paragraph.</p>
  <button id="remove-button">Remove</button>
</div>

<script>
  // Retrieve the button element
  const button = document.getElementById('remove-button');

  // Add an event listener to the button
  button.addEventListener('click', () => {
    // Retrieve the element to be removed
    const p = document.querySelector('p');

    // Remove the element
    p.remove();
  });
</script>


```


### Size and Scrolling 

1. window.getComputedStyle(element): a function of the window object in JavaScript that is used to get the computed values of an element's style properties. It takes an element and an optional pseudo-element as arguments, and returns a CSSStyleDeclaration object that contains the computed values of the element's style properties.

```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
  }
</style>
<div id="my-div">This is a div</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Get the computed style of the element
  const style = window.getComputedStyle(div);

  // Output the values of the style properties
  console.log(style.backgroundColor); // Output: "rgb(255, 0, 0)"
  console.log(style.width); // Output: "200px"
  console.log(style.height); // Output: "100px"
</script>


```

2. element.clientHeight: used to get the height of an element, including its padding but not its margins, borders, or scrollbars. It is a read-only property and is measured in pixels.
```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
    padding: 20px;
  }
</style>
<div id="my-div">This is a div</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Get the client height of the element
  const height = div.clientHeight;

  // Output the client height
  console.log(height); // Output: 140 (200px height + 20px padding on top + 20px padding on bottom)
</script>

```
3. element.offsetHeight:  used to get the height of an element, including its padding, borders, and scrollbars, but not its margins. It is a read-only property and is measured in pixels.

```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 2px solid black;
  }
</style>
<div id="my-div">This is a div</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Get the offset height of the element
  const height = div.offsetHeight;

  // Output the offset height
  console.log(height); // Output: 144 (100px height + 20px padding on top + 20px padding on bottom + 2px border on top + 2px border on bottom)
</script>

```
4. element.scrollHeight: used to get the total height of an element's content, including its padding, but not its margins, borders, or scrollbars. It is a read-only property and is measured in pixels.

```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
    padding: 20px;
    overflow: scroll;
  }
</style>
<div id="my-div">
  <p>This is a paragraph.</p>
  <p>This is another paragraph.</p>
</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Get the scroll height of the element
  const height = div.scrollHeight;

  // Output the scroll height
  console.log(height); // Output: 128 (20px padding on top + 20px padding on bottom + 48px height of first paragraph + 48px height of second paragraph)
</script>

```
In this example, the div element is retrieved from the document using document.getElementById(), and the scrollHeight property is used to get the total height of the element's content. The scrollHeight includes the element's top and bottom padding of 20px and the combined height of the two p elements, which is 48px each, for a total of 96px. The output is the value 128, which represents the total height of the element's content.

The element.scrollHeight property is useful for getting the total height of an element's content when the element has scrollbars, or for determining if an element's content overflows its boundaries. It can be used in combination with other size properties, such as element.clientHeight, element.offsetHeight, and element.scrollTop, to manipulate the scroll position of an element.

5. element.offsetTop: used to get the distance of the element from the top of the offset parent element. The offset parent is the nearest ancestor element that has a position other than static. The offsetTop property is a read-only property and is measured in pixels.

```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
    position: relative;
    top: 50px;
  }
</style>
<div id="my-parent">
  <div id="my-div">This is a div</div>
</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Get the offset top of the element
  const top = div.offsetTop;

  // Output the offset top
  console.log(top); // Output: 50 (distance from top of parent element)
</script>



```
6. element.scrollIntoView(): used to scroll the element into view within its nearest scrollable ancestor. It takes an optional argument that specifies how the element should be aligned within the viewport.

```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
  }
  #my-parent {
    overflow: scroll;
    height: 200px;
  }
</style>
<div id="my-parent">
  <div id="my-div">This is a div</div>
</div>

<script>
  // Retrieve the element
  const div = document.getElementById('my-div');

  // Scroll the element into view
  div.scrollIntoView();
</script>


```
7. element.scrollTo(): used to scroll the document to a specified position. It takes two arguments: the x-coordinate and the y-coordinate of the position to scroll to. The coordinates are measured in pixels and are relative to the top-left corner of the document.


```
<!-- HTML document -->
<style>
  #my-div {
    background-color: red;
    width: 200px;
    height: 100px;
  }
</style>
<div id="my-div">This is a div</div>

<script>
  // Scroll the document to the top-left corner
  window.scrollTo(0, 0);

  // Scroll the document to the position of the div element
  const div = document.getElementById('my-div');
  window.scrollTo(div.offsetLeft, div.offsetTop);
</script>


```




