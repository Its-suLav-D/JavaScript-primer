# Variables and Scoping 



## Let 

<p>
  A keyword for declaring a <b>block-scoped</b> variable that cannot be
  accessed before initialization.
</p>

## Var 
<p>
  A keyword for declaring a <b>function-scoped</b> variable that is automatically
  initialized to <span>undefined</span> when it is <b>hoisted</b>.
</p>

> https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var

## Const 
<p>
  A keyword for declaring a constant value. Constants have the same behavior
  as variables declared with <span>let</span>, except they cannot be reassigned.
</p>

> https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Const 

## Block Scope

<p>
  The behavior of a variable that is only accessible inside of the block it was defined. Most of the
  time, the block will simply be the nearest pair of curly braces to the declaration.
</p>

## Function Scope 
<p>
  The behavior of a variable that is accessible anywhere inside of the function it was defined.
</p>

## Hoisting 
  <p>
    The process by which the JavaScript engine moves variable declarations to
    the top of their scope, allocating memory for them before reaching the line
    of code where they are declared. For variables declared with
    <span>var</span>, they are initialized to <span>undefined</span> until
    reaching the line of code that initializes the variable. For variables
    declared with <span>let</span> or <span>const</span>, the variable is not
    initialized and thus cannot be accessed before the line of code that
    initializes it. For example:
  </p>

```
console.log(testVar) // Undefined
console.log(testLet) // reference error 

var testVar = 10;
let testLet = 10; 

console.log(testVar) // 10 
console.log(testlet) // 10 

```