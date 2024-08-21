check below links

pending : jwt vs refresh token

===========


how js works - callstack, eventloop
Impppppppppppppppppppppp

https://www.youtube.com/watch?v=8aGhZQkoFbQ
https://felixgerschau.com/javascript-event-loop-call-stack/
https://www.freecodecamp.org/news/a-guide-to-the-node-js-event-loop/

https://medium.com/@gautambhargav644/javascripts-call-stack-and-event-loop-making-sense-of-the-madness-1f7cddbf6712

https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/


execution example
https://javascriptcentric.medium.com/javascript-interview-preparation-priority-of-callback-promise-settimeout-and-process-nexttick-93be400470a8

====================

very imp

https://medium.com/@Rahulx1/understanding-event-loop-call-stack-event-job-queue-in-javascript-63dcd2c71ecd

=================

https://medium.com/sessionstack-blog/how-javascript-works-dockerizing-a-node-js-application-228154e9d91a

docker steps for nodejs

===========

https://medium.com/@olumideadewusis/implementing-rate-limiting-in-node-js-apis-94f18cd74695

app configuration in node

-------


https://medium.com/@Adekola_Olawale/the-event-loop-demystified-171eebf8c0d9
https://www.freecodecamp.org/news/nodejs-eventloop-tutorial/

https://medium.com/sessionstack-blog/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5

https://medium.com/sessionstack-blog/how-javascript-works/home

---

memory leak isssue
https://medium.com/sessionstack-blog/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec


---

https://javascriptcentric.medium.com/top-50-nodejs-interview-questions-and-answers-for-2024-5e460dac7852

https://freedium.cfd/https://javascriptcentric.medium.com/top-30-javascript-interview-questions-and-answers-for-2024-7f1e2d1d0638

---
### What is the Factory function and generator function?
A factory function in JavaScript is a function that returns an object. It is a pattern used to create objects in a straightforward and organized manner. Instead of using constructor functions and the new keyword to create new objects, a factory function encapsulates the object creation process and returns a new object.

```
function createPerson(name, age) {
  return {
    name: name,
    age: age,
    greet: function() {
      return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
  };
}

const person1 = createPerson('Alice', 25);
const person2 = createPerson('Bob', 30);

console.log(person1.greet()); // Output: Hello, my name is Alice and I am 25 years old.
console.log(person2.greet()); // Output: Hello, my name is Bob and I am 30 years old.
```

### Generator function

A Generator function in JavaScript is a special type of function that can be paused and resumed during its execution.

A generator function produces a sequence of results instead of a single value.

When a generator function called it returns a generator object that can be used to control the execution of the function by calling the next() method.

The function's code can be paused within the body using the yield keyword, and it can later be resumed from the exact point where it was paused.

```
function* numberGenerator() {
  let i = 0;
  while (true) {
    yield i++;
  }
}

const gen = numberGenerator();
console.log(gen.next().value); // Output: 0
console.log(gen.next().value); // Output: 1
console.log(gen.next().value); // Output: 2
```
This provides a powerful mechanism for creating iterators and handling asynchronous code.

---

### How to make an object immutable? (seal and freeze methods)?
In JavaScript, you can make an object immutable using the Object.seal() and Object.freeze() methods.

Object.freeze(): (Completely Immutable) this method freezes an object, making it both sealed and marking all its properties as read-only. After freezing an object, its properties cannot be modified, added, or removed.

```
     const obj = { name: 'Alice', age: 25 };
     Object.freeze(obj);
     obj.name = 'Bob'; // Not allowed
     obj.address = '123 Street'; // Not allowed
     delete obj.age; // Not allowed
```
     
Object.seal(): (Partialy Immutable) this method seals an object, preventing new properties from being added and marking all existing properties as non-configurable. However, you can still modify the values of existing properties that are writable.

```
     const obj = { name: 'Alice', age: 25 };
     Object.seal(obj);
     obj.name = 'Bob'; // Allowed
     obj.address = '123 Street'; // Not allowed (no new properties can be added)
     delete obj.age; // Not allowed (existing properties cannot be deleted)
```

---

### Find vs Filter

const x = [1, 2, 3, 4, 5];

const y = x.find(el => el*2 === 2);
const z = x.filter(el => el*2 === 2);

console.log("y is: ", y); // y is: 1        //element itselt
console.log("z is: ", z); // z is: [1]      // array of elements that satisfy the condition

filter() returns an array containing the element that satisfies the condition, but find() returns the element itself that satisfies the condition.


In filter(), whole array is iterated despite the fact that the element being searched for is present at the beginning.
But in find(), as soon as the element that satisfies the condition is found, it gets returned.

---

### import vs require

var myVac = import("module-name");
var myVar = require('http'); 

import is asynchronous and require is synchronous
require() can be called from anywhere inside the program whereas import() cannot be called conditionally, it always runs at the beginning of the file.

import express from "express";

You can't selectively load only the pieces you need with require but with import, you can selectively load only the pieces you need, which can save memory.

Loading is synchronous(step by step) for require on the other hand import can be asynchronous(without waiting for previous import) so it can perform a little better than require.

---

## Concurrency & the Event Loop or why asynchronous callbacks.

What happens when you have function calls in the Call Stack that take a huge amount of time in order to be processed? For example, imagine that you want to do some complex image transformation with JavaScript in the browser.

You may ask — why is this even a problem? The problem is that while the Call Stack has functions to execute, the browser can’t actually do anything else — it’s getting blocked. This means that the browser can’t render, it can’t run any other code, it’s just stuck. And this creates problems if you want nice fluid UIs in your app.

And that’s not the only problem. Once your browser starts processing so many tasks in the Call Stack, it may stop being responsive for quite a long time. And most browsers take action by raising an error, asking you whether you want to terminate the web page.

