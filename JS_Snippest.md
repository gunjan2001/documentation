# var and let example

```
for (var i = 0 i < 3 i++) {
	setTimeout(() => console.log(i), 1000);
}
// 3 3 3

for (let i = 0 i < 3 i++) {
	setTimeout(() => console.log(i), 1000);
}
// 0 1 2
```

# Hoisting code snippest:

```
const abc = () => {
  var x = 10;
  if(true){
    var x = 20;
    console.log(x); // 20
  }
  console.log(x); // 20
}


const abc = () => {
  let x = 10;
  if(true){
    let x = 20;
    console.log(x); // 20
  }
  console.log(x); // 10
}
abc();

const abc = () => {
  const x = 10;
  if(true){
    const x = 20;
    console.log(x); // 20
  }
  console.log(x); // 10
}
abc();

console.log(x) // undefine
var x = 10;
```

**`binary (+) & unary (+)`**

- binary plus : string concatination
- unary plus : Numeric conversion -> `if we apply + before any value it will convert that value to number not apply numbers`

```
// Converts non-numbers
alert( +true ); // 1
alert( +"" );   // 0
```

### calculation with plus

```
string + number = string concatination
number + string  = string concatination
null + number = number
```

```
alert( '2' > 1 ); // true, string '2' becomes a number 2
alert( '01' == 1 ); // true, string '01' becomes a number 1
```

```
alert( null === undefined ); // false
alert( null == undefined ); // true
```

- **For maths and other comparisons < > <= >=**
- **null/undefined are converted to numbers: null becomes 0, while undefined becomes NaN**

**An incomparable undefined**
**The value undefined shouldn’t be compared to other values so it will gives false**

### **`The values null and undefined equal == each other and do not equal any other value.`**

## Objects

```
function makeUser() {
  return {
    name: "John",
    ref: this
  };
}

let user = makeUser();

alert( user.ref.name ); // What's the result? =>  // Error: Cannot read property 'name' of undefined
```

- That’s because rules that set this do not look at object definition. Only the moment of call matters.
- Here the value of this inside makeUser() is undefined, because it is called as a function, not as a method with “dot” syntax.
- insted of that we can do like below:

```
function makeUser() {
  return {
    name: "John",
    ref() {
      return this;
    }
  };
}

let user = makeUser();

alert( user.ref().name ); // John
```

**Objects Questions: https://javascript.info/object-methods#tasks**

- **Static methods are designed to live only on the constructor in which they are created, and cannot be passed down to any children or called upon class instances.**


## primitives:

```
let str = "Hello";

str.test = 5; // (*)

alert(str.test);
```

- Depending on whether you have use strict or not, the result may be:

- undefined (no strict mode)
- An error (strict mode).

## Array:

```
let arr = ["a", "b"];

arr.push(function() {
  alert( this );
})

arr[2]();
```

- here this will refer to that array object so it prints all values of array.

<hr/>
<hr/>

```
const obj = {
  a: 1,
  b: 2,
  sum() {
    return this.a + this.b;
  }
};

const res = obj.sum; 
console.log(res()) // NaN: because this.a give undefine and undefine + undefine is NaN.

SOLUTION to get 3:
const res = obj.sum.bind(obj); 
```

## Questions:

1. Copied Object

```
const user = {
  name: 'Raj',
  location: {
    city: 'NY',
    state: 'NY'
  }
};
const copy = Object.assign({}, user);
// OR
// const copy = { ...user };
copy.location.city = 'Albany';
console.log('original: ', user.location);
console.log('copy:', copy.location);
```

**Output:**

- The reason for the changed original object is because when we use Object.assign or spread operator, it only does shallow copy, which means while creating a copy of the object, properties of only the first level are copied and if there are nested properties then only their reference is copied which means the copied reference still refers to the original place where the object is stored.

```
original:  {
  city: 'Albany',
  state: 'NY'
}
copy: {
  city: 'Albany',
  state: 'NY'
}
```

2. Hoisting

```
var number = 10;
var display = function () {
  console.log(number);
  var number = 20;
};
display();
```

**Output:**

- The reason for undefine is hoisting see below:

```
var number = 10;
var display = function () {
  var number; // here the number is redeclare and is not assigned any value so it is undefined
  console.log(number);
  number = 20;
};
display();
```

