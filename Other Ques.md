https://javascriptcentric.medium.com/top-50-nodejs-interview-questions-and-answers-for-2024-5e460dac7852

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

### Difference between pipe and chaining in a node?

Pipe: In Node.js, the “pipe” method is used to direct the output of one stream to the input of another stream. It is commonly used with readable and writable streams to efficiently transfer data from one source to another without explicitly having to manage the data flow.

```
const fs = require('fs');

const readableStream = fs.createReadStream('input.txt');
const writableStream = fs.createWriteStream('output.txt');

readableStream.pipe(writableStream);
```

Chaining in Node.js generally refers to method chaining, which is the practice of calling multiple methods on an object in a single statement, with each method returning the object itself, thereby allowing for a sequence of operations to be performed on the object in a linear fashion.
```
const result = [1, 2, 3, 4, 5]
  .map(num => num * 2)
  .filter(num => num > 5)
  .reduce((acc, num) => acc + num, 0);

console.log(result); // Output: 24
```

Both concepts are fundamental to working with streams and asynchronous operations in Node.js.

---

### What is the control flow function?

Control flow functions are used to dictate the order in which specific code blocks or functions are executed. These functions are used to manage the flow of execution within a program, enabling developers to handle asynchronous operations, iterate through collections, handle conditional logic, and more.

---

### What is CORS?
CORS stands for Cross-Origin Resource Sharing. It is a security feature implemented in web browsers to restrict web pages from making requests to a different domain than the one that served the web page.

In a Node.js application, you can set up CORS handling using middleware such as the ‘cors’ package or by manually adding the necessary CORS headers to responses. This allows you to control which origins have permission to access resources in your Node.js application.

CORS is a security feature that regulates cross-origin requests, allowing secure communication between different domains while protecting users’ data from unauthorized access and potential security threats.

When you visit a website, let’s say “example.com”, your web browser allows JavaScript code running on “example.com” to make requests to the same domain. This is part of the security protocol called the same-origin policy, and it’s meant to protect users’ data from malicious attacks.

However, sometimes a web page might need to make requests to a different domain. For example, let’s say “example.com” needs to retrieve some data from “api.otherdomain.com”. This is where CORS comes into play.

---

###  Difference between crypto and bcrypt module?

**crypto Module**: The crypto module in Node.js provides cryptographic functionality, including encryption, hashing, and decryption. It offers a wide range of cryptographic algorithms and tools for handling secure data transformations.

```
   const crypto = require('crypto');

   const password = 'mySecurePassword';
   const salt = crypto.randomBytes(16).toString('hex'); // Generate a random salt
   const hash = crypto.pbkdf2Sync(password, salt, 100000, 64, 'sha512').toString('hex'); // Generate a hashed password

   console.log('Salt:', salt);
   console.log('Hashed Password:', hash);
```

**bcrypt Module**: The bcrypt module is specifically designed for password hashing using the bcrypt algorithm. It provides a convenient way to securely hash passwords, a common requirement for user authentication systems. bcrypt automatically handles the generation of salts, which enhances the security of the hashed passwords.

```
   const bcrypt = require('bcrypt');
   const saltRounds = 10;
   const myPlaintextPassword = 'mySecurePassword';

   bcrypt.hash(myPlaintextPassword, saltRounds, function(err, hash) {
     if (!err) {
       console.log('Hashed Password:', hash);
     }
   });
```
   ---

### Difference between req.params and req.query?

In the context of a Node.js server using the Express framework, req.params and req.query are used to access different types of parameters passed in the URL.

req.params is an object containing properties mapped to the named route parameters. These parameters are part of the URL path and are matched by the route’s path pattern. They are typically used to capture dynamic values from the URL.

```
// Route definition
app.get('/users/:id', (req, res) => {
    const userId = req.params.id; // Access the "id" parameter from the URL
    // Use userId to retrieve user data
});
```

req.query is an object containing a property for each query string parameter in the route. Query parameters are appended to the URL after a ? and are used to pass additional information or filters for the requested resource.

If you have a route defined as /search, and a client makes a request like /search?city=NewYork&active=true, you can access the query parameters city and active using req.query.city and req.query.active respectively.

```
  // Route definition
  app.get('/search', (req, res) => {
      const city = req.query.city; // Access the "city" query parameter
      const active = req.query.active; // Access the "active" query parameter
      // Use city and active for searching
  });
```
---

### Difference between dependency and dev-dependency?
Dependencies are the packages that are required for the application to run in the production environment.

DevDependencies are the packages that are only needed for development and testing purposes. These packages include tools, libraries, and utilities that are used during the development, testing, and build process, but are not required for the application to function in the production environment.

---

### What is the error first callback function?
The “error-first callback” pattern, also known as “Node.js-style callbacks”, is a convention used in Node.js for handling asynchronous operations. In this pattern, callback functions are structured to take an error as the first parameter, allowing the calling code to check for and handle errors in a consistent manner.

```
function readFileAndHandleError(path, callback) {
  fs.readFile(path, 'utf8', (err, data) => {
    if (err) {
      // Pass the error to the callback as the first parameter
      callback(err);
    } else {
      // Pass the data to the callback as the second parameter
      callback(null, data);
    }
  });
}

// Example usage of the error-first callback function
readFileAndHandleError('example.txt', (err, data) => {
  if (err) {
    console.error('An error occurred:', err);
  } else {
    console.log('File data:', data);
  }
});

```
---

### Difference between Authentication and Authorization?

Authentication is the process of validating the identity of a user or entity, through the credentials, such as usernames, passwords, biometric data, or security tokens.

Authorization is the process of determining the rights and privileges of a user to access the resources. Authorization typically involves specifying what resources or operations a user can interact with based on their role, group membership, or other relevant attributes.

---

### What is cron job?
A cron job is a time-based job scheduler. It allows users to schedule tasks (commands or scripts) to run periodically at fixed times, dates, or intervals.

In Node.js, you can use the node-cron module to schedule jobs to run at specific times.

```
const cron = require('node-cron');

// Schedule a job to run every minute
cron.schedule('* * * * *', () => {
  console.log('Running scheduled job every minute');
});
```
The first argument ‘* * * * *’ represents the cron expression for running the job every minute. The second argument … is a function that will be executed when the scheduled time is reached.

```
Run a Job Every Hour:

   const cron = require('node-cron');

   // Schedule a job to run every hour
   cron.schedule('0 * * * *', () => {
     console.log('Running scheduled job every hour');
   });
```

```
Run a Job Every Day at a Specific Time:

   const cron = require('node-cron');

   // Schedule a job to run at 8:00 AM every day
   cron.schedule('0 8 * * *', () => {
     console.log('Running scheduled job at 8:00 AM every day');
   });
```
  ---
