
### Here are the array methods with syntax, definition, example, and output:

1. `forEach()`

Syntax: `array.forEach(callback(element, index, array))`

Definition: Iterate over an array and perform an action for each element.

Example: `const numbers = [1, 2, 3, 4, 5]; numbers.forEach((num) => console.log(num));`

Output: `1 2 3 4 5`

---

1. `map()`

Syntax: `array.map(callback(element, index, array))`

Definition: Transform each element in the array and return a new array.

Example: `const numbers = [1, 2, 3, 4, 5]; const doubledNumbers = numbers.map((num) => num * 2);`

Output: `[2, 4, 6, 8, 10]`

---

2. `filter()`

Syntax: `array.filter(callback(element, index, array))`

Definition: Create a new array with only the elements that pass the test.

Example: `const numbers = [1, 2, 3, 4, 5]; const evenNumbers = numbers.filter((num) => num % 2 === 0);`

Output: `[2, 4]`

---

3. `reduce()`

Syntax: `array.reduce(callback(accumulator, element, index, array), initialValue)`

Definition: Reduce the array to a single value by applying a callback function.

Example: `const numbers = [1, 2, 3, 4, 5]; const sum = numbers.reduce((acc, num) => acc + num, 0);`

Output: `15`


---

4. `find()`

Syntax: `array.find(callback(element, index, array))`

Definition: Find the first element that satisfies the test.

Example: `const numbers = [1, 2, 3, 4, 5]; const foundNumber = numbers.find((num) => num > 3);`

Output: `4`

---

5. `some()`

Syntax: `array.some(callback(element, index, array))`

Definition: Check if at least one element satisfies the test.

Example: `const numbers = [1, 2, 3, 4, 5]; const hasEvenNumber = numbers.some((num) => num % 2 === 0);`

Output: `true`

---

6. `every()`

Syntax: `array.every(callback(element, index, array))`

Definition: Check if all elements satisfy the test.

Example: `const numbers = [1, 2, 3, 4, 5]; const allPositive = numbers.every((num) => num > 0);`

Output: `true`

---

7. `includes()`

Syntax: `array.includes(element)`

Definition: Check if the array contains a specific element.

Example: `const numbers = [1, 2, 3, 4, 5]; const includesThree = numbers.includes(3);`

Output: `true`

---

8. `indexOf()`

Syntax: `array.indexOf(element)`

Definition: Find the index of the first occurrence of an element.

Example: `const numbers = [1, 2, 3, 4, 5]; const index = numbers.indexOf(3);`

Output: `2`

---

9. `push()`



Syntax: `array.push(element1, element2, ...)`

Definition: Add elements to the end of the array.

Example: `const numbers = [1, 2, 3]; numbers.push(4, 5);`

Output: `[1, 2, 3, 4, 5]`

---
10. `pop()`

Syntax: `array.pop()`

Definition: Remove the last element from the array.

Example: `const numbers = [1, 2, 3]; numbers.pop();`

Output: `[1, 2]`

---

11. `shift()`

Syntax: `array.shift()`

Definition: Remove the first element from the array.

Example: `const numbers = [1, 2, 3]; numbers.shift();`

Output: `[2, 3]`

---

12. `unshift()`

Syntax: `array.unshift(element1, element2, ...)`

Definition: Add elements to the beginning of the array.

Example: `const numbers = [2, 3]; numbers.unshift(1);`

Output: `[1, 2, 3]`

---

13. `splice()`

Syntax: `array.splice(index, deleteCount, element1, element2, ...)`

Definition: Add or remove elements from the array.

Example: `const numbers = [1, 2, 3, 4, 5]; numbers.splice(2, 1, 6, 7);`

Output: `[1, 2, 6, 7, 4, 5]`

---

14. `slice()`

Syntax: `array.splice(index, deleteCount, element1, element2, ...)`

Definition: Add or remove elements from the array.

