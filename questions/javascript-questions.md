# JS Questions and Answers:

* Explain event delegation
  > DOM event delegation is a mechanism of responding to ui-events via a single common parent rather than each child, through the magic of event "bubbling" (aka event propagation).
  
* Explain how `this` works in JavaScript
  >  If a function is called on an object, such as in obj.myMethod() or the equivalent obj[myMethod](), then "this" is set to the object (obj in the example). In most other cases, "this" is set to the global object (calling inside eval() or with the new keyword are special cases).
  
* Explain how prototypal inheritance works
  > Every object in Javascript has its prototype. So, the core idea of Prototypal Inheritance is that an object can point to another object's prototype and inherit all its properties. The main purpose is to allow multiple instances of an object to share common properties, hence, the Singleton Pattern.
  
* What do you think of AMD vs CommonJS?
  > AMD is more suited for the browser, because it supports asynchronous loading of module dependencies, and CommonJS Modules are generally used server-side. However, you can use either module spec in either environment - for example, RequireJS offers directions for running in Node.js and browserify is a CommonJS Module implementation that can run in the browser.
  
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  > Because the word `function` makes parser treat it like function declaration, so it gets stored in memory.
  
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
  > **Feature detection** is just a way of determining if a feature exists in certain browsers (`if(window.XMLHttpRequest){
    var ajax = new XMLHttpRequest();}`).
    
  > **UA String** or User Agent String is a string text of data that each browsers send and can be access via navigator.userAgent. These “string text of data” contains information of the browser environment you are targeting (tip: Modernizr).  
  
* Explain Ajax in as much detail as possible.
  > **A**synchronous **J**avascript **A**nd **X**ML (which interestingly enough tends to use JSON more these days), is a system in which Javascript uses a browser object to communicate with a remote server. AJAX typically involves sending HTTP requests from client to server and processing the server's response, without reloading the entire page. (Asynchronously). Javascript generally does the submission and receives the data response from the server (traditionally XML, often other less verbose formats like JSON)
  
* What are the advantages and disadvantages of using Ajax?
  > **Pros:** The use of Ajax can reduce connections to the server, since scripts and style sheets only have to be requested once(small requests). 
  
  > **Cons:** Pages dynamically created using successive Ajax requests do not automatically register themselves with the browser's history engine; Ajax-powered interfaces may dramatically increase the number of user-generated requests to web servers and their back-ends (databases, or other)
  