```
undefined
```

<hr/>

```
const number = 1;
const result = (function () {
  delete number;
  return number;
})();
console.log(result);
```

**output:**

```
1
```

- because here the delete is used for deleteing object property not premitive type number and also it will not throw error.

<hr/>

```
const number = 1;
const result = (function (number) {
  delete number;
  return number;
})(10);
console.log(result);
```

**Output:**

```
10
```

<hr/>

```
function display() {
  var a = b = 10;
}
display();
console.log('b', typeof b === 'undefined');
console.log('a', typeof a === 'undefined');
```

**Output:**

```
function display() {
  b = 10;  // here b is global so it is accessible to outside of this display() function so it is not undefined
  var a = b; // but here a is in block scope so it is not accessible outside of display function
 }

```

<hr/>

```
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```

**Output:**

```
outer func:  this.foo = bar
outer func:  self.foo = bar
inner func:  this.foo = undefined // because here this will check refrence to it's parents and here `foo` is not defined in outside of function scope
inner func:  self.foo = bar
```

<hr/>

```
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}
```

**Output:**

```
foo1: { bar: "hello" }
foo2: undefined
```

<hr/>

```
console.log(0.1 + 0.2);
console.log(0.1 + 0.2 == 0.3);

```

**Output:**

```
0.300000000000000000004
false // because 0.1 + 0.3 will give above ans and it will not same as 0.3
```

<hr/>

**Palindrome**

```
function isPalindrome(str) {
  str = str.replace(/\W/g, '').toLowerCase(); // remove white space
  return (str == str.split('').reverse().join(''));
}
```

<hr/>

```
var arr1 = "john".split('');
var arr2 = arr1.reverse();
var arr3 = "jones".split('');
arr2.push(arr3);
console.log("array 1: length=" + arr1.length + " last=" + arr1.slice(-1));
console.log("array 2: length=" + arr2.length + " last=" + arr2.slice(-1));
```

**Output:**

```
array 1: length=5 last=j,o,n,e,s
array 2: length=5 last=j,o,n,e,s
```

- here arr2 will push whole array as last element and whatever we perform on one array it will affect that original array. so that's why here the arr1 is changed accordingly.
- and here let and const is also give same result.

<hr/>

```
console.log(1 +  "2" + "2");
console.log(1 +  +"2" + "2");
console.log(1 +  -"1" + "2");
console.log(+"1" +  "1" + "2");
console.log( "A" - "B" + "2");
console.log( "A" - "B" + 2);
```

**Output:**

```
"122"
"32"
"02"
"112"
"NaN2"
NaN
```

<hr/>

```
console.log(false == '0')
console.log(false === '0')
```

**Output:**

```
true
false
```

<hr/>

```
var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;
a[c]=456;

console.log(a[b]);
```

**Output:**

```
456
```

- In JavaScript, when an object is used as a key in another object (or in a Map), it is implicitly converted to a string. This conversion is done by calling the toString() method on the object. By default, the toString() method returns [object Object] for objects.

- In the code snippet, b and c are separate objects with different memory references, even though they have the same key value ('b' and 'c' respectively). When you use a[b] and a[c] as property keys, both b and c are implicitly converted to the same string representation, which is "[object Object]". As a result, a[b] and a[c] are treated as the same property.

- When you assign 123 to a[b] and then 456 to a[c], the value 456 overrides the previous value 123. So, when you log a[b] to the console, it retrieves the most recent value assigned to the property with the key "[object Object]", which is 456.

<hr/>

**Most Imp**

```
var length = 10;
function fn() {
	console.log(this.length);
}

var obj = {
  length: 5,
  method: function(fn) {
    fn();
    arguments[0]();
  }
};

obj.method(fn, 1);
```

**Output:**

```
10
2
```

Explanation:

In the first place, as fn is passed as a parameter to the function method, the scope (this) of the function fn is window. var length = 10; is declared at the window level. It also can be accessed as window.length or length or this.length (when this === window.)

method is bound to Object obj, and obj.method is called with parameters fn and 1. Though method is accepting only one parameter, while invoking it has passed two parameters; the first is a function callback and other is just a number.

When fn() is called inside method, which was passed the function as a parameter at the global level, this.length will have access to var length = 10 (declared globally) not length = 5 as defined in Object obj.