Example: 
```
const numbers = [1, 2, 3, 4, 5];
numbers.splice(2, 1, 6, 7);

Output: `[1, 2, 6, 7, 4, 5]`
```

In this example, the `splice()` method removes 1 element starting at index 2 (which is the number 3) and adds the numbers 6 and 7 in its place.

---
---

### `splice()`

Yes, `splice()` can be used to add or remove elements to an array. Here's how:

`array.splice(index, 0, element1, element2, ...)`

- `index`: The position where you want to add the elements.

- `0`: The number of elements to remove (in this case, 0, because you're adding elements).

- `element1, element2, ...`: The elements to add.

Example:

```
const numbers = [1, 2, 3];
numbers.splice(1, 0, 4, 5); // [1, 4, 5, 2, 3]

```

In this example, `splice()` adds `4` and `5` at index `1`, shifting the existing elements to the right.

Note that `splice()` can also be used to remove elements (by specifying a value greater than 0 for the second argument) or replace elements (by specifying a value for the second argument and providing new elements).

Here are some more examples:

- Add a single element: `numbers.splice(1, 0, 4)`

- Add multiple elements: `numbers.splice(1, 0, 4, 5, 6)`

- Remove and add elements: `numbers.splice(1, 2, 4, 5)` (removes 2 elements starting at index 1 and adds 4 and 5)


Splice 2nd parameter if

- 0 means add element

- Greater than 0
    Like
    If 1 : means remove 1 element
    If 2 : means remove 2 elements

add or remove both can check index which is 1st parameter of splice

---
---

### `slice()` is a method that returns a shallow copy of a portion of an array or a string. Means not modify original array

Here's how it works:

*Array Slice:*

`array.slice(start, end)`

- `start`: The index where the slice starts (inclusive).

- `end`: The index where the slice ends (exclusive).

Example:

```
const numbers = [1, 2, 3, 4, 5];

const slicedNumbers = numbers.slice(1, 3); // [2, 3]

```

*String Slice:*

`string.slice(start, end)`

- `start`: The index where the slice starts (inclusive).

- `end`: The index where the slice ends (exclusive).

Example:

```

const greeting = "Hello World!";

const slicedGreeting = greeting.slice(6, 11); // "World"

```

Note that `slice()` returns a new array or string, leaving the original unchanged.

Also, if you omit the `end` parameter, `slice()` will extract all elements or characters from the `start` index to the end of the array or string.

Example:

```

const numbers = [1, 2, 3, 4, 5];

const slicedNumbers = numbers.slice(2); // [3, 4, 5]

```

---
---
---

### `slice()` and `splice()` 

`slice()` and `splice()` are two array methods in JavaScript that are often confused with each other due to their similar names. However, they serve different purposes:
 
`slice()`
 
- Returns a shallow copy of a portion of an array
- Does not modify the original array
- Takes two optional arguments: `start` and `end` indices
- Returns a new array with elements from `start` to `end-1`
 
Example:
```
const arr = [1, 2, 3, 4, 5];
const slicedArr = arr.slice(1, 3); // [2, 3]
console.log(arr); // [1, 2, 3, 4, 5] (original array remains unchanged)
```
 
`splice()`
 
- Modifies the original array by removing or replacing elements
- Returns an array of removed elements (if any)
- Takes three optional arguments: `start`, `deleteCount`, and `items` to insert
- Removes `deleteCount` elements starting from `start` index and inserts `items` at that position
 
Example:
```
const arr = [1, 2, 3, 4, 5];
arr.splice(1, 2, 'a', 'b'); // [1, 'a', 'b', 4, 5]
console.log(arr); // [1, 'a', 'b', 4, 5] (original array is modified)
```
 
In summary:
 
- `slice()` creates a new array copy without modifying the original array.
- `splice()` modifies the original array by removing or replacing elements.
 
When to use each:
 
- Use `slice()` when you need a copy of a portion of an array without modifying the original array.
- Use `splice()` when you need to modify the original array by removing or replacing elements.
