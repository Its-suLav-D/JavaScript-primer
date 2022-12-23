# Equality and Type 


## Loose Equality 
<p>
  The most basic equality operator in JavaScript using <span>==</span>. Loose
  equality compares values regardless of types following these steps:
</p>

<ol>
  <li>
    If both values are either <span>null</span> or <span>undefined</span>, return true.
  </li>
  <li>
    Convert all <span>booleans</span> to <span>numbers</span>. <span>True</span>
    converts to <span>1</span> and <span>false</span> converts to 0.
  </li>
  <li>
    If comparing a <span>number</span> to a <span>string</span>, convert the
    <span>string</span> to a <span>number</span>.
  </li>
  <li>
    If comparing an <span>object</span> to a <span>string</span>, convert the
    <span>object</span> using its <span>toString()</span> or <span>valueOf()</span> methods.
  </li>
  <li>
    If the types are the same, follow the same rules as <b>strict equality</b>.
  </li>
</ol>

<p>
  In general, <b>strict equality</b> should be preferred due to it being easier
  to predict. However, <b>loose equality</b> can be useful for checking against
  <span>null</span> and <span>undefined</span> at once with <span>value == null</span>.
</p>
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality" target="_blank" >Learn more: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality</a>

## Strict Equality 
<p>
  A JavaScript equality operator using <span>===</span>. Strict equality compares
  both values and types following these steps:
</p>

<ol>
  <li>If either value is <span>NaN</span>, return false.</li>
  <li>If the values have different types, return false.</li>
  <li>If both values are <span>null</span> or both values are <span>undefined</span>, return true.</li>
  <li>If both values are <span>objects</span>, return true if they are the same object. False otherwise.</li>
  <li>If both values are of the same primitive type, return true if the values are the same. False otherwise.</li>
</ol>
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality" target="_blank">Learn more: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality</a> 