Now, we know that we can access any number of arguments in a JavaScript function using the arguments[] array.

**Arrow functions do not have "arguments"**

- If we access the arguments object from an arrow function, it takes them from the outer “normal” function.

Hence arguments[0]() is nothing but calling fn(). Inside fn now, the scope of this function becomes the arguments array, and logging the length of arguments[] will return 2.

<hr/>

```
var x = 21;
var girl = function () {
    console.log(x);
    var x = 20;
};
girl ();
```

**Output:**

```
undefined
```

<hr/>

```
for (let i = 0; i < 5; i++) {
  setTimeout(function() { console.log(i); }, i * 1000 );
}
```

**output:**

```
0 1 2 3 4
```

<hr/>

```
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

**output:**

```
true < 3 => 1 < 3 => true
true > 1 => 1 > 3 => false
```

<hr/>

```
typeof undefined == typeof NULL
typeof undefined === typeof NULL
```

**output:**

```
true
true
```

<hr/>

```
var b = 1;
function outer(){
   	var b = 2
    function inner(){
        b++;
        var b = 3;
        console.log(b)
    }
    inner();
}
outer();
```

**output:**

```
3
```

<hr/>

```
function bark() {
  console.log('Woof!');
}

bark.animal = 'dog';
```

**Output:**

- This is possible in JavaScript, because functions are objects! (Everything besides primitive types are objects)
- A function is a special type of object. The code you write yourself isn't the actual function. The function is an object with properties. This property is invocable.

<hr/>

```
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

const member = new Person('Lydia', 'Hallie');
Person.getFullName = function() {
  return `${this.firstName} ${this.lastName}`;
};

console.log(member.getFullName());
```

**Output:**

- TypeError

```
let arr = [
  { name: "djkas", age: 31, surname: "djkash", id: 3 },
  { name: "John", age: 21, surname: "Smith", id: 1 },
  { name: "Pete", age: 26, surname: "Hunt", id: 2 },
  { name: "Mary", age: 31, surname: "Key", id: 3 },
];

// concat two names

let ans = arr.reduce((newArr, curr) => {
  newArr.push(`${curr.name} ${curr.surname}`);
  return newArr;
}, []);

// find multiple counts of age
let ageCount = arr.reduce((ansObj, curr) => {
  let age = curr.age;
  if (ansObj[age]) {
    ansObj[age]++;
  } else {
    ansObj[age] = 1;
  }
  return ansObj;
}, {});

// filter age < 30 and print their full name in array

// let filterNames = arr.reduce((nameArr, curr) => {
//   if (curr.age < 30) {
//     nameArr.push(`${curr.name} ${curr.surname}`);
//   }
//   return nameArr;
// }, []);

// console.log(ans);
// console.log(ageCount);
// console.log(filterNames);

// -------------

// function unique(arr) {
//   let ans = new Set();
//   arr.forEach((user) => {
//     ans.add(user);
//   });
//   return ans;
// }

function unique(arr) {
  let ans = new Set();
  ans = arr;
  return ans;
}

let values = [
  "Hare",
  "Krishna",
  "Hare",
  "Krishna",
  "Krishna",
  "Krishna",
  "Hare",
  "Hare",
  ":-O",
];

console.log(values);
console.log(unique(values));

// ------------------------------------------
// Write a function aclean(arr) that returns an array cleaned from anagrams.
// let arr2 = ["nap", "teachers", "cheaters", "PAN", "ear", "era", "hectares"];
// alert(aclean(arr)); // "nap,teachers,ear" or "PAN,cheaters,era"

// function aclean(arr) {
//   let map = new Map();

//   for (let word of arr) {
//     // split the word by letters, sort them and join back
//     let sorted = word.toLowerCase().split("").sort().join(""); // (*)
//     map.set(sorted, word);
//   }

//   return Array.from(map.values());
// }

const groupById = (arr) => {
  let ans = arr.reduce((ansObj, user) => {
    let id = user.id;
    ansObj[id] = user;
    return ansObj;
  }, {});
  return ans;
};

let users = [
  { id: "john", name: "John Smith", age: 20 },
  { id: "ann", name: "Ann Smith", age: 24 },
  { id: "pete", name: "Pete Peterson", age: 31 },
];

let usersById = groupById(users);
console.log(usersById);

