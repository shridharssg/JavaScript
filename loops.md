Loops
Loops are useful for executing a block of code for a specified number of times based on some specified conditions. There are different types of loops in JavaScript:

  for loops
  for ... in loops
  for ... of loops
  while loops
  do ... while loops  

----
**How to use for loops**

for loops are used to execute a block of code a number of times:

for (let i = 0; i < 5; i++) {
    return i;
}



The "for" loop used for iterating over arrays, objects, or sequences of values.

It provides more control over the iteration process, allowing you to specify the start and end conditions, as well as the increment or decrement step.

It is typically used when you need to perform a specific action a fixed number of times or when you need fine-grained control over the loop.

It support "break" or "continue" statements for early termination or skipping iterations

**usecase**
 suppose array has 10000 records, and we want to find specific reocrd. at that time once match, we dont want to proceed more. so in this situation
for loop should be used bcz we can used break statement to check further. but same thing not possible in forEach so it iterate over 10000 records


---


How to use for ... in loops
for ... in loops are used to loop through the properties of an object:

for (let prop in obj) {
    return obj.prop;
}

---

How to use for ... of loops
for ... of loops are used to loop through the values of iterable objects like arrays, strings, maps, and so on:

let numArr = [2, 4, 6, 8]
for (let val of numArr) {
    return val ** 2
}

---

How to use while loops
while loops are used to execute a block of code while a certain condition still holds true:

while (i < 20) {
    return i;
    i++;
}

---

How to use do ... while loops
do ... while loops execute a block of code first without any conditions. For as long as a certain condition still holds true it continues to execute the block of code:

let i = 3;
do {
    return i;
    i++;
} 
while (i < 4)



============
do...while loop is similar to the while loop. 

The only difference is that 
	in do…while loop, the body of loop is executed at least once.

do {
    // body of loop
} while(condition)


---


while (condition) {
    // body of loop
}

eg.

// program to display numbers from 1 to 5
// initialize the variable

let i = 1, n = 5;

// while loop from i = 1 to 5
while (i <= n) {
    console.log(i);
    i += 1;
}

---

### What is the difference between ‘of’ and ‘in’?

For Of: It loops over the Values
For In: Loops over the Keys

---

### for...in

In JavaScript, the `for...in` loop is used to iterate over the properties of an object. Here's a basic example:

```
const obj = {a: 1, b: 2, c: 3};

for (const key in obj) {
  console.log(key, obj[key]);
}

```
This will output:

```
a 1

b 2

c 3

```

The `for...in` loop iterates over the property names (keys) of the object, and you can access the corresponding property values using `obj[key]`.

**inherited properties**

Note that `for...in` also iterates over inherited properties, so if you only want to iterate over the object's own properties, you can use the `hasOwnProperty()` method:

Also, keep in mind that the order of iteration is not guaranteed, as object properties are not ordered in JavaScript. 
If you need to iterate over an array or an iterable in a specific order, consider using `for...of` or a traditional `for` loop instead

In the example I provided earlier:

```
const obj = {a: 1, b: 2, c: 3};

```
The properties `a`, `b`, and `c` are the object's own properties, also known as "direct properties" or "own enumerable properties".

Now, let's say we have a prototype object that `obj` inherits from:

```
const prototypeObj = {x: 10, y: 20};
Object.setPrototypeOf(obj, prototypeObj);
```

In this case, `obj` inherits the properties `x` and `y` from `prototypeObj`. These inherited properties are not directly defined on `obj`, but are accessible through the prototype chain.
So, if we use `for...in` to iterate over `obj`, we'll get:

```
for (const key in obj) {
 console.log(key, obj[key]);
}
```

Output:
```
a 1
b 2
c 3
x 10
y 20
```

Notice that `x` and `y` are included in the iteration, even though they're not directly defined on `obj`. This is because `for...in` iterates over all enumerable properties, including inherited ones.

To filter out inherited properties, we can use the `hasOwnProperty()` method:

```
for (const key in obj) {
  if (obj.hasOwnProperty(key)) {
    console.log(key, obj[key]);
  }
}
```

Output:
```
a 1
b 2
c 3
```
Now, only the direct properties `a`, `b`, and `c` are included in the iteration.

---

### `for...in` With array

When using `for...in` on an array in JavaScript, it iterates over the array's property names, which are the index values (as strings) and any other enumerable properties.
Here's an example:

```
const arr = [1, 2, 3];

for (const key in arr) {
  console.log(key, arr[key]);
}

```
Output:

```
0 1
1 2
2 3
```

