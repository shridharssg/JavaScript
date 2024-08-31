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

```
for (const key in obj) {
  if (obj.hasOwnProperty(key)) {
    console.log(key, obj[key]);
  }
}

```
Also, keep in mind that the order of iteration is not guaranteed, as object properties are not ordered in JavaScript. 
If you need to iterate over an array or an iterable in a specific order, consider using `for...of` or a traditional `for` loop instead

---

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