```

<hr/>

```
let x = 1;

function func() {
  console.log(x); // ?

  let x = 2;
}

func();
```

**Output:**

```
error
```

## Object defineProperty

- With the defineProperty method, we can add new properties to an object, or modify existing ones. When we add a property to an object using the defineProperty method, they are by default not enumerable. The Object.keys method returns all enumerable property names from an object, in this case only "name".

- Properties added using the defineProperty method are immutable by default. You can override this behavior using the writable, configurable and enumerable properties. This way, the defineProperty method gives you a lot more control over the properties you're adding to an object.

```
const person = { name: 'Lydia' };

Object.defineProperty(person, 'age', { value: 21 });

console.log(person);
console.log(Object.keys(person));

//-----> { name: "Lydia", age: 21 }, ["name"]
```

## Infinite curring:

```
function multiply(a){
    return function(b){
    if(!b){
        return a
    }
    else{
        return multiply(a*b)
    }
    }
}

console.log(multiply(5)(6)(10)())
```

## set

```
const config = {
  languages: [],
  set language(lang) {
    return this.languages.push(lang);
  },
};

console.log(config.language);
```

- output is undefined because here the language method is a setter. Setters don't hold an actual value, their purpose is to modify properties.
- When calling a setter method, undefined gets returned.

## argument

```
const myFunc = ({ x, y, z }) => {
  console.log(x, y, z);
};

myFunc(1, 2, 3); // undefined undefined undefined
```

- myFunc expects an object with properties x, y and z as its argument.
- Since we're only passing three separate numeric values (1, 2, 3) instead of one object with properties x, y and z ({x: 1, y: 2, z: 3}), x, y and z have their default value of undefined.

## object destructuring

```
const spookyItems = ['👻', '🎃', '🕸'];
({ item: spookyItems[3] } = { item: '💀' });

console.log(spookyItems);
```

- By destructuring objects, we can unpack values from the right-hand object, and assign the unpacked value to the value of the same property name on the left-hand object. In this case, we're assigning the value "skull" to spookyItems[3].

## Number.isNaN()

- With the Number.isNaN method, you can check if the value you pass is a numeric value and equal to NaN. name is not a numeric value, so Number.isNaN(name) returns false. age is a numeric value, but is not equal to NaN

## flatten Array:

```
let flatArr = [1, [2, 3, [9, [10]], [4, 5, [6, 7]]]];


Method 1:

function flatArr(arr){
	const flattenArr = [];

	for(let val of arr){
	    if (Array.isArray(val)) {
	      acc.push(...flattenArray(val));
	    } else {
	      acc.push(val);
	    }
	}

	return flattenArr;
}


Method 2:
function flattenArray(arr) {
  return arr.reduce((acc, curr) => {
    if (Array.isArray(curr)) {
      acc.push(...flattenArray(curr));
    } else {
      acc.push(curr);
    }
    return acc;
  }, []);
}

let xyz = flattenArray(flatArr);

console.log(xyz);
```

### OR:

```
flatArr.toString().split(",") // but this will gives all values of array as string
```

## Promises:

```
var promise = new Promise(function(resolve, reject) {
    setTimeout(function() {
        resolve('hello world 1');
        resolve('hello world 2');
        resolve('hello world 3');
        resolve('hello world 4');
    }, 1000);
});

promise.then(function success(data) {
    console.log(data);
});
```

**Output:**

```
hello world 1
```

### Given two strings, return true if they are anagrams of one another

- An `“anagram”` of a `“string”` is another character string containing the same characters, only the order of the characters can be different.
- simple approach is split string to array and sort that array and join that array and compare two strings.
- string.split("").sort().join("")

<hr/>

```
var y = 1;
if (function f() {}) {
  y += typeof f;
}
console.log(y);
```

<hr/>

## Palindrome Problem

- take string convert it to lower case and split it apply reverse method and join it and compare it with actual string.

<hr/>

## clousre:

```
function outer() {
  let count = 0;

  function inner() {
    return count++;
  }

  return inner;
}

const closure = outer();

console.log(closure()); // Output?
console.log(closure()); // Output?
console.log(closure()); // Output?

```

<hr/>

**[1,2,3,1,"M",[1,2],[1,2],5,[1,2]]**
- it should return [1,2] because it's count is highest.

```
```

<hr/>
