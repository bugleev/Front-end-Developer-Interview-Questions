# JS Questions and Answers:

* Explain event delegation
  > DOM event delegation is a mechanism of responding to ui-events via a single common parent rather than each child, through the magic of event "bubbling" (aka event propagation).
  
* Explain how `this` works in JavaScript
  >  If a function is called on an object, such as in obj.myMethod() or the equivalent obj["myMethod"](), then "this" is set to the object (obj in the example). In most other cases, "this" is set to the global object (calling inside eval() or with the new keyword are special cases).
  
* Explain how prototypal inheritance works
  > Every object in Javascript has its prototype. So, the core idea of Prototypal Inheritance is that an object can point to another object's prototype and inherit all its properties. The main purpose is to allow multiple instances of an object to share common properties, hence, the Singleton Pattern.
  
* What do you think of AMD vs CommonJS?
  > AMD is more suited for the browser, because it supports asynchronous loading of module dependencies, and CommonJS Modules are generally used server-side. However, you can use either module spec in either environment - for example, RequireJS offers directions for running in Node.js and browserify is a CommonJS Module implementation that can run in the browser.
  
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
    > `(function foo(){ }());`
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  > **undefined** is a variable that has been declared but no value exists and is a type of itself ‘undefined’. **null** is a value of a variable and is a type of object. **undeclared** variable is a variable that has been declared without ‘var’ keyword
  * How would you go about checking for any of these states?
    > `typeof(variable) !== "undefined"` or `variable === null`
    
* What is a closure, and how/why would you use one?
  > Closure is when a function can remember and access its lexical scope even when it's invoked outside its lexical scope (e.g. store references to the outer function’s variable). Usage: timers, event handlers, Ajax requests, cross-window messaging, web workers, or any of the other asynchronous (or synchronous!) tasks, when you pass in a callback function.
  
* Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
  > Array.forEach executes a provided function once per array element. Array.map creates a new array with the results of calling a provided function on every element in this array.
  
* What's a typical use case for anonymous functions?
  > As a callback function or an argument for another function.
  
* How do you organize your code? (module pattern, classical inheritance?)
  > * Use an anonymous closure(IIFE that lets us hide variables from the parent (global) namespace).
  > * Another popular approach used by libraries like jQuery is global import. It’s similar to the anonymous closure, except now we pass in globals as parameters.
  > * Self-contained object interfaces, this approach lets us decide what variables/methods we want to keep private and what variables/methods we want to expose by putting them in the return statement.
  
  > The approaches above all have one thing in common: the use of a single global variable to wrap its code in a function, thereby creating a private namespace for itself using a closure scope.  
  
  
* What's the difference between host objects and native objects?
  > Host Objects are objects supplied by a certain environment. Example, browser environment supplies objects such as window. While a node.js/server environment supplies objects such as NodeList. Native Objects or Built-in Objects are standard built-in objects provided by Javascript, sometimes referred to as ‘Global Objects’.
  
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  > Function Declaration, Function Expression, Function Constructor
  
* What's the difference between `.call` and `.apply`?
  > .apply and .call are methods we use to assign the ‘this’ keyword from the invoked function to reference to an object for the duration of the method invocation. .apply lets you invoke the function with arguments as an array, .call requires the parameters be listed explicitly
  
* Explain `Function.prototype.bind`.
  > .bind returns a function which will act like the original function but with 'this' predefined. 
  
  > If you've used bind to get back a function with a bound this value, you just call the function: `getx();`
  
  > If you don't have a bound function, and you want to set this, you do so with call or apply:`someFunction.call(objectToUseAsThis, arg1, arg2);`
  
* What's the difference between feature detection, feature inference, and using the UA string?
  > **Feature detection** is just a way of determining if a feature exists in certain browsers.**UA String** or User Agent String is a string text of data that each browsers send and can be access via navigator.userAgent. These “string text of data” contains information of the browser environment you are targeting (tip: Modernizr).  
  
* Explain Ajax in as much detail as possible.
  > **A**synchronous **J**avascript **A**nd **X**ML (which interestingly enough tends to use JSON more these days), is a system in which Javascript uses a browser object to communicate with a remote server. AJAX typically involves sending HTTP requests from client to server and processing the server's response, without reloading the entire page. (Asynchronously). Javascript generally does the submission and receives the data response from the server (traditionally XML, often other less verbose formats like JSON)
  
* What are the advantages and disadvantages of using Ajax?
  > **Pros:** The use of Ajax can reduce connections to the server, since scripts and style sheets only have to be requested once(small requests). 
  
  > **Cons:** Pages dynamically created using successive Ajax requests do not automatically register themselves with the browser's history engine; Ajax-powered interfaces may dramatically increase the number of user-generated requests to web servers and their back-ends (databases, or other)
  
* Explain how JSONP works (and how it's not really Ajax).
  > 
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document DOMContentLoaded event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary operator, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
* What are the differences between variables created using `let`, `var` or `const`?
* What are the differences between ES6 class and ES5 function constructors?
* Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?
* What advantage is there for using the arrow syntax for a method in a constructor?
* What is the definition of a higher-order function?
* Can you give an example for destructuring an object or an array?
* ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
* Can you give an example of a curry function and why this syntax offers an advantage?
* What are the benefits of using `spread syntax` and how is it different from `rest syntax`?
* How can you share code between files?
* Why you might want to create static class members?