So, how can we execute heavy code without blocking the UI and making the browser unresponsive? Well, the solution is asynchronous callbacks.

---

## maximum call stack size exceeded

https://medium.com/sessionstack-blog/how-does-javascript-actually-work-part-1-b0bacc073cf


function foo() {
    foo();
}
foo();

When the engine starts executing this code, it starts with calling the function “foo”. This function, however, is recursive and starts calling itself without any termination conditions. So at every step of the execution, the same function gets added to the Call Stack over and over again. It looks something like this:

			                      overflowing	
step1	    step2	    step3	  foo()
			
		                foo()	  foo()
	
	        foo()	    foo()	   foo()

foo()	    foo()	    foo()	   foo()

At some point, however, the number of function calls in the Call Stack exceeds the actual size of the Call Stack, and the browser decides to take action, by throwing an error, which can look something like this:

uncaught rangeError : maximum call stack size exceeded

---

### callstack , callback queue, job queue

```
console.log('a');
setTimeout(() => console.log('b'), 0);
new Promise((resolve, reject) => {
  resolve();
})
.then(() => {
  console.log('c');
});
console.log('d');
```

o /p 

a		   // callstack
d		  // callstack
c		 // job q
d		// callback q

.then , .catch is added into job queue

The job queue, also known as the promise queue, has priority over the callback queue. (paid darshan in temple)
The event loop will take calls from the promise queue first before processing the callback queue.

---


How to install multiple version of nodejs

### Node Version Manager (nvm) : 

NVM allows installing multiple versions on the same machine.

It helps to switch among multiple Node.js versions while working on projects that require different versions. 
It saves development time by rapidly changing to the required Node.js version.

install nvm
- nvm version

Install the latest Node.js version : nvm install node

Install a Specific Node.js version : 
nvm install 8.11.1 // to install the 8.11.1 version

nvm install 12.13.1 //to install the 12.13.1 version

UnInstall Multiple Node.js Versions : nvm uninstall 12.13.1

Get a List of Installed Versions : nvm list

Switch Between Currently Installed Node.js Versions : nvm use 8.11.1  //To enable 8.11.1

Run Specific Node.js Versions Without Switching : nvm run 8.11.1 app.js

---

### Strict mode

Some of the code you write in JavaScript has errors but, JavaScript does not throw an error.

Strict mode does the following:

It throws errors for JavaScript silent errors.
It fixes mistakes that makes it difficult for JavaScript engines to perform optimizations.
It prohibits some syntax likely to be defined in future versions of the ECMAScript.
Strict mode works in an entire script file and functions, but it does not work in block scopes.

To invoke script mode you will add the "use strict"; syntax to the top of the code you want to apply it to. You can apply strict mode to a script like this:

"use strict";

let name = "Shridhar";

console.log(name);
Also, you can apply strict mode to a function like this:

function sayHi(name) {
    "use strict";
    console.log(`Hi ${name}`);
}

---

### .env file uses

NODE_ENV="development"
PORT=8081
JWT_SECRET="{{YOUR_SECRET_KEY}}"
MONGO_URI="{{YOUR_MONGODB_URI}}"
MESSAGE_BROKER_URL="{{YOUR_MESSAGE_BROKER_URL}}"

Replace YOUR_SECRET_KEY with a strong secret key, YOUR_MONGODB_URI with your MongoDB URI, and YOUR_MESSAGE_BROKER_URL with your RabbitMQ message broker URI.

---

### What is a web worker or service worker in javascript?
Web Workers and Service Workers are two different concepts in JavaScript,

Web Workers are designed for concurrent JavaScript execution in the background, while Service Workers are used for creating Progressive Web Apps with offline capabilities and advanced features. Both are essential tools for enhancing the performance and functionality of web applications.

Each serves a distinct purpose in web development:

**Web Workers:**
Concurrency: Web Workers are a browser feature that allows you to run JavaScript code in the background, separate from the main browser thread. This enables concurrent execution of tasks without blocking the user interface.

Use Cases: Web Workers are commonly used for tasks that are computationally intensive or time-consuming, such as data processing, image manipulation, or complex calculations. By running these tasks in a separate thread, they don't impact the responsiveness of the web page.

Communication: Web Workers can communicate with the main thread using a messaging system. They can send and receive messages, allowing for coordination between the main thread and the worker.

Browser Support: Web Workers are supported in most modern browsers.

**Service Workers:**

**Offline Capabilities**: Service Workers are a more advanced feature used for creating Progressive Web Apps (PWAs). They act as proxy servers that run in the background and can intercept and cache network requests. This enables offline capabilities, such as serving cached content when the user is offline.

**Use Cases:** Service Workers are primarily used for implementing features like offline access, push notifications, and background sync. They enable web apps to function even when there's no internet connection.

**Lifecycle**: Service Workers have their own lifecycle with events like install, activate, and fetch. They are typically registered at the beginning of a web app's life.

**Browser Support**: Service Workers are supported in modern browsers and are a key technology for creating reliable and engaging web applications.

---

### What is Event delegation?
Event delegation is a JavaScript programming technique that optimizes event handling for multiple elements.

Instead of attaching an event listener to each individual element, event delegation involves attaching a single event listener to a common ancestor element that is higher up in the DOM (Document Object Model) hierarchy.

When an event occurs on one of the descendant elements, it "bubbles up" to the common ancestor, where the event listener is waiting.

Event delegation is a technique for listening to events where you delegate a parent element as the listener for all of the events that happen inside it.

```
var form = document.querySelector("#registration-form");
// Listen for changes to fields inside the form
form.addEventListener(
  "input",
  function (event) {
    // Log the field that was changed
    console.log(event.target);
  },
  false
);
```