* Explain how JSONP works (and how it's not really Ajax).
  > The key difference between a JSON response and a JSONP response is the callback function. A regular AJAX endpoint would simply respond with a string of JSON, a JSONP response, on the other hand, is actually an executable script that calls a designated JSONP callback function, passing a JSON string as a parameter. Can't make POST requests and insecure.
  
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
    > I used **EJS** and **pug** in node js projects.
    
* Explain "hoisting".
  > Because variable declarations (and declarations in general) are processed before any code is executed, declaring a variable anywhere in the code is equivalent to declaring it at the top. This also means that a variable can appear to be used before it's declared. This behavior is called "hoisting".
  
* Describe event bubbling.
  > It's when an event is bubbled into container elements, in the higher level of a DOM tree. With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.
  
* What's the difference between an "attribute" and a "property"?
  > **Attribute:** specified in HTML, always in the form of string. **Property:** specified in DOM object, can have any type of JavaScript

* Why is extending built-in JavaScript objects not a good idea?
  > Because, modified native objects can interfere with someone else's code and cause unpredictible bugs. If you need custom behaviour, it is far better to define your own class (perhaps a subclass) instead of changing a native one.
  
* Difference between document load event and document DOMContentLoaded event?
  > The **DOMContentLoaded** event is fired when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. A very different event **load** should be used only to detect a fully-loaded page. It is an incredibly popular mistake to use load where DOMContentLoaded would be much more appropriate, so be cautious.
  
* What is the difference between `==` and `===`?
  > **`==`** compares values with type coersion, **`===`** compares values **AND** types without coersion. 

* Explain the same-origin policy with regards to JavaScript.
  > Only scripts that are served from the same domain can access each others objects and properties without restriction (you can't execute js file hosted on a different domain). 
  
  > There are two ways to "bypass" SOP, one is JSONP, the other is through CORS(Cross Origin Resource Sharing). CORS needs cooperation from server setting. You have to set Access-Control-Origin-Allow: yourdomain.com to domains which you want it to be allowed in header in order to access resource via normal AJAX call.

* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
  > `const duplicate = (arr) => arr.concat(arr)`
  
* Why is it called a Ternary operator, what does the word "Ternary" indicate?
  > A Ternary operator is an operator that takes three arguments (that's why **ternary**). It's called so because the conditional operator has 3 arguments: condition, false-returned value and true-returned value.
  
* What is `"use strict";`? what are the advantages and disadvantages to using it?
  > * Advantages
  
      Cannot assign a value to an undefined global variable
      
      Fire TypeError for not-allowed assignments
      
      `this` in a normal function refers to undefined, instead of global
      
      > In short, it secures JavaScript.
      
   > * Disadvantage
  
      When using global strict mode and concatenating the script with other scripts not using strict mode, the other scripts can be broken.   
        
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
  > LOL
  
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
  > Collisions between various scripts on the same page.
  
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
  > **load** event tells browser to do something only after everthing including frames, images, asynchronous JavaScripts are fully loaded.
  
  > If you want event function to execute before fully loaded frames, images, async scripts, use **domcontentloaded** instead.
  
* Explain what a single page app is and how to make one SEO-friendly.
  > **SPA** is a web application or web site that fits on a single web page with the goal of providing a more fluid user experience similar to a desktop application. In a SPA, HTML, JavaScript, and CSS — are retrieved with a single page load, or the appropriate resources are dynamically loaded and added to the page as necessary, usually in response to user actions.
  
* What is the extent of your experience with Promises and/or their polyfills?
  > Heavily usage of promises with plain shifting towards async/await.
  
* What are the pros and cons of using Promises instead of callbacks?
  > **Pros:** no callback hell, more readable code; **Cons:** have to use polyfills for IE.
  
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
  > **Pros:** Syntactic sugar, readable code, and use of good patterns; **Cons:** debugging and compilation issues
  
* What tools and techniques do you use debugging JavaScript code?
  > Chrome Dev Tools, linting (prevent bugs mainly).
  
* What language constructions do you use for iterating over object properties and array items?
  > `for..of`, `.forEach()`, `for...in` (objects).
  
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
  
  > **Mutable** objects are those whose state is allowed to change over time. An **immutable** value is the exact opposite — after it has been created, it can never change. Strings and Numbers are inherently immutable in javascript, opposite to Array and Object. Tip: `immutable.js`.
  
* Explain the difference between synchronous and asynchronous functions.
  > **Synchronous:** Step wise execution. Next line executed after first. **Asynchronous:** Execution moves to next step before first is finished
  
* What is event loop?
  * What is the difference between call stack and task queue?
    > Event loop is a queue of callback functions. When a asynchronous function executes, it is pushed into task queue and JavaScript will only start processing task queue after codes after async function are executed.
    
    > The difference between call stack and task queue is that task queue is a place where JavaScrip schedules async function while call stack is a place for JavaScript to trace what the current function is.
    
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
  >  First one is declaration defined at parse time while the other is expression defined at run time.
  
* What are the differences between variables created using `let`, `var` or `const`?
  > **var** is scoped to the nearest function block and **let** is scoped to the nearest enclosing block, which can be smaller than a function block (e.g. `for` loops). Also, variables declared with **let** are not accessible before they are declared in their enclosing block, also **let** cannot be redeclared within the same scope. **const** behaves like **let**, besides it cannot be reassigned
  
* What are the differences between ES6 class and ES5 function constructors?
  > The syntax basically. Still the prototype inheritance.
  
* Can you offer a use case for the new arrow `=>` function syntax? How does this new syntax differ from other functions?
  > In the anonymous functions without usage of `this` keyword (e.g. callbacks). For explicit return.
  
* What advantage is there for using the arrow syntax for a method in a constructor?
  > Don't have to .bind(this).
  
* What is the definition of a higher-order function?
  > Function that returns a function, or accepts as an argument.
  
* Can you give an example for destructuring an object or an array?
  > `const {user, password, email} = this.props;`
  
* ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
  > `const userName = this.props.name; const text = 'User ${userName} is online!'`;
  
* Can you give an example of a curry function and why this syntax offers an advantage?
  > `function add (a) { return function (b) { return a + b; } }; add(2)(3)`. Increases functionality.
  
* What are the benefits of using `spread syntax` and how is it different from `rest syntax`?
  > **Spread operator** allows an iterable such as an array expression or string to be expanded in places where zero or more arguments or elements are expected. `var arr1 = [0, 1, 2];var arr2 = [3, 4, 5];arr1 = [...arr2, ...arr1]; // arr1 is now [3, 4, 5, 0, 1, 2]`
  
  > **Rest** syntax looks exactly like spread syntax, but is used for destructuring arrays and objects. In a way, rest syntax is the opposite of spread syntax: spread 'expands' an array into its elements, while rest collects multiple elements and 'condenses' them into a single element. `function fun1(...theArgs) {console.log(theArgs.length);} fun1(5, 6, 7); // 3`
  
  > Spread is on the right side of the expression, rest - on the left. 
  
* How can you share code between files?
  > Create global scope variables, use commonJS or modules.
  
* Why you might want to create static class members?
  > No idea what class members are
