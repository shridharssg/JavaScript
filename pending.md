package.json how to install latest version automatically

100 req and each req takes 2 seconds, then how it will execute in node js. 

		nodejs is single threaded so it will take time ? ----done
http status code in nodejs
post -> if data inserted same then which ststaus send

fork vs spawn nodejs
what is diff between forEach / map/ for loop
how to stop forEach loop
map vs foreach

		how can handle asyn in js ---------------done
cluster

event bubling

error handling, try catch
authentication in rest api : how to use JWT in specific req
jwt
access vs refresh token
how to validate api with JWT
unit testing

logs - how u logs in ur project
	log level like error info etc
	how to disable logs for prod
bug - how u fix bugs, logs, apporach

======
put post patch = > what happend in post if record already exist

which error it will throw with status code

If server just point the duplicate, look at 4xx:

400 Bad Request - when the server will not process a request because it's obvious client fault
409 Conflict - if the server will not process a request, but the reason for that is not the client's fault
=========
1. why nestjs if we have already expressjs
2. what is controller and how to write get request -(asked to write whole code)	
3. which library used to connect with mongodb
4. how node is single threaded
5. strams - need to read data from file and write into another. how it work
6. 10000 records in file. how to store in database. optimization way
=====


which component you have worked in last
loggs handling in node

why async await if promises there
cluster and real time uses

* 1L records in json file how to read and optimize way and how to get 5 records from that
* how to use class which created in File1 and want to use in file2, want to access all its members

  ---

  jwt vs refresh token
import vs require

==============

import vs require

var myVac = import("module-name");
var myVar = require('http'); 

import is asynchronous and require is synchronous
require() can be called from anywhere inside the program whereas import() cannot be called conditionally, it always runs at the beginning of the file.

import express from "express";

You can't selectively load only the pieces you need with require but with import, you can selectively load only the pieces you need, which can save memory.

Loading is synchronous(step by step) for require on the other hand import can be asynchronous(without waiting for previous import) so it can perform a little better than require.
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

Concurrency & the Event Loop
What happens when you have function calls in the Call Stack that take a huge amount of time in order to be processed? For example, imagine that you want to do some complex image transformation with JavaScript in the browser.

You may ask — why is this even a problem? The problem is that while the Call Stack has functions to execute, the browser can’t actually do anything else — it’s getting blocked. This means that the browser can’t render, it can’t run any other code, it’s just stuck. And this creates problems if you want nice fluid UIs in your app.

And that’s not the only problem. Once your browser starts processing so many tasks in the Call Stack, it may stop being responsive for quite a long time. And most browsers take action by raising an error, asking you whether you want to terminate the web page.

So, how can we execute heavy code without blocking the UI and making the browser unresponsive? Well, the solution is asynchronous callbacks.


=====================

https://medium.com/sessionstack-blog/how-does-javascript-actually-work-part-1-b0bacc073cf


function foo() {
    foo();
}
foo();

When the engine starts executing this code, it starts with calling the function “foo”. This function, however, is recursive and starts calling itself without any termination conditions. So at every step of the execution, the same function gets added to the Call Stack over and over again. It looks something like this:

			overflowing	
step1	step2	step3	foo()
			
		foo()	foo()
	
	foo()	foo()	foo()

foo()	foo()	foo()	foo()

At some point, however, the number of function calls in the Call Stack exceeds the actual size of the Call Stack, and the browser decides to take action, by throwing an error, which can look something like this:

uncaught rangeError : maximum call stack size exceeded


===================


callstack , callback queue, job queue

console.log('a');
setTimeout(() => console.log('b'), 0);
new Promise((resolve, reject) => {
  resolve();
})
.then(() => {
  console.log('c');
});
console.log('d');


o /p 

a		   // callstack
d		  // callstack
c		 // job q
d		// callback q

.then , .catch is added into job queue

The job queue, also known as the promise queue, has priority over the callback queue. (paid darshan in temple)
The event loop will take calls from the promise queue first before processing the callback queue.

=======================

How to install multiple version of nodejs

Node Version Manager (nvm) : 
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

======================================

What is nodeJS

Node.js is an open-source JavaScript runtime environment that allows you to run JavaScript outside the browser.
Although Node.js is single-threaded, it has an event loop that makes it multi-threaded.

Single-threaded programming languages are synchronous, which means they run the task in their programs sequentially. 
JavaScript is synchronous, but its event loop makes it asynchronous.


The JavaScript runtime engine consists primarily of the:

Memory heap and
Call stack

The memory heap is where variables declared in the program are allocated memory space, 
and the call stack is where the runtime engine stores functions in the program for execution.


=============

Strict mode
Some of the code you write in JavaScript has errors but, JavaScript does not throw an error.

Strict mode does the following:

It throws errors for JavaScript silent errors.
It fixes mistakes that makes it difficult for JavaScript engines to perform optimizations.
It prohibits some syntax likely to be defined in future versions of the ECMAScript.
Strict mode works in an entire script file and functions, but it does not work in block scopes.

To invoke script mode you will add the "use strict"; syntax to the top of the code you want to apply it to. You can apply strict mode to a script like this:

"use strict";

let name = "Musab";

console.log(name);
Also, you can apply strict mode to a function like this:

function sayHi(name) {
    "use strict";
    console.log(`Hi ${name}`);
}

===============

var res = [];

for(var i=0; i<5; i++){
	res[i]=function(){
		return i;
	}
}

console.log(res)
========================================

.env file uses


NODE_ENV="development"
PORT=8081
JWT_SECRET="{{YOUR_SECRET_KEY}}"
MONGO_URI="{{YOUR_MONGODB_URI}}"
MESSAGE_BROKER_URL="{{YOUR_MESSAGE_BROKER_URL}}"


Replace YOUR_SECRET_KEY with a strong secret key, YOUR_MONGODB_URI with your MongoDB URI, and YOUR_MESSAGE_BROKER_URL with your RabbitMQ message broker URI.

---
---

memoization - js
Explain the concept of stub in Node.js.
DOM
How does the DNS lookup function work in Node.js?
In Node.js, the DNS module provides methods for performing DNS lookups. DNS stands for Domain Name System, and it is responsible for translating domain names into IP addresses. The DNS. lookup() method is used to perform a DNS lookup and resolve a domain name into an IP address.

What is web socket?

diff between event and callback

The difference between an event and a callback is that an event is a mechanism that signals a change or action that represents a part of the program's behaviour, while a callback is a function that takes data and sends it back to the calling function.


---
---