As you can see, `for...in` iterates over the index values (`0`, `1`, and `2`) and logs the corresponding array values.
However, if you add other properties to the array, `for...in` will also iterate over those:

```
const arr = [1, 2, 3];
arr.four = 'shridhar';

for (const key in arr) {
  console.log(key, arr[key]);
}

```

Output:

```

0 1
1 2
2 3
four shridhar

```

**To avoid this and only iterate over the array's index values, you can use a traditional `for` loop or `for...of` loop:**

```

const arr = [1, 2, 3];
for (let i = 0; i < arr.length; i++) {
  console.log(i, arr[i]);
}

// or

for (const value of arr) {
  console.log(value);
}

```
These loops will only iterate over the array's index values or values, respectively, without including any additional properties.

---
---

### `for...of`

*What is `for...of`?*

`for...of` is a loop that iterates over the values of an iterable object, such as an array, string, or Map.

*Pros:*

1. *Concise syntax*: `for...of` provides a more concise and readable way to iterate over iterables compared to traditional `for` loops.

2. *Easy to use*: It's easy to understand and use, even for developers new to JavaScript.

3. *Supports async/await*: `for...of` can be used with async/await syntax for asynchronous iteration.

4. *Iterates over values*: It iterates directly over the values of the iterable, without needing to access indices or keys.

*Cons:*

1. *Only works with iterables*: `for...of` only works with iterable objects, such as arrays, strings, Maps, and Sets. It can't be used with plain objects.

2. *No index access*: You don't have direct access to the index or key of the current iteration.

3. *No support for sparse arrays*: `for...of` will skip over empty slots in sparse arrays.

4. *Can be slower*: In some cases, `for...of` can be slower than traditional `for` loops due to the overhead of iteration protocols.

*Example usage:*
```
const arr = [1, 2, 3];

for (const value of arr) {
  console.log(value); // Output: 1, 2, 3
}

```
**IMP**
**Loops like `for...of` work with *iterable* objects, which are objects that have a specific method called `[Symbol.iterator]()`.**

*Iterable objects* include:

- Arrays (`[]`)

- Strings (`""`)

- Maps (`new Map()`)

- Sets (`new Set()`)

- Other iterable objects (like `NodeList`, `arguments`, etc.)

*Plain objects* (`{}`) are not iterable by default. They don't have the `[Symbol.iterator]()` method, so `for...of` can't iterate over them.

Example:
```
const plainObject = { a: 1, b: 2, c: 3 };

for (const value of plainObject) {
  console.log(value); // **Error: plainObject is not iterable**
}

```

**However, you can make a plain object iterable by adding the `[Symbol.iterator]()` method to it. This method should return an iterator object that defines the `next()` method.**

Here's an example:
```
const plainObject = { a: 1, b: 2, c: 3 };

plainObject[Symbol.iterator] = function* () {
  for (const key in this) {
    yield this[key];
  }
};

for (const value of plainObject) {
  console.log(value); // Output: 1, 2, 3
}

```
In this example, we've added the `[Symbol.iterator]()` method to the plain object, making it iterable. Now, `for...of` can iterate over its values.

**Keep in mind that making a plain object iterable like this is not a common practice, and it's usually better to use other data structures like arrays or Maps when you need to iterate over values.

---
---

### Diff :`for...in` and `for...of` are both loops in JavaScript, but they serve different purposes and have different behaviors.

*`for...in`*

- Iterates over the *property names* (keys) of an object

- Returns a string representing the property name

- Includes inherited properties (from prototype chain)

- Works with objects, arrays, and strings

Example:

```
const obj = {a: 1, b: 2, c: 3};

for (const key in obj) {
  console.log(key); // Output: "a", "b", "c"
}

```
*`for...of`*

- Iterates over the *values* of an iterable object (array, string, Map, Set, etc.)

- Returns the value itself (not the property name)

- Does not include inherited properties

- Works with iterables (arrays, strings, Maps, Sets, etc.), not plain objects

Example:
```
const arr = [1, 2, 3];
for (const value of arr) {
  console.log(value); // Output: 1, 2, 3
}

```
In summary:
- Use `for...in` when you need to iterate over property names (keys) of an object.

- Use `for...of` when you need to iterate over values of an iterable object (array, string, Map, Set, etc.).

---
---

### forEach

`forEach` is a method in JavaScript that allows you to iterate over an array or an iterable object, executing a provided function for each element.

 - It is often preferred when you want to perform the same action on each element of an array.
 - It does not support "break" or "continue" statements for early termination or skipping iterations;
 - It is specifically designed for iterating over the elements of an array and executing a provided function once for each element.

