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
