# JS in Depth

## Table of Contents

1. Table of Contents
2. Homework Details
3. Core JavaScript Questions
4. ES6 Questions
5. Node.js Questions
6. React.js Questions
7. Internet/Network questions

## Homework Details

This homework is designed to prepare you for questions you may face during an interview. It should take you no more than 3 hours. It's akin to an open book quiz since you can use the internet to look things up. But first, try going through and seeing how many questions you can answer without using google/stackoverflow/anyOtherInternetSource! And then go back and look up the answers to the ones that stumped you.

## Core JavaScript Questions

1. What is the difference between `undefined` and `not defined` in JavaScript?

answer:`undefined` is the output caused by calling a variable that is declared but not defined.`not defined` is the output caused by calling a variable that is neither declared or defined.

2. What is "Hoisting" in JavaScript?

answer: variables are moved to the top of the scope in which they are declared in order to be accessible by all scope attributes   

3. What would be the output of the following code?
```javascript
    var y = 1;
      if (function f(){}) {
        y += typeof f;
      }
     console.log(y);
```
answer: y is declared and defined as 1 and f(){} is declared but not defined so the output would be `1undefined`

4. What is a "private method"?

answer: a method that is not accessible globally.

5. What is the drawback of creating true private methods in JavaScript?

answer: the method takes up a lot of memory because each time an instance of the method is called it is rewritten for the new instance

6. What is a “closure” in JavaScript? Provide an example.

answer: a closure is function within a parent function that has access to global, parent, and personal variables.
  ```javascript
    let globalVar = 1;
    parent = () => {
      inner = 2 * globalVar;
      child = () => {
        innerInner = 3 * inner;
        console.log(innerInner);
      };
    };
    //output 6
```
7. Write a mul function which will produce the following outputs when invoked.
```javascript
console.log(mul(2)(3)(4)); // output : 24
console.log(mul(4)(3)(4)); // output : 48
```
answer:
```javascript
  function mul (a) {
  return function (b) {
    return function (c) {
      return a * b * c;
    };
  };
}
```
8. How would you empty an array in JavaScript? Provide at least 2 methods of doing so.

answer: array = []; & array = null;

9. What will be the output of the following code?
```javascript
var output = (function(x){
    delete x;
    return x;
  })(0);

  console.log(output);
```
answer: `0`

What about this code?
```javascript
var x = 1;
var output = (function(){
    delete x;
    return x;
  })();

  console.log(output);
```
answer: `1`

And what about this one?
```javascript
var x = { foo : 1};
var output = (function(){
    delete x.foo;
    return x.foo;
  })();

  console.log(output);
```
answer: `undefined`

And finally, what about this one?
```javascript
var Employee = {
  company: 'xyz'
}
var emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company);
```
answer: `xyz`

10. What would this code return?
```javascript
var trees = ["xyz","xxxx","test","ryan","apple"];
delete trees[3];

  console.log(trees.length);
```
answer:`5`

11. What will be the output of the code below?
```javascript
var bar = true;
console.log(bar + 0);   
console.log(bar + "xyz");  
console.log(bar + true);  
console.log(bar + false);   
```
answer: `1, truexyz, 2, 1`

12. What will be the output of the code below?
```javascript
var z = 1, y = z = typeof y;
console.log(y);  
```
12. `undefined`

13. What would be the output of the code below?
```javascript
 var salary = "1000$";

 (function () {
     console.log("Original salary was " + salary);

     var salary = "5000$";

     console.log("My New Salary " + salary);
 })();

```
answer: `Original salary was undefined, My New Salary 5000$`

14. What is the instanceof operator in JavaScript? What would be the output of the code below?
```javascript
function foo(){
  return foo;
}
new foo() instanceof foo;
```
answer: an instance operator checks if an object has inheritance from the stated prototype, `false`.

15. What constitutes a "Primitive" value in Javascript?

answer: the value is immutable, cannot be changed.

16. What is the difference between a reference type variable and a value type variable?

answer: reference type variable (pointer) looks to other variables to establish value. A value type variable (holder) holds an established value.

17. How would you describe the difference between class-based inheritance and prototypical inheritance?  

## ES6 Questions

1. What is the difference between JavaScript and ECMAScript?
2. What do `const` and `let` do? And when would we use them?

answer: `const` defines a variable that will stay constant and cannot be reassigned an new value. `let` defines a variable.

3. How would you describe the difference between `function` and `function*`?

answer: `function*` declares a generator function which is a pausable function

4. When would you NOT use an arrow function in the place of a regular function expression?
5. Refactor the following code to use an ES6 Template Literal.
```javascript
var name = 'Tiger';
var age = 13;

console.log('My cat is named ' + name + ' and is ' + age + ' years old.');
```
answer:
```javascript
let name = 'Tiger';
let age = 13;

console.log(`My cat is named ${name} and is ${age} years old.`)
```
6. How would you refactor the following code to use ES6 default parameters?
```javascript
function addTwoNumbers(x, y) {
    x = x || 0;
    y = y || 0;
    return x + y;
}
```
answer:
```javascript
(x,y) => {
  x = x || 0;
  y = y || 0;
  return x + y;
}
```
7. What is a "Promise" in ES6? And how many different states do they have?

answer: A promise (callback) initiates an action once a value is realized. The states are Rending, Fulfilled, and Rejected.

8. What is a practical use case for Promises?

answer: querying information and once that information is received acting on that value (().then).

9. What is wrong with the following code? And how could it be better?
```javascript
new Promise((resolve, reject) => {  
  throw new Error('error')
}).then(console.log)
```
10. Describe the .fetch() method. What is one disadvantage to using the .fetch() method over existing methods?

answer: Fetch allows access to the the request and responses pipeline of the HTTP protocol.  The .fetch() method will not reject on HTTP error status, it will only reject if the request was not completed.  fetch() doesn't maintain user sessions causing possible issues with authentication.

## Node.js Questions

1. What is Node.js?

answer: Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine.

2. What is an "Error-First" Callback?

answer: If there is an error throw and error otherwise return the successful information query.

3. What is the Node.js Event Loop?
4. Why might someone choose to use the Node.js Async single-threaded model over a more traditional multi-threaded model?
5. What is meant by the term "non-blocking I/O"?
6. What is the "memory stack"? And what happens when you exceed it?

## React.js Questions

1. What makes React.js more efficient at updating the DOM?
2. What is the difference between a Logical component and a Pure component?
3. What happens when you call "setState" in React?
4. What is the React method to create a component? Alternatively, how would you accomplish the same thing using ES6 classes?
5. In which React lifecycle event would you make AJAX requests? And why?
6. Why would you use `React.Children.map(props.children, () => )` instead of `props.children.map(() => )`?
7. What is JSX?

answer: a preprocessor step that adds XML syntax to JavaScript.

## Internet/Network Questions

1. What does TCP/IP stand for?

answer: Transmission Control Protocol/Internet Protocol

2. Behind the scenes, how does HTTPS differ from HTTP?

answer: All communications between the users browser and the website are encrypted.

3. Define the general response status code categories.

answer: 200 -> ok, 201 -> created, 204 -> no content, 304 -> not modified, 400 -> bad request, 401 -> not authorized, 403 -> forbidden, 404 -> not found, 409 -> conflict, 500 -> internal server error

4. What does DDOS stand for?

answer: distributed denial-of-service

5. What is CORS? How does it work?

answer: Cross-Origin Resource Sharing allows data to be transferred securely across different domains.  HTTP headers communicate what actions is to executed on what data.  

6. What does REST stand for when we refer it in the context of a "RESTful API"?

answer: REpresentational State Transfer