*Syntax:*
`array.forEach(callback(currentValue, index, array))`

*Parameters:*

- `callback`: The function to execute for each element

- `currentValue`: The current element being processed

- `index`: The index of the current element

- `array`: The array being processed

*Example:*

```
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(function(number) {
  console.log(number);
});
```

*Output:*

```

1

2

3

4

5

```

*Using arrow functions:*

```
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(number => console.log(number));
```

*Output:*

```
1

2

3

4

5

```

*Using `forEach` with objects:*

```
const obj = {a: 1, b: 2, c: 3};

Object.keys(obj).forEach(key => console.log(key, obj[key]));
```

*Output:*
```
a 1
b 2
c 3

```
Note that `forEach` does not return a new array, but rather returns `undefined`. If you need to return a new array, consider using `map()` instead.


**In the `forEach` method, the `callback` function takes three parameters:**

1. `currentValue`: This is the element itself, which is being processed in the current iteration. You can use this parameter to access the value of the current element.

2. `index`: This is the index of the current element in the array. You can use this parameter to access the index of the current element.

3. `array`: This is the array being processed. You can use this parameter to access the entire array.

Here's an example to illustrate this:

```
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(currentValue, index, array) {
  console.log(`Current Value: ${currentValue}, Index: ${index}, Array: ${array}`);
});

```

Output:

```
Current Value: 1, Index: 0, Array: 1,2,3,4,5

Current Value: 2, Index: 1, Array: 1,2,3,4,5

Current Value: 3, Index: 2, Array: 1,2,3,4,5

Current Value: 4, Index: 3, Array: 1,2,3,4,5

Current Value: 5, Index: 4, Array: 1,2,3,4,5

```

In this example, we're logging the current value, index, and array in each iteration. This demonstrates how you can access these parameters within the `forEach` callback function.


**Foreach array parameter : modify original array example**

use case for the `array` parameter would be when you need to modify the original array or access its properties within the `forEach` callback function.

Here's an example:

```
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(currentValue, index, array) {
  array[index] = currentValue * 2; // modify the original array
});

console.log(numbers); // Output: [2, 4, 6, 8, 10]

```

In this example, we're using the `array` parameter to modify the original array by multiplying each element by 2.

---
---

### Map

The `map()` function in JavaScript is a powerful array method that creates a new array with the results of applying a provided function to every element in the original array.

Here's the basic syntax:

`const newArray = array.map(function(currentValue, index, array) { /* return new value */ });`

**Key points:**

- `map()` returns a new array, leaving the original array unchanged.

- The callback function receives three arguments: `currentValue`, `index`, and `array`.

- The callback function should return a new value to be included in the resulting array.


Example:

```
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map(function(num) { return num * 2; });

console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]

```

**Common use cases:**

- Transforming data (e.g., converting strings to uppercase)

- Extracting specific properties from objects

- Performing calculations on array elements

**Note that `map()` is chainable, meaning you can combine it with other array methods like `filter()` or `reduce()` to create more complex data transformations.**

---

### `map()` and `forEach()` are both array methods in JavaScript, but they serve different purposes:

*`forEach()`*

- Iterates over the array, executing a callback function for each element

- Returns `undefined`

- Modifies the original array (if the callback function does so)

- Focus: Executing a side effect or modifying the original array


*`map()`*

- Iterates over the array, executing a callback function for each element

- Returns a new array with the transformed elements

- Leaves the original array unchanged

- Focus: Transforming data and creating a new array

Key differences:

- Return value: `forEach()` returns `undefined`, while `map()` returns a new array

- Mutation: `forEach()` can modify the original array, while `map()` leaves it unchanged

- Purpose: `forEach()` for side effects or modifications, `map()` for transformations and new arrays


Choose `forEach()` when:

- You need to execute a side effect (e.g., logging, updating an external variable)

- You want to modify the original array

Choose `map()` when:

- You need to transform data and create a new array

- You want to preserve the original array

Here's an example that demonstrates the difference:

```

const numbers = [1, 2, 3];

// Using forEach()

numbers.forEach((num) => {
  console.log(num * 2); // Logs 2, 4, 6
});

console.log(numbers); // Still [1, 2, 3]



// Using map()

const doubledNumbers = numbers.map((num) => num * 2);

console.log(doubledNumbers); // [2, 4, 6]

console.log(numbers); // Still [1, 2, 3]

```

In summary, `forEach()` is for executing side effects or modifying the original array, while `map()` is for transforming data and creating a new array.

