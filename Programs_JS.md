#### Program : Given string is a palindrome (reads the same forwards and backwards)

```
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

```
---

#### 

```

```
---

#### 

```

```
---

#### 

```

```
---

#### 

```

```
---