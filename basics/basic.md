# JavaScript Basics

## JavaScript 
  The primary programming language of the web, primarily used for adding functionality
  to websites. JavaScript is a general purpose multi-paradigm programming language with
  dynamic typing.

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" class="mIbssb657Yg6sEDYNXbC" rel="noreferrer">Learn more: <span class="Link Link--fe GgbfIB2K5OJlLnFrm_xf">https://developer.mozilla.org/en-US/docs/Web/JavaScript</span></a>

## Paradigm 
  <p>
    A style of programming. Oftentimes languages are built with a specific
    paradigm in mind, but JavaScript is known as a <b>multi-paradigm</b>
    language, because it allows for programming in a variety of paradigms.
    Some of the major paradigms of JavaScript include:
  </p>
  <ul>
    <li>
      <b>Event-driven</b>: Functions can be made to respond to events, such as when a
      user clicks on an element or scrolls down the page.
    </li>
    <li>
      <b>Functional</b>: Functions can be written as "pure functions", meaning
      functions that always have the same output for a given set of arguments
      and never produce side effects. Additionally, JavaScript supports
      <b>first-class functions</b> and <b>higher-order functions</b>. This
      means that functions can be treated as normal values, passed as arguments
      to other functions and returned from functions.
    </li>
    <li>
      <b>Object-oriented</b>: Objects can be created as custom data stores and
      they can be made to inherit from each other.
    </li>
    <li>
      <b>Imperative</b>: Programs can be written by explicitly describing the
      control flow, such as with loops and conditionals.
    </li>
    <li>
      <b>Declarative</b>: Programs can be written by describing the desired output
      with implicit control flow. Oftentimes this is associated with functional programming
      (e.g. using the forEach function to loop over an array instead of a for loop).
    </li>
  </ul>

## Primitive 
<p>
  The most basic data types of a language. In JavaScript, there
  are 7 primitive types:
</p>

<ul>
  <li>
    <b>Number</b>: Numeric values, including integers and decimal values.
  </li>
  <li>
    <b>BigInt</b>: Integers too large to store in a number.
  </li>
  <li>
    <b>Boolean</b>: A binary value of <span>true</span> or <span>false</span>.
  </li>
  <li>
    <b>String</b>: A sequence of characters.
  </li>
  <li>
    <b>Symbol</b>: A dynamically generated unique value.
  </li>
  <li>
    <b>Null</b>: A nonexistent value.
  </li>
  <li>
    <b>Undefined</b>: A value that has not been set.
  </li>
</ul>

<p>
  JavaScript has a <span>typeof</span> operator that
  can get the type of a value as a lowercase string.
  However, do be aware that this function does have some
  special casing. For example, <span>typeof function</span>
  will return "function" even though functions are
  just objects.
</p>

<a href="https://developer.mozilla.org/en-US/docs/Glossary/Primitive" target="_blank" class="mIbssb657Yg6sEDYNXbC" rel="noreferrer">Learn more: <span class="Link Link--fe GgbfIB2K5OJlLnFrm_xf">https://developer.mozilla.org/en-US/docs/Glossary/Primitive</span></a> 