coding ques imp: https://blog.bitsrc.io/most-important-javascript-coding-challenge-aa14c956d2df

----

event loop phases example

https://javascriptcentric.medium.com/javascript-interview-preparation-priority-of-callback-promise-settimeout-and-process-nexttick-93be400470a8

---

sort array : [5,200,6]

const arr = [5,200,6]
arr.sort((a,b)=>a-b);			// for desc : b-a
console.log(arr)

sort method sort the array and modify the original arry. if you want the preserve original array,you can use slice() to create copy of arrya before sorting it.

const arr = [5,200,6]
const sortedArr = arr.slice().sort((a,b)=>a-b);
console.log(sortedArr)



---

#### Reverse a string without any built-in method:
```
function reverseString(str) {
    let reverseString = "";
    for (let i = str.length - 1; i >= 0; i -- ) {
        reverseString += str[i];
    }
    return reverseString;
}
const result = reverseString("hello world");
console.log(result); // dlrow olleh
```
---

#### Program : Given string is a palindrome (reads the same forwards and backwards)

```
use above logic to check without inbuild method.

function isPalindrome(str) { 

  return str === str.split(”).reverse().join(”); 

}
```
---

#### Program : check if a number is prime or not

```
// take input from the user
const number = parseInt(prompt("Enter a positive number: "));
let isPrime = true;

                       
if (number < 1) {
    // check if number is less than 1
    console.log("The number is not a prime number.");
} else if (number === 1) {
    // check if number is equal to 1
    console.log("1 is neither prime nor composite number.");
} else if (number > 1) {
    // looping through 2 to number-1     //dont take last number bcz its always divided by itselt
    for (let i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
    }

    if (isPrime) {
        console.log(`${number} is a prime number`);
    } else {
        console.log(`${number} is a not prime number`);
    }
}
```
---

#### Program : Fibonacci Series Using For-loop

```
function fibo(num){
    console.log('Fibonacci Series:');
    let n1=0, n2=1, nextTerm=0
    for(let i=1; i<=num; i++){
        console.log(n1) //print n1
        nextTerm=n1+n2;
        n1=n2;
        n2=nextTerm;
    }
}

fibo(5)

o/p : 0 1 1 2 3

```
The for loop iterates up to the number entered by the user.
0 is printed at first. Then, in each iteration, the value of the second term is stored in variable n1 and the sum of two previous terms is stored in variable n2.

---

#### Program : fibo using recursion

```
function fibonacci(num) {
    if(num < 2) {
        return num;
    }
    else {
        return fibonacci(num-1) + fibonacci(num - 2);
    }
}

function fibo(num){
    for(let i = 0; i < num; i++) {
        fibonacci(i)
    }
}

fibo(6)
```
---

#### Program : write program to get following output

```

const inp = [
 
  { user: 'UserA', city: 'Bangalore' },
 
  { user: 'UserB', city: 'Delhi' },
 
  { user: 'UserC', city: 'Bangalore' }
 
];

required op
const output = [
 
  { city: 'Bangalore', users: ['UserA', 'userC'] },
 
  { city: 'Delhi', users: ['UserB'] }
 
]

**program**

let result = [];
 
inp.forEach( ({ user, city }) => {
      let cityObj = result.find(obj => obj.city === city);
    
      if (cityObj) {
        cityObj.users.push(user);
      } else {
        result.push({ city: city, users: [user] });
      }
      
});
 
console.log(result);

```
---

#### argument binding addition of infinite number of parameter

```
addition of infinite number of parameter send to function - argument binding

function sum(){
	//console.log(arguments[0]);
	let sum = 0
	for(let i=0; i<arguments.length; i++){
	    sum+=arguments[i]
	}
	console.log(sum)
}

sum(2,3)
sum(2,3,8)
sum(2,3,10)

```
---

#### function chaining

```
function main(num) {
  let i = num;
  return {
    add: function (num) {
      i += num;
      return this;
    },
    subtract: function (num) {
      i -= num;
      return this;
    },
    multiple: function (num) {
      i *= num;
      return this;
    },
    print() {
      return i;
    },
  };
}

const x1 = main(10);
const value = x1.add(6).subtract(4).multiple(3).print();
console.log(value)

```
---

#### Program : factorial

```
function factorial(number) { 
  if (number === 0 || number === 1) { 
    return 1; 
  } else { 
    return number * factorial(number-1); 
  } 
} 

let res = factorial(4)
console.log(res) //4*3*2
```
---

#### Reverse string without inbuilt methods

```
function reverseString(str) { 
  let reversed = ”; 
  for (let i = str.length – 1; i >= 0; i–) { 
    reversed += str[i]; 
  } 
  return reversed; 
}

```
---

#### Program : Remove duplicates or get unique numbers from an array. 
```
function removeDuplicates(arr) { 
    let abc =  new Set(arr); 
    return abc; //Set(4) { 1, 2, 3, 12 }
  //return Array.from(new Set(arr)) // [ 1, 2, 3, 12 ]
}

or

function removeDuplicates(arr) { 

  return arr.filter(function(item, index) {
            return (arr.indexOf(item) === index)
        }
      ); 
} 

let res = removeDuplicates([1,1,4,2,4,1])
console.log(res) // [1,4,2]

console.log(getUniqueElements([1,2,3,1,12]))
```
---

#### Program : write a function to count the occurrences of each character in the string. 

```
function countCharacterOccurrences(str) { 

  const charCount = {}; 

  for (let char of str) { 
    charCount[char] = (charCount[char] || 0) + 1; 
  }
  
  return charCount; 
} 

let res = countCharacterOccurrences('hii')
console.log(res)

o/p : { h: 1, i: 2 }

```
---

#### Program : 
```

var res = [];

for(var i=0; i<5; i++){
	res[i]=function(){
		return i;
	}
}

console.log(res)
```
---

#### Program : 
```
input : uoy-era-woh
o/p : how are you

function reverseString(){
   var string ="uoy-era-woh"
   let result =   string.split('').reverse().join('')
   return result
}

let res = reverseString() // how-are-you
console.log(res.split('-').join(' ')) // how are you

==========



let person = {    
    x:15,
    add: () => { 
        return person.x   //if this.x then undefined
    } 
};

let a = person.add;
console.log(a()) //15


const obj = {
  a: 10,
  b: () => {
    console.log(obj.a); //10
  }
};
 
let op = obj.b;
op(); 


let show = {    
    x:20,
    add: () => { 
        return show.x+10
    } 
};

let ab =show.add(4)
console.log(ab) // 30

=======

const obj = {
  a: 10,
  b: function() {
    console.log(this.a); // 10.   //but simply console.log(a) then error
  }
};

way 1 
let op = obj.b.bind(obj);
op(); 

way 2
obj.b.call(obj);

=========

function Man (){
  this.a= 19,
  this.b= () => {
    console.log(this.a);
  }
};
let abc = new Man()
abc.b() // 19

===============================

const arr = [1, 2, 3, 4, 5];
const sum = arr.reduce((total, num) => total + num);	//it will take default 0 accumulator
console.log(sum); // 15


const initialValue = 5;
const sumWithInitial = arr.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  initialValue,
);

console.log(sumWithInitial); // 20

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---


#### Program : 
```

```
---
