# Javascript

## 1. What is Ecmascript?

- It is a set of guidlines for browsers vendors to provide functinality to ensure the interoperability of web pages across different browsers.
- latest version of es is es-2022 which 13th edition.
- commonly used is es 6.

## 2. What is Babel?

- Babel is a free and open-source JavaScript transcompiler that is mainly used to convert ECMAScript 2015+(ES-6) code into backwards-compatible JavaScript code that can be run by older JavaScript engines. (If we want to convert new js functinality to old that work was done by babel.)

## 3. What makes JavaScript unique?

There are at least three great things about JavaScript:

- Full integration with HTML/CSS.
- Simple things are done simply.
- Supported by all major browsers and enabled by default.

## 4. Explain Hoisting in javascript.

- Hoisting is the default behaviour of javascript where all the variable and function declarations are moved on top.
- This means that irrespective of where the variables and functions are declared, they are moved on top of the scope. The scope can be both local and global.

Example 1:

```
hoistedVariable = 3;
console.log(hoistedVariable); // outputs 3 even when the variable is declared after it is initialized	
var hoistedVariable;
```

Example 2: 

```
hoistedFunction();  // Outputs " Hello world! " even when the function is declared after calling

function hoistedFunction(){ 
  console.log(" Hello world! ");
} 
```

Example 3:

```
// Hoisting takes place in the local scope as well
function doSomething(){
  x = 33;
  console.log(x);
  var x;
} 
```

**Note - Variable initializations are not hoisted, only variable declarations are hoisted:**

```
var x;
console.log(x); // Outputs "undefined" since the initialization of "x" is not hoisted
x = 23;
```

**Note - To avoid hoisting, you can run javascript in strict mode by using “use strict” on top of the code:**

```
"use strict";
x = 23; // Gives an error since 'x' is not declared
var x;
```


## 4. What is dom(Document Object Model)?

- The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the structure of a document as a tree of objects, where each object corresponds to a part of the document, such as an element, attribute, or text. 

  ![image](/images/Screenshot%20from%202023-03-10%2010-35-10.png)

## 5. where to write js in our html?

- Placing scripts at the bottom of the `<body>` element improves the display speed, because script interpretation slows down the display.

- Inside the <head> section: Scripts placed here are loaded and executed before the <body> content. This is suitable for functions or global variables that need to be available early in the page load.
- Before the closing </body> tag: Placing scripts here allows the HTML content to load and render before the JavaScript executes.

## 6. 4 Ways to Declare a JavaScript Variable:

- Since JavaScript treats a dollar sign as a letter, identifiers containing $ are valid variable names.
- Using var : if we have not intialize with value it will log undefined in console.
- Using let : block scope
- Using const: can not reassign.
- Using nothing: if you dont use any keyword name then it is automatically declare
- Variables created without a declaration keyword (var, let, or const) are always global, even if they are created inside a function.

## 9. var vs let.

- The var and let keywords in JavaScript are both used for declaring variables, but they differ significantly in their scoping rules and hoisting behavior.
  
1. Scoping:
- **var** is function-scoped: A variable declared with var is accessible throughout the entire function in which it is declared
- **let** is block-scoped: A variable declared with let is only accessible within the block (curly braces {}) where it is defined. This includes if statements, for loops, and other block-level constructs.

2. Hoisting:
- **var** variables are hoisted and initialized with undefined: Declarations made with var are "hoisted" to the top of their function scope, meaning you can reference them before their actual declaration in the code. However, they are initialized with undefined until the line of declaration is executed.
- **let** variables are hoisted but not initialized: While let declarations are also hoisted, they are not initialized with a default value. Attempting to access a let variable before its declaration results in a ReferenceError due to the **"Temporal Dead Zone" (TDZ)**.

3. Redeclaration:
- **var** allows redeclaration: You can declare the same variable multiple times within the same scope using var without causing an error.
- **let** prevents redeclaration within the same scope: Attempting to redeclare a let variable within the same block scope will result in a **SyntaxError**.

## 10 JavaScript has 2 Datatypes

- primitive:

1. String
2. Number
3. Bigint
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

- Non primitive:

  The Object Datatype
  The object data type can contain:

1. An object
2. An array
3. A date

![image](/images/datatypes.png)

## 11. Explain Implicit Type Coercion in javascript.

Example 1:

```
var x = 3;
var y = "3";
x + y // Returns "33" 
```

**Note - ‘ + ‘ operator when used to add two numbers, outputs a number. The same ‘ + ‘ operator when used to add two strings, outputs the concatenated string:**

**Note - Type coercion also takes place when using the ‘ - ‘ operator, but the difference while using ‘ - ‘ operator is that, a string is converted to a number and then subtraction takes place.**

```
var x = 3;
Var y = "3";
x - y    //Returns 0 since the variable y (string type) is converted to a number type
```

## What is the difference between undefined value and null value?

- Null in JavaScript means an empty value and is also a primitive type in JavaScript. The variable which has been assigned as null contains no value.Undefined, on the other hand, means the variable has been declared, but its value has not been assigned.

## JavaScript Operators:

- `**` : `Exponentiation`

  ![image](/images/operators.png)

- typeof: Returns the type of a variable.
- instanceof: Returns true if an object is an instance of an object type.

## The Nullish Coalescing Operator (`??`):

- The nullish coalescing operator is written as two question marks `??`.
- As it treats null and undefined similarly, we’ll use a special term here, in this article. For brevity, we’ll say that a value is “defined” when it’s neither null nor undefined.

```
The result of a ?? b is:

if a is defined, then a,
if a isn’t defined, then b.
```

```
|| returns the first truthy value.
?? returns the first defined value.
```

## The Optional Chaining Operator (?.):

- The ?. operator returns undefined if an object is undefined or null (instead of throwing an error).
- In other words, value?.prop:

- works as value.prop, if value exists,
- otherwise (when value is undefined/null) it returns undefined.

- The optional chaining ?. syntax has three forms:

- `obj?.prop `– returns obj.prop if obj exists, otherwise undefined.
- `obj?.[prop]` – returns obj[prop] if obj exists, otherwise undefined.
- `obj.method?.() `– calls obj.method() if obj.method exists, otherwise returns undefined.

## The typeof Operator:

![image](/images/typeof.png)

## Boolean function:

- `Boolean('')` : gives false.
- `Boolean('dasd')` : gives true.

  ![image](/images/boolean.png)

## truthy values & falsy values using `!!`:

- The following values are considered falsy in JavaScript:
  - false
  - 0 (the number zero)
  - -0 (negative zero)
  - 0n (BigInt zero)
  - "", '', `` `` (empty strings)
  - null
  - undefined
  - NaN (Not-a-Number)

- All other values are considered truthy. This includes:
  - Non-zero numbers (e.g., 1, -5, 3.14)
  - Non-empty strings (e.g., "hello", "false", "0")
  - Objects (including empty objects {} and arrays [])
  - Functions
  - true itself

## Ternary statement `? :` :

## Switch statement:

- In switch, the cases will use the `===` for comparision not `==`.
- Switch cases use strict comparison (===).

## Numbers:

- Numbers come in the blue colour and string in black colour.

## JavaScript Integer Accuracy:

- JavaScript integers are only accurate up to 15 digits.

## BigInt:

- To create a BigInt, append n to the end of an integer or call BigInt()
- `let y = BigInt(1234567890123456789012345)`
- `let y = 9999999999999999n;`
- `The JavaScript typeof a BigInt is "bigint".`
- let x = 5n;
- let y = x / 2;
- // Error: Cannot mix BigInt and other types, use explicit conversion.
- let x = 5n;
- let y = Number(x) / 2;

## isNaN() function:

- NaN property represents the “Not-a-Number” value. It indicates a value that is not a legal number.
- typeof of NaN will return a Number.

- isNaN() to find out if a value is a not a number.
- `NaN is a number: typeof NaN returns number`.
- `Infinity is a number: typeof Infinity returns number.`
- isNaN("2") => false
- isNaN("a") => true
- isNaN(a) => error

- But do we need this function? Can’t we just use the comparison === NaN? Unfortunately not.
- The value NaN is unique in that it does not equal anything, including itself:

```
alert( NaN === NaN ); // false
```

## Number Methods:

![image](/images/numbermethods.png)

## toFixed() method :

- used for round off the float value.
- `99.5210.toFixed()` : gives 100
- `99.5210.toFixed(2)` : gives 99.52

## Comparision:

- `==`, `===`, and `object.is(value1, value2)`.
- `==` : if the right side is string then it will convert the left side value into to string and then compare. and if the right side value is numeric then it will apply valueOf method on the left side value and then compare
- There is a special built-in method Object.is that compares values like ===, but is more reliable for two edge cases:
- It works with NaN: Object.is(NaN, NaN) === true, that’s a good thing.
- Values 0 and -0 are different: Object.is(0, -0) === false, technically that’s correct, because internally the number has a sign bit that may be different even if all other bits are zeroes.

## Comparing strings

- As we know from the chapter Comparisons, strings are compared character-by-character in alphabetical order.
- A lowercase letter is always greater than the uppercase:  

## Number Methods:

- Basic number methods can be used on any number:

- toString() : The toString() method returns a number as a string.
- toExponential() : toExponential() returns a string, with a number rounded and written using exponential notation.
- toFixed() : toFixed() returns a string, with the number written with a specified number of decimals:
- toPrecision() : toPrecision() returns a string, with a number written with a specified length:
- valueOf() : valueOf() returns a number as a number

## Strings & Template Literals:

- ways: ` `` `(backticks) , " " , ' '.

- Template Literals use back-ticks (``) rather than the quotes ("") to define a string:
- The \ method is not the preferred method. It might not have universal support.
- Some browsers do not allow spaces behind the \ character.
- strings are immutable cannot be changed.

  ![image](/images/strings.png)

## String with const:

![image](/images/immutablestrings.png)

## String Methods:

- **Javascript strings are primitive and immutable: All string methods produce a new string without altering the original string.**

- There are 3 methods for extracting a part of a string:

- slice(start, end)
- substring(start, end)
- substr(start, length)

## slice()

- slice() extracts a part of a string and returns the extracted part in a new string.
- The method takes 2 parameters: start position, and end position (end not included).

## substring():

- substring() is similar to slice().
- The difference is that start and end values less than 0 are treated as 0 in substring()

## substr()

- substr() is similar to slice().
- The difference is that the second parameter specifies the length of the extracted part.

![image](/images/stringsmethods.png)

## trim():

- It will trim the whitespace string from begin and end.

![image](/images/trim.png)

## padStart()

- The padStart() method pads a string from the start.
- It pads a string with another string (multiple times) until it reaches a given length.

```
Pad a string with "0" until it reaches the length 4:

let text = "5";
let padded = text.padStart(4,"0");
```

## repeat():
- The repeat() method returns a string with a number of copies of a string.
- The repeat() method returns a new string.
- The repeat() method does not change the original string.

```
string.repeat(count)
```

## Extracting String Characters:

- There are 3 methods for extracting string characters:

- charAt(position)
- charCodeAt(position)
- Property access [ ] : ECMAScript 5 (2009) allows property access [ ] on strings.
- It makes strings look like arrays (but they are not).
- If no character is found, [ ] returns undefined, while charAt() returns an empty string.
- It is read only. str[0] = "A" gives no error (but does not work!)

## Converting a String to an Array:

- A string can be converted to an array with the `split()` method.

## JavaScript String Search:

- String indexOf()
- String lastIndexOf()
- String search()
- String match()
- String matchAll()
- String includes() : The includes() method returns true if a string contains a specified value.it is case sensitive.
- String startsWith()
- String endsWith()

## index vs search.

- The search() method cannot take a second start position argument.
- The indexOf() method cannot take powerful search values (regular expressions).

### match():

- The match() method returns(will return only the first match in the string) an array containing the results of matching a string against a string (or a regular expression).

### matchAll()

- The matchAll() method returns an iterator containing the results of matching a string against a string (or a regular expression).
- matchAll() does not work in Internet Explorer.

### global search :

- `/aim/g` : Perform a global search for aim.
- `/aim/gi` : Perform a global, case-insensitive search for "aim"

### Interpolation

- Template literals provide an easy way to interpolate variables and expressions into strings.
- means if we have one variable that has value if we want to add it to our string we use `string ${variable_name}` for concatinating our variable with string.
- let firstName = "John";
- let lastName = "Doe";
- let text = `Welcome ${firstName}, ${lastName}!`;

## JavaScript Array Methods

- at():	Returns an indexed element of an array
- concat():	Joins arrays and returns an array with the joined arrays
- constructor : Returns the function that created the Array prototype
- copyWithin():	Copies array elements within the array, to and from specified positions
- entries():	Returns a key/value pair Array Iteration Object
- every():	Checks if every element in an array pass a test

```
// Create an Array
const ages = [32, 33, 16, 40];

// Create a Test Function
function checkAge(age) {
  return age > 18;
}

// Are all ages over 18?
ages.every(checkAge);
```

- fill():	Fill the elements in an array with a static value

- The fill() method fills specified elements in an array with a value.
- The fill() method overwrites the original array.
- Start and end position can be specified. If not, all elements will be filled.

```
Syntax
array.fill(value, start, end)
```

- **filter()**:	Creates a new array with every element in an array that pass a test
- find():	Returns the value of the first element in an array that pass a test
- findIndex():	Returns the index of the first element in an array that pass a test
- findLast():	Returns the value of the last element in an array that pass a test
- findLastIndex():	Returns the index of the last element in an array that pass a test
- **flat()**:	Concatenates sub-array elements
- flatMap():	Maps all array elements and creates a new flat array

```
const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap(x => [x, x * 10]);

Output: 1,10,2,20,3,30 ...
```

- forEach():	Calls a function for each array element
- from():	Creates an array from an object

```
let text = "ABCDEFG";
Array.from(text);

Ans: A,B,C,D,E,F,G
```
- includes():	Check if an array contains the specified element

```
Syntax
array.includes(element, start)
```

- indexOf():	Search the array for an element and returns its position
- isArray():	Checks whether an object is an array
- **join()**:	Joins all elements of an array into a string
- **keys()**:	Returns a Array Iteration Object, containing the keys of the original array
- lastIndexOf():	Search the array for an element, starting at the end, and returns its position
- length:	Sets or returns the number of elements in an array
- map():	Creates a new array with the result of calling a function for each array element
- of():	Creates an array from a number of arguments

```
let fruits = Array.of("Banana", "Orange", "Apple", "Mango");
Ans: [ "Banana", "Orange", "Apple", "Mango" ]
```

- **pop():**	Removes the last element of an array, and returns that element
- **push():**	Adds new elements to the end of an array, and returns the new length

- reduce():	Reduce the values of an array to a single value (going left-to-right)

```
const numbers = [175, 50, 25];

document.getElementById("demo").innerHTML = numbers.reduce(myFunc);

function myFunc(total, num) {
  return total - num;
}
```
- reduceRight():	Reduce the values of an array to a single value (going right-to-left)

- reverse():	Reverses the order of the elements in an array, The reverse() method overwrites the original array.

- **shift()**:	Removes the first element of an array, and returns that element
- **unshift()**:	Adds new elements to the beginning of an array, and returns the new length

- slice():	Selects a part of an array, and returns the new array
- some():	Checks if any of the elements in an array pass a test
- sort():	Sorts the elements of an array

- splice():	Adds or Removes array elements

- toReversed():	Reverses the order of array elements (to a new array)
- toSorted():	Sorts the elements of an array (to a new array)
- toSpliced():	Adds or Removes array elements (to a new array)

- toString():	Converts an array to a string, and returns the result
- valueOf():	Returns the primitive value of an array

- with():	Returns a new array with updated elements
- The with() method updates a specified array element.
- The with() method returns a new array.

```
array.with(index, value)


const months = ["Januar", "Februar", "Mar", "April"];
const myMonths = months.with(2, "March");

Ans: Mar -> march
```

## Functions:

- https://www.w3schools.com/js/js_function_definition.asp

- Topics:
  - The Function() Constructor
  - Function Hoisting
  - Self-Invoking Functions
  - Function Expressions

### Functions are Objects

- The typeof operator in JavaScript returns "function" for functions.

- The toString() method returns the function as a string:

### Arrow Functions

Arrow functions allows a short syntax for writing function expressions.

Arrow functions have no “this”

You don't need the function keyword, the return keyword, and the curly brackets.

You can only omit the return keyword and the curly brackets if the function is a single statement.

Arrow functions are special: they don’t have their “own” this. If we reference this from such a function, it’s taken from the outer “normal” function. means it will access property from the global object.

Arrow functions are not hoisted. They must be defined before they are used.

Using const is safer than using var, because a function expression is always constant value.

## Normal Function Vs Arrow Functions:

- First main diff. is `Syntax`. we can write an arrow function in fewer lines. we don't need the function keyword. we can only omit the return keyword and the curly brackets if the function is a single statement.

- Second Main difference between is `this` keywords. In regular functions `this` value is dynamic means if we have a method in any object then the value of `this` referes to particular object where in arrow function `this` not refers to particular object. show below example carefully.

```
let me = {
 name: "Ashutosh Verma",
 thisInArrow:() => {
 console.log("My name is " + this.name); // no 'this' binding here
 },
 thisInRegular(){
 console.log("My name is " + this.name); // 'this' binding works here
 }
};
me.thisInArrow();
me.thisInRegular();
```

**Output:**

![image](https://user-images.githubusercontent.com/125242584/229422068-a0f82dd7-5f55-4ce4-8697-138cc246486a.png)

## Function Parameters Vs arguments:

Function parameters are the names listed in the function definition.

Function arguments are the real values passed to (and received by) the function.when we are calling it.

https://www.w3schools.com/js/js_function_parameters.asp

### Rest parameters & The Arguments Object:

The rest parameter `(...)` allows a function to treat an indefinite number of arguments as an array. means if we have to pass argument more than one we can use function myFun(...params(give any name)).

Before this in es 5 uses the argument parameter for accessing all argument as a parameter.

![image](/images/rest.png)

## Immediately-Invoked Function Expressions (IIFE):

- An IIFE (Immediately Invoked Function Expression) is a function that runs the moment it is invoked or called in the JavaScript event loop.

```
 // Regular Function.
    function Greet() {
        console.log("Welcome to GFG!");
    };
    // Execution of Regular Function.
    Greet();

    // IIFE creation and execution.
    (function() {
        console.log("Welcome to GFG!");
    })();
```

- here when we call the second time the counter will reset to 0 and again increase 1 but the function will call 3 times.to avoid this type of error we use clousre in which we use IIFE.

![image](/images/withoutClousre.png)

- with clousre:

![image](/images/clousoure.png)

## what is function statement?

- when we written function normally it is called function statement.

```
function a(){
console.log("a called");
}
```

## what is function expression?

- when we assign any function to variable it is called expression.

```
var b = function (){
console.log("b called");
}
```

## Difference between them:

- major diff is hoisting. when we called both a(); and b(); before defining a will return `a called` and for b it is showing `error` because the b is var and it is undefine so it is not callable.

## Anonymous function:

- function with no name is called anonymous function.
- we used this when it will used as values.

## Named function Expression:

```
var b = function `xyz`(){
console.log("b called");
}
```

## First class function: functions are first class citizen

- The ability to pass a function as argument to another function or return a function to another function. or ability to used function as variable.

</hr>

## Function Clousre:

- It return a function with its lexical environment means we get functions bind with its lexical scope where all variables are accessible by its reference.

```
function init() {
var name = 'Mozilla'; // name is a local variable created by init
function displayName() {
// displayName() is the inner function, a closure
console.log(name); // use variable declared in the parent function
}
name = "Harry"
return displayName;
}
let c = init();
c()
```

**Output:**

```
Harry
```

## `this` keyword:

It is a keyword which reference to a variable of current object.

### Global Object

When a function is called without an owner object, the value of this becomes the global object.

In a web browser the global object is the browser window.

## Call, Apply and Bind Methods:

- When used?

- for example we have object which has two keys fname and lname and third key has `function` as a value and in that function i have access the object's value using `this` keyword.

- and we have another object which has diff fname and lname value and we have same function that has in first object so insted of writing the function again in second object we will simply define function explictly and we can use `.call` method and passing the object.

`call` : It is called function borrowing.we can pass extra argument by providing comas.

- For ex:

```
let obj1 = {
  firstname: "Gunjan",
  lastname: "Dalwadi",
  printFullName: function () {
    console.log(this.firstname + " " + this.lastname);
  },
};
name.printFullName();

let obj2 = {
  firstname: "Sachin",
  lastname: "Tendulkar",
};
// function borrowing
name.printFullName.call(name2);
```

- Insted of above you can write below using call.

```
let obj1 = {
  firstname: "Gunjan",
  lastname: "Dalwadi",
};

let obj2 = {
  firstname: "G",
  lastname: "D",
};

function xyz() {
  console.log(this.firstname + " " + this.lastname);
}

xyz.call(obj1);
xyz.call(obj2);

```

`apply` : Same but after writing objectname, if suppose function have extra argument then we can use `[ ]`.

```
obj1{}
obj2{}
function(param1,param2){}
function.call(obj1,param1,param2)
function.apply(obj1,[param1,param2])
```

- **we can use any of them, but apply will probably be faster, because most JavaScript engines internally optimize it better.**
- **Passing all arguments along with the context to another function is called call forwarding.**

`bind` : It is bind/append particular function with object. and creating the copy of the function. so when we directly log that we get the whole function. so we have to call it explicitaly.

**Example:**

```
function f() {
  alert(this.name);
}
f = f.bind( {name: "John"} ).bind( {name: "Ann" } );
f(); // return john because A function cannot be re-bound.

```

```
function sayHi() {
  alert( this.name );
}
sayHi.test = 5;

let bound = sayHi.bind({
  name: "John"
});

alert( bound.test ); // what will be the output? why?
```

- The answer: undefined.
- The result of bind is another object. It does not have the test property.

![image](/images/callapply.png)

## Object:

- It is collection of element with key-value pairs.
- Generally, the js engine will take the key and value as a string in backend. so we can define any of the way either string format using quotes or any general way.

- Booleans can be objects (if defined with the new keyword)
- Numbers can be objects (if defined with the new keyword)
- Strings can be objects (if defined with the new keyword)
- Dates are always objects
- Maths are always objects
- Regular expressions are always objects
- Arrays are always objects
- Functions are always objects
- Objects are always objects
- `All JavaScript values, except primitives, are objects`.
- Objects are associative arrays with several special features.
- **They store properties (key-value pairs), where:**
- Property keys must be strings or symbols (usually strings).
- Values can be of any type.

- **By default, a plain object has following toString and valueOf methods:**

- The **toString** method returns a string "[object Object]".
- The **valueOf** method returns the object itself.

- **All objects have prototypes, except for the base object. The base object is the object created by the user, or an object that is created using the new keyword. The base object has access to some methods and properties, such as .toString. This is the reason why you can use built-in JavaScript methods! All of such methods are available on the prototype. Although JavaScript can't find it directly on your object, it goes down the prototype chain and finds it there, which makes it accessible for you.**

##### Additional operators:

- To delete a property: delete obj.prop.
- To check if a property with the given key exists: "key" in obj.
- To iterate over an object: for (let key in obj) loop.

##### There are many other kinds of objects in JavaScript:

- Array to store ordered data collections,
- Date to store the information about the date and time,
- Error to store the information about an error.

![image](/images/keywithspace.png)

![image](/images/keywithspacewithnoerror.png)

## Creating the object:

- There are different ways to create new objects:

### using an object literal.

```

const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

```

### with the keyword new.

```

const person = new Object();
person.firstName = "John";
person.lastName = "Doe";
person.age = 50;
person.eyeColor = "blue";

```

- Define an object constructor, and then create objects of the constructed type.
- Create an object using `Object.create()`.
- Objects are Mutable
- The delete keyword deletes a property from an object

## Computed properties

- We can use square brackets in an object literal, when creating an object. That’s called computed properties.

## Property names limitations

```

let obj = {
0: "test" // same as "0": "test"
};

// both alerts access the same property (the number 0 is converted to string "0")
alert( obj["0"] ); // test
alert( obj[0] ); // test (same property)

```

- A notable feature of objects in JavaScript, compared to many other languages, is that it’s possible to access any property. There will be no error if the property doesn’t exist!
- Reading a non-existing property just returns undefined. So we can easily test whether the property exists:

## The "for..in" loop

- To walk over all keys of an object, there exists a special form of the loop: for..in

## Are objects ordered? In other words, if we loop over an object, do we get all properties in the same order they were added? Can we rely on this?

- The short answer is: “ordered in a special fashion”: integer properties are sorted, others appear in creation order.

## Property flags

- Object properties, besides a value, have three special attributes (so-called “flags”):

- `writable` – if true, the value can be changed, otherwise it’s read-only.
- `enumerable` – if true, then listed in loops, otherwise not listed.
- `configurable` – if true, the property can be deleted and these attributes can be modified, otherwise not.

`Object.preventExtensions(obj)`

- Forbids the addition of new properties to the object.

`Object.seal(obj)`

- Forbids adding/removing of properties. but allow for changing. Sets configurable: false for all existing properties.

`Object.freeze(obj)`

- Forbids adding/removing/changing of properties. Sets configurable: false, writable: false for all existing properties.

`Object.isExtensible(obj)`

- Returns false if adding properties is forbidden, otherwise true.

`Object.isSealed(obj)`

- Returns true if adding/removing properties is forbidden, and all existing properties have configurable: false.

## Frozen Object: `IMP`

- You can make immutable object using the function `Object.freeze(obj)`. The object passed to the freeze method will become immutable. so we cannot overwrite the value to it's parameter.

```

let obj = {
    a:21,
    b:"test"
} 
obj2 = obj 
obj2.b = "test21"

```

- this will change the value of obj.b and to avoid this we can use `Object.freeze(obj_name)` so this will make object mutable.

## Garbage Collector:

- There’s a background process in the JavaScript engine that is called garbage collector.
- It monitors all objects and removes those that have become unreachable.

**Example:**

```

// user has a reference to the object
let user = {
name: "John"
};

```

- If the value of user is overwritten, the reference is lost:

```

user = null;

```

- Now John becomes unreachable. There’s no way to access it, no references to it. Garbage collector will junk the data and free the memory.```

- **The basic garbage collection algorithm is called “mark-and-sweep”.**
- **the garbage collector tries to run only while the CPU is idle, to reduce the possible effect on the execution.**
- **Garbage collection is performed automatically. We cannot force or prevent it.**

- Functions that are stored in object properties are called “methods”.
- Methods allow objects to “act” like object.doSomething().
- Methods can reference the object as this.

## Object Comparison by reference:

let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true

### Accessing the object values:

![image](/images/accessingobjectvalues.png)

<hr/>

- if we want to make key and value_variable as same name so we can define by this:

![image](/images/keyvalsame.png)

### Object destructring:

- For finding remaining element of the object we use `...rest` keyword in our destructure object.

![image](/images/destructimhg.png)

## Object.keys, values, entries:

- Object.keys(obj) – returns an array of keys.
- Object.values(obj) – returns an array of values.
- Object.entries(obj) – returns an array of [key, value] pairs.
- `Object.entries(user) = [ ["name","John"], ["age",30] ]`
- Use **Object.fromEntries(array)** on the resulting array to turn it back into an object.

## Types of clone the object:

```

const a = {
  name:"gunjan",
  tech:{
    front:"react",
    aaaa:{
      bbb:"abc"
    }
  }
}

const b = Object.assign({},a); // copy one level means if we change first level it will not copy
const b = {...a} // copy one level means if we change first level it will not copy
const b = JSON.parse(JSON.stringify(a)) // copy deeply and it will not
const b = structuredClone(a); // copy deeply and it will not

b.name = "dasj"
b.tech.front = "html"
b.tech.aaaa.bbb = "html"
console.log("b",b)
console.log("a",a)

```

### Property and Value Existence Checking:

- we check whether the values are stay in object or not by using below:

![image](/images/checking.png)

## Converting objects into array:

- Any JavaScript object can be converted to an array using Object.values(object_name).

## Converting objects into strings:

- Any JavaScript object can be converted to a string with the JavaScript function `JSON.stringify(object_name)`. but we have to assign this to variable so that variable's type is string.

### Stringify Arrays:

- Any JavaScript array can be converted to a string with the JavaScript function `JSON.stringify(array_name)`:

## JavaScript Arrays:

- Type of array is `object`. arrays are mutable changeable.

## flat methods OR flatten array into one dimention from 2d or 3d.

- let a = [[1],[2,3],4,5,6] convert to [1,2,3,4,5,6]
- for that we use a.flat() will flatten array up to one level means one dimentions.
- for further flatten we pass .flat(2 or 3) 2 or 3 levels.

## join or concat two array using spread opearator or withour using `concat`:

```

// merging array with concat
let alltoppings = toppings.concat(newtoppings);
console.log(alltoppings);

// merging array using spread opearator
let alltoppings1 = [...toppings, ...newtoppings]
console.log(alltoppings1);

```

## new Array()

- it will take the length of array as argument so we want to create array with no elements and specific length then we can use this.

### Arrays methods:

1. tostring() method:

- converts array to string. `arr_name.tostring();`

2. join():

- it will seperate elements with given operator. `arr_name.join("*")`
- type of this is string.

3. pop():

- It will remove last element. it will change the original array.
- `arr.pop()` it will return poped element.

4. push():

- It will add new element in array at last position. it will change the original array.
- `arr.push(element)` it will return length of array.

5. shift():

- it will remove fist element and modified original array.
- `arr.shift()` return first element.

6. unshift():

- it will add fist element and modified original array.
- `arr.unshift(element)` return length of new array.

7. delete (it is operator):

- delete array element by giving position. but the array length is remain same its length is not decreasing.
- `delete arr[position]`

8. concat:

- it will concat the two array. not change existing array.
- `newarray = arr1.concat(arr2,arr3,arr4,arr5)`

9. sort:

- it will sort the array and changed the original array.
- it will sort array alphabetically. means it will take element as an strings.
- `arr.sort()`

### How to sort numeric array?

- create compare function given below:

```

function compare = (a,b) =>{ return a-b; }
(a-b: for ascending & b-a for decending order)
then arr.sort(comapre).

```

10. reverse:

- it will reverse the array.

11. splice:

- syntax: .splice(start_position, howmany_elements to remove from position you have given , list of elements)
- returns deleted values and modified original array.

12. slice:

- syntax: slice(start-position,end-pos_but-not-included)
- it will not modified original array.
- returns sliced array .

13. find:

- it will return first value that has pass the condition given in fucntion.
- arr.find(function_name or define function)

14. findIndex:

- it will return the index of first element that pass the condition given in fucntion.
- arr.findIndex(function_name or define function)

15. some():

- It will return the true or false value for array that's some value pass conditions or not.

16. every():

- It will return the true or false value for array that's all value pass conditions or not.

## looping in array:

1. forEach():

- synatx: arr.forEach((ele)=>{ console.log(ele \* ele) }) // print the square of array element

2. Array.from() method:

- used to create an array from object.
- also create an array from string.
- `Array.from(string_name);`
- ex:
  let str = "Gunjan"; </br>
  console.log(Array.from(str));

  output:
  ['G', 'u', 'n', 'j', 'a', 'n']

3. for.....of:

- return list of array elements.
- syntax: `for(let item of arr){ console.log(item) }`

4. for.....in:

- return list of array element's position or index.
- syntax: `for(let i of arr){ console.log(i) }` //return the indexes
- syntax: `for(let i of arr){ console.log(arr[i]) }` //return the elements

## map filter and reduce:(Higher order array methods)

### 1. Map vs forEach:

- syntax : `.map(value, index, array)`
- `map` is create the new array (by return the values and it is a function) where `forEach` will perform some operation on existing array(it is basically a loop).
- example of map:

  ![image](/images/arraymap.png)

### WeakMap

- The first difference between Map and WeakMap is that keys must be objects, not primitive values:

### 2. filter:

- this will apply on array for each item the condition become true that item it will return and create a new array.
- newarray = arr.filter((num)=>{ </br>
  return num<20 ; </br>
  })

- this will not changed our original array.

### 3. reduce:

- it will return the single value not an array.
- syntax: arr.reduce(function_name or function)

  ![image](/images/reduce.png) </br>

- this will return 14 only.
- The reduceRight() works from right-to-left in the array. The reduceRight() method does not reduce the original array.

```
[1, 2, 3, 4].reduce((x, y) => console.log(x, y));
```

- The first argument that the reduce method receives is the accumulator, x in this case. The second argument is the current value, y. With the reduce method, we execute a callback function on every element in the array, which could ultimately result in one single value.
- In this example, we are not returning any values, we are simply logging the values of the accumulator and the current value.
- The value of the accumulator is equal to the previously returned value of the callback function. If you don't pass the optional initialValue argument to the reduce method, the accumulator is equal to the first element on the first call.

# DOM Manipulation:

## Adding elements using js:

1. .append() method.

- const body = document.body
- body.append("Hi");

2. creating html elements.

- const div = document.createElement("div");
- body.append(div);
- div.innerText = "hello";

### Diff between innerText and textContent

- when we log innerText it will print in one line where the textContent will print same as it is define in our html file with all indentation.

3. innerHTML:

- `div.innerHTML = "<b>Welcome</b>";`

4. remove html element:

- const bold = document.querySelector("b");
- bold.remove();

5. getattribute and setAttribute:

- console.log(bold1.getAttribute("title"));
- console.log(bold1.setAttribute("title", "Italic text"));
- console.log(bold1.title);

6. class:

- `bold1.classList.add("b3");` // add class to existing element
- `bold1.classList.remove("b1");` // remove class to existing element
- `bold1.classList.toggle("b2");` // remove class if that name exists otherwise add it
- `bold1.classList.toggle("b3", true);` // it will add class and if false it will remove it

7. customize css property:

- bold1.style.backgroundColour = "value";

8. queryselectorAll():

- If you want to find all HTML elements that match a specified CSS selector (id, class names, types, attributes, values of attributes, etc), use the querySelectorAll() method.
- This example returns a list of all `<p>` elements with class="intro".

- Example:
- const x = document.querySelectorAll("p.intro");

## Difference Between textContents, innerText, and innerHtml?

- `textContents` is all text contained by an element and all its children that are for formatting purposes only.
- `innerText` returns all text contained by an element and all its child elements.
- `innerHtml` returns all text, including html tags, that is contained by an element.

## DOM:

![image](/images/dom.png) </br>

## Date:

- JavaScript counts months from 0 to 11:

```

January = 0.
December = 11.

```

## Math Object:

https://www.w3schools.com/js/js_math.asp

## typeof keyword:

- typeof array, object, null, regExp are `object`.
- typeof string is string.
- typeof number,NaN are number.
- typeof undefine is undefine.

## Type Conversion / Type Casting:

- Implicit : It will autometically converts to other type. like '1' + 3 ans is 13 as string
- Explicit type casting/conversion: String(value) or .toString(), Number(value), Boolean(value) function

### Converting Strings to Numbers:

- `Number(value)`.
- A numeric string (like "3.14") converts to a number (like 3.14).
- An empty string (like "") converts to 0.
- A non numeric string (like "John") converts to NaN (Not a Number).

### Converting Numbers to Strings:

- String(here) or number.toString()

## Type coercion

- Type coercion is the automatic or implicit conversion of values from one data type to another
- one key difference — type coercion is implicit whereas type conversion can be either implicit or explicit.

## Declaring Strict Mode

- Strict mode is declared by adding "use strict"; to the beginning of a script or a function.

## JavaScript Modules:

- JavaScript modules allow you to break up your code into separate files.
- This makes it easier to maintain a code-base.
- Modules are imported from external files with the import statement.
- As modules support special keywords and features, we must tell the browser that a script should be treated as a module, by using the attribute `<script type="module">`
- In a module, “this” is undefined.

## Core module features

- Always `“use strict”` : Modules always work in strict mode. E.g. assigning to an undeclared variable will give an error.

## Import:

**1. `Import *`**

- Usually, we put a list of what to import in curly braces import {...}, like this:
- But if there’s a lot to import, we can import everything as an object using import \* as <obj>, for instance:

```
import * as say from './say.js';

say.sayHi('John');
say.sayBye('John');
```

**2. Import “as”**

- We can also use as to import under different names.
- For instance, let’s import sayHi into the local variable hi for brevity, and import sayBye as bye:

```
import {sayHi as hi, sayBye as bye} from './say.js';
```

**Export “as”**

- The similar syntax exists for export.
- Let’s export functions as hi and bye:

## Export:

- There are two types of exports: Named Exports and Default Exports.

**Named export** :
export class User {...} export default class User {...}
**Default export**
import {User} from ... import User from ...

- **Please note that import/export statements don’t work if inside {...}**

## How JavaScript Code is executed?

- First it will create the global execution context which has two components:

1. memory compo.
2. code component.

- Then it will start executing code line by line and giving the varable value as undefined first and for function it will put whole function code.

- Then after it will again go through line by line and assign value to variable and for `function call` it will again create execution context with memory and code compo.

- for managing this js contain the `callstack` where all execution context are pushed and after executed they will popout from stack.

- `Shortest program in js is no code in js file.`

## Block Scope and Shadowing:

1. Block:

- it is a compound statement. it used for combine multiple js statement into group so js expect/understand the single statement.

2. Block scope:

- The variables or functions are accessible to particular block only.
- `var` is accessible outside the block.
- scope for normal functions and arrow functions are same.

3. Shadowing:

- If we have one variable outside block and same named var inside the block with different value so the in block when we log it will shadowed to outside block & print the inside block's value.
- but it depends on var, let or const when we access it outside and inside.

4. Illegal shadowing:

- ex :

```

let a = 10;
{
var a = 100;
}

```

- this will throw an error named a already declare.

- if we used function here so it will not throw error because it is

- so when we do shadowing that second variable cannot be accessible outside of its scope.if we used let it will not throw error.

5. lexical scoping:

- it means one scope inside another scope.

## Closures:

- function along with it's lexical scope forms a closures.

![image](/images/closures.png)

- in this the y will maintain their lexical scope or connection with its parent functions or scopes. means by this it will not store their value in garbage but yes it will store the reference of particular variable not that value.

![image](/images/function%20closures.png)

# Asynchronous Javascript:

## setTimeout:

- It is used when we have to execute our js after some time that we have given.
- The setTimeout() is executed only once.
- syntax:

```

myTimeout = setTimeout(function, milliseconds);

```

Then you can to stop the execution by calling clearTimeout():

```

clearTimeout(myTimeout);

```

- This function will return the id with a number type.

## setInterval:

- It is used when we have to execute our javascript continuosly with some time interval.
- The setInterval() method continues calling the function until clearInterval() is called, or the window is closed.

```

myInterval = setInterval(function, milliseconds);
Then you can to stop the execution by calling clearInterval():
clearInterval(myInterval);

```

- **Nested setTimeout allows to set the delay between the executions more precisely than setInterval.**

## Callbacks:

- it is a functions that is sent as an input to another functions or return particular function in one function.
- plays a main role in writing code in asynchronous javascript
- callbacks functions are the functions that sometimes else called.
- examples:

```

setTimeout(function () {
console.log(x);
}, x \* 1000);

```

- here the function is called callbacks functions.means it will call after sometime.
- there are two issues that are in callbacks: 1. callback hell 2. inversion of control

## Callback Hell:

- when we are using callbacks for our async javascript then it will become large nested callback and this is called callback hell.In this our code will increase horizontally not vertically.

```

// Callback hell
createOrder(cart, function (orderId) {
proceedToPayment(orderId, function (paymentInfp) {
showOrderSummary(paymentInfp, function () {
updateWalletBalance();
});
});
});

```

## Inversion of control:

- means we are giving our function's control in some other api so it will be risky if API has not calling our function or it call our function many time so this are issues are occur when we use callbacks in our async js.

## Promises:

- A promise is a special JavaScript object that links the “producing code” and the “consuming code” together. In terms of our analogy: this is the “subscription list”. The “producing code” takes whatever time it needs to produce the promised result, and the “promise” makes that result available to all of the subscribed code when it’s ready.

- Promise handlers .then/.catch/.finally are always asynchronous.
- Even when a Promise is immediately resolved, the code on the lines below .then/.catch/.finally will still execute before these handlers.

- The constructor syntax for a promise object is:

```
let promise = Promise.resolve();
promise.then(() => alert("promise done!"));
alert("code finished"); // this alert shows first
```

```
let promise = new Promise(function(resolve, reject) {
// executor (the producing code, "singer")
});
```

- The function passed to new Promise is called the executor. When new Promise is created, the executor runs automatically.
- Its arguments resolve and reject are callbacks provided by JavaScript itself. Our code is only inside the executor.
- The promise object returned by the new Promise constructor has these internal properties:

- `state` — initially "pending", then changes to either "fulfilled" when resolve is called or "rejected" when reject is called.
- `result` — initially undefined, then changes to value when resolve(value) is called or error when reject(error) is called.

- A promise that is either resolved or rejected is called “settled”, as opposed to an initially “pending” promise.
- An “unhandled rejection” occurs when a promise error is not handled at the end of the microtask queue.

</hr>

## 1. Consuming Promises:

- A promise is an object representing eventual completion or failer of asynchronous operation.

```
const promise = createOrder(cart);
```

- when the Js engine execute this line initially promise contain the empty object and then that api is going to running state. till then js engine will execute the rest of the code.
- when the api gets executed then it will add data to object.
- now promise object contain two property:

### 1. promise state:

- three states: pending, fullfilled, and rejected.

### 2. promise result:

- it stores promise resultant data.
- now after promise object get data we will attach our callbacks with our promise using `.then(callback_function)` function.
- `fetch()` function is used for fetching the external content and it will return a promise object.
- promise object are immutable.

## Promise chaining:

- callback hell issue was solved using promise chaining.
- it is compalsary to return all function which are add in promise chaining.

```

// Callback hell
createOrder(cart, function (orderId) {
  proceedToPayment(orderId, function (paymentInfp) {
    showOrderSummary(paymentInfp, function () {
      updateWalletBalance();
    });
  });
});

// which written as promise chaining
createOrder(cart)
.then(function (orderId) {
return proceedToPayment(orderId);
})
.then(function (paymentInfo) {
return showOrderSummary(paymentInfo);
})
.then(function (paymentInfo) {
return updateWalletBalance(paymentInfo);
});

```

## 2. Creating Promises:

- const promise = `new Promise(function (resolve, reject){ ... content ... })`
- In promises when the promise get resolved or fullfilled it will catch by function callback using .then but if any error occur then we have to show that to user so for that we use `.catch()` method for showing our error.

```

promise
.then(function (orderId) {
console.log(orderId);
})
.catch(function (err) {
alert(err.message);
});

```

- we also catch particular callback function's error also.

## Summary:

- Promise handling is always asynchronous, as all promise actions pass through the internal “promise jobs” queue, also called “microtask queue” (V8 term).
- So .then/catch/finally handlers are always called after the current code is finished.
- If we need to guarantee that a piece of code is executed after .then/catch/finally, we can add it into a chained .then call.

## Promise API:

- There are 6 static methods in the Promise class.

**1. Promise.all**

- Let’s say we want many promises to execute in parallel and wait until all of them are ready.
- For instance, download several URLs in parallel and process the content once they are all done.
- That’s what Promise.all is for.
- The syntax is:

`let promise = Promise.all(iterable);`

- `Promise.all` takes an iterable (usually, an array of promises) and returns a new promise.

```
Promise.all([
  new Promise(resolve => setTimeout(() => resolve(1), 3000)), // 1
  new Promise(resolve => setTimeout(() => resolve(2), 2000)), // 2
  new Promise(resolve => setTimeout(() => resolve(3), 1000))  // 3
]).then(alert);
```

- **If any of the promises is rejected, the promise returned by Promise.all immediately rejects with that error.**

**2. Promise.allSettled**

- Promise.allSettled just waits for all promises to settle, regardless of the result. The resulting array has:

- `{status:"fulfilled", value:result}` for successful responses,
- `{status:"rejected", reason:error}` for errors.
- we can use Promise.allSettled to get the results of all given promises, even if some of them reject.

**3. Promise.race**

- Similar to Promise.all, but waits only for the first settled promise and gets its result (or error).

```
let promise = Promise.race(iterable);
```

**4. Promise.any**

- Similar to Promise.race, but waits only for the first fulfilled promise and gets its result. If all of the given promises are rejected, then the returned promise is rejected with AggregateError – a special error object that stores all promise errors in its errors property.

The syntax is:

```
let promise = Promise.any(iterable)
```

## Event listeners:

## Event Capturing / Trickling:

- Trickling down.

```

const childS = document.querySelector(".child");
childS.addEventListener("click", (e) => {
alert("child");
},useCapture);

```

- Here useCapture takes boolean true/false value like you want to bubble or capture if capture then make it true. false is by default.

```

const childS = document.querySelector(".child");
childS.addEventListener("click", (e) => {
alert("child");
});

const parent = document.querySelector(".parent");
parent.addEventListener("click", (e) => {
alert("parent");
},true);

```

## Stoping the bubbling :

- `e.stopPropagation();`

```

const childS = document.querySelector(".child");
childS.addEventListener("click", (e) => {
console.log("child");
e.stopPropagation();
});

```

## Event Occur only once :

- use `{once:true}` at end for listen only once.

```

const parent = document.querySelector(".parent");
parent.addEventListener(
"click",
(e) => {
console.log("parent");
},
{ once: true }
);

```

## Event Deligation:

- Insted of attaching eventlistener to all child element we can attach it to parent's.
- event deligation will depend on the event bubbling.
- Behaviour patterns achieve using delogation. means converting entered input to uppercase:

Benifits:

- saves lot of memory.
- writing less code
- dom manipulation (if we have attach to parent then if any extra child element is added then we no need to write eventlisteners for them)

loss:

- all events are not bubbled up.
- if we used stop propogation then it cannot used.

## Event Loop:

- it is checked whether the call stack is empty or not if empty then it will checked to microtask queue and if any function is there so it will send it to call stack and if not then it will check the callback queue if there any function then it will send to callstack .

## Browser layout:

![img](/images/browserStructure.png)

![img](/images/browserAPI.png)

![img](/images/queues.png)

## Microtask Queue:

- All the callback function that are fall through the promises will go inside the microtask queue. and it is called mutation oberver.

## fetch():

- it is a window object used for accessing the external content or accessing the API's. And it can be used with the promises.

## alert, prompt, confirm:

### alert

- This one we’ve seen already. It shows a message and waits for the user to press “OK”.

### prompt

The function prompt accepts two arguments:

```

result = prompt(title, [default]);

```

- title : The text to show the visitor.
- default: An optional second parameter, the initial value for the input field.

### confirm

The syntax:

```

result = confirm(question);

```

- The function confirm shows a modal window with a question and two buttons: OK and Cancel.

## JSON:

`JSON.stringify`: to convert JS objects into JSON.
`JSON.parse`: to convert JSON back into an javascript object.

- JSON is data-only language-independent specification, so some JavaScript-specific object properties are skipped by JSON.stringify.

  **Namely:**

- Function properties (methods).
- Symbolic keys and values.
- Properties that store undefined.

**Example:**

```

let user = {
sayHi() { // ignored
alert("Hello");
},
[Symbol("id")]: 123, // ignored
something: undefined // ignored
};

alert( JSON.stringify(user) ); // {} (empty object)

```

## Limitations:

- The important limitation: there must be no circular references.

## Higher Order Functions:

- A function which takes a function as argument or return a function is called `higher order function`.

```

function x() {
console.log("Namaste");
}
function y(x) {
x();
}

```

## Functional programming:

- are resusability, modularity, composition.

## Error Handling:

- It is used to handle or show our errors in document.
- for catching the error we use `try`...`catch` block.
- A code we write in our try block and if that try block's code has error then the control will go to the catch block and our error message is shown that we have written in our catch block.
- we can also add custom error message or the error that has occured that we also catch it.
- But this try catch will only properly run on the synchronous Js. it will not properly work on Async. Js like setTimeout or interval.
- And if we want to add it to setTimeout then we have to add try catch inside the setTimeout.
- `finally`: it written at last and after catch block and whatever code is written in that block is always run whether try has run or catch has run.

### Types of error:

```

EvalError
RangeError
ReferenceError
SyntaxError
TypeError
URIError
AggregateError

```

## Async / await:

- There is a special syntax to work with promises in javascript.
- A function is made async using an async keyword before function.
- The word “async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.

```
async function hibye(){
  return 7;
}

hibye().then(alert)
```

### await:

- there is another keyword await that only works inside the async functions.

```
let value = await promise;
```

- The await keywords makes JS wait untill the promise settles or fullfilled or resolve and return its value to variable

## Loading the javascript or how Html is parse?.

## Async Vs Defer Vs Normal way to

- `async` and `defer` are the attributes that are used in the script tag.
- when we are load a webpage at that time two events are occur: 1. Html parsing and 2. Js downloading

![img](/images/async%20vs%20defer.png)

## Debouncing vs Throttling:

- This two are the ways or solutions to avoiding or making the unnecessary api calls.

### case studies:

- Suppose we have a search bar so insted of calling the api on every key press it is more convinient to make api call when the time difference between the two key press is more than some time. so for this method is called debouncing.
- where in the case of throttling we can set certain time interval it will call that api after every 10 second like that.

- other scenario is that resizing the window, pressing the button, or click on the screen like when we are playing the game so that time for shooting the gun like for machine gun we can set time interval for shooting time like 100ms and for the pistol we can set more time interval.

- which method is better ?
- so it is totally depends on the usecase or scenario we have.

## Symbol:

- it is a new datatype which is used for unique values.

## Iterators:

- It is a method that is used to iterate over the strings, objects and arrays.
- It performs the operations like others which are forin foreach and forof etc but the diff between them is for filtering we have to add if statement on each loop where in iterator it become more easier.

```

let numbers = [100, 200, 300];
let iter = numbers [Symbol.iterator]();
iter.next();
console.log(iter.next().value);
console.log(iter.next().done);

```

- Iterator with string.

![iet](/images/iterator.png)

## Generators:

- Regular functions return only one, single value (or nothing).
- Generators can return (“yield”) multiple values, one after another, on-demand.
- To create a generator, we need a special syntax construct: function\*, so-called “generator function”.
- Generator functions behave differently from regular ones. When such function is called, it doesn’t run its code. Instead it returns a special object, called “generator object”, to manage the execution.

```
function* generateSequence() {
  yield 1;
  yield 2;
  return 3;
}

// "generator function" creates "generator object"
let generator = generateSequence();
alert(generator); // [object Generator]
```

- The main method of a generator is next(). When called, it runs the execution until the nearest yield <value> statement (value can be omitted, then it’s undefined). Then the function execution pauses, and the yielded value is returned to the outer code.
- The result of next() is always an object with two properties:
- `value`: the yielded value.
- `done`: true if the function code has finished, otherwise false

```
let one = generator.next();
alert(one) // gives value and done
```

**Generators are iterable**

- As you probably already guessed looking at the next() method, generators are iterable.
- We can loop over their values using for..of:

### Accessing properties & length properties:

![image](/images/string-properties.png)

## Deep copy/cloning Or Shallow copy/cloning:

1. Shallow copy will make copy but if we changed any items in copied object then it will changed that item in main object also.

- for this we try `newObject = old_object` ;

2. Deep copy will make copy but if we changed any item in copied object then it will not changed into main object.

- for that we use `newobject = JSON.parse(JSON.stringify(old_object_name))`.

## what is pure functions:

- Pure functions are functions that don't produce side effects and, when called with the same input parameters, will always return the same output. You can use pure functions to ensure your code is clean, maintainable, and testable.

- The **return value** of the function on the function call should only be dependent on the input function arguments.

- It should not **modify any non-local** state. It means the function should not manipulate anything other than the data stored in the local variables declared within the function.

- The function should not have any side effects, such as reassigning non-local variables, mutating the state of any part of code that is not inside the function, or calling any non-pure functions inside it.

```

function operationAdd(a, b){ // A pure function adding two integers passed in it.
return a+b;
}

function operationDivide(a, b){ // Pure function to divide two integers passed in it.
return a/b;
}

function operationMulti(a, b){ // Pure function to multiple two integers passed in it.
return a\*b;
}
console.log( // Calling all the pure functions
operationAdd(2,5),
operationMulti(3,2),
operationDivide(20,5)
);

```

- No side effects some common side effects:
- Making an HTTP request
- Mutating any data that is not part of the function
- Printing to a screen or console
- DOM Query/Manipulation
- Using Math.random()
- Getting the current time

## BreakPoints:

- A breakpoint is a point of code where the debugger will automatically pause the JavaScript execution.
- While the code is paused, we can examine current variables, execute commands in the console etc. In other words, we can debug it.

- `Watch` – shows current values for any expressions.
- `Call Stack` – shows the nested calls chain.
- `Scope` – current variables.

## Transpilers

- A transpiler is a special piece of software that translates source code to another source code. It can parse (“read and understand”) modern code and rewrite it using older syntax constructs, so that it’ll also work in outdated engines.

- Speaking of names, Babel is one of the most prominent transpilers out there.

## Polyfills

- Polyfills are like handy tools that web developers can use to make their websites work properly even if some web browsers don't support certain features.
- They work by checking if a browser can understand and use a particular feature. If the browser can handle it, the polyfill steps aside and lets the browser do its thing.
- But if the browser doesn't support the feature, the polyfill jumps in and provides its own version of that feature, so the website still functions correctly.
- For example, Math.trunc(n) is a function that “cuts off” the decimal part of a number, e.g Math.trunc(1.23) returns 1.
- They work by checking if a browser can understand and use a particular feature. If the browser can handle it, the polyfill steps aside and lets the browser do its thing. But if the browser doesn't support the feature, the polyfill jumps in and provides its own version of that feature, so the website still functions correctly

## Two interesting polyfill libraries are:

- `core js` that supports a lot, allows to include only needed features.
- `polyfill.io` service that provides a script with polyfills, depending on the features and user’s browser.

## Symbol type

- There is a primitive in JavaScript used to create a globally unique reference via the function Symbol():

```
- const firstName = Symbol("name");
```

**Symbols in an object literal**

- If we want to use a symbol in an object literal {...}, we need square brackets around it.
- Like this:

```

let id = Symbol("id");

let user = {
name: "John",
[id]: 123 // not "id": 123
};

```

**Symbols are skipped by for…in**

```

let id = Symbol("id");
let user = {
name: "John",
age: 30,
[id]: 123
};

for (let key in user) alert(key);

```

**In contrast, Object.assign copies both string and symbol properties:**

- Symbol is a primitive type for unique identifiers.

- Symbols are created with Symbol() call with an optional description (name).

- Symbols are always different values, even if they have the same name. If we want same-named symbols to be equal, then we should use the global registry: Symbol.for(key) returns (creates if needed) a global symbol with key as the name. Multiple calls of Symbol.for with the same key return exactly the same symbol.

- Symbols have two main use cases:

- **“Hidden” object properties.**

- If we want to add a property into an object that “belongs” to another script or a library, we can create a symbol and use it as a property key. A symbolic property does not appear in for..in, so it won’t be accidentally processed together with other properties. Also it won’t be accessed directly, because another script does not have our symbol. So the property will be protected from accidental use or overwrite.

- So we can “covertly” hide something into objects that we need, but others should not see, using symbolic properties.

## Map

- Map is a collection of keyed data items, just like an Object. But the main difference is that Map allows keys of any type.

- Methods and properties are:

- new Map() – creates the map.
- map.set(key, value) – stores the value by the key.
- map.get(key) – returns the value by the key, undefined if key doesn’t exist in map.
- map.has(key) – returns true if the key exists, false otherwise.
- map.delete(key) – removes the element (the key/value pair) by the key.
- map.clear() – removes everything from the map.
- map.size – returns the current element count.

## Iteration over Map

For looping over a map, there are 3 methods:

- map.keys() – returns an iterable for keys,
- map.values() – returns an iterable for values,
- map.entries() – returns an iterable for entries [key, value], it’s used by default in for..of.

## Set

A Set is a special type collection – “set of values” (without keys), where each value may occur only once.

Its main methods are:

- new Set([iterable]) – creates the set, and if an iterable object is provided (usually an array), copies values from it into the set.
- set.add(value) – adds a value, returns the set itself.
- set.delete(value) – removes the value, returns true if value existed at the moment of the call, otherwise false.
- set.has(value) – returns true if the value exists in the set, otherwise false.
- set.clear() – removes everything from the set.
- set.size – is the elements count.

```

```

## ProtoType:

```
let animal = {
  eats: true
};
let rabbit = {
  jumps: true
};

rabbit.__proto__ = animal; // sets rabbit.[[Prototype]] = animal
```

- Now if we read a property from rabbit, and it’s missing, JavaScript will automatically take it from animal.

```
alert( rabbit.eats ); // true (**)
alert( rabbit.jumps ); // true
```

- **we can also assign it as :**

```
let animal = {
  eats: true,
  walk() {
    alert("Animal walk");
  }
};

let rabbit = {
  jumps: true,
  __proto__: animal
};

```

- **Please note that **`__proto__`** is not the same as the internal `[[Prototype]]` property. It’s a getter/setter for `[[Prototype]]`**
- The **`__proto__`** property is a bit outdated. It exists for historical reasons, modern JavaScript suggests that we should use Object.getPrototypeOf/Object.setPrototypeOf functions instead that get/set the prototype.

```
let animal = {
  eats: true
};

let rabbit = {
  jumps: true,
  __proto__: animal
};

// Object.keys only returns own keys
alert(Object.keys(rabbit)); // jumps

// for..in loops over both own and inherited keys
for(let prop in rabbit) alert(prop); // jumps, then eats
```

- there’s a built-in method obj.hasOwnProperty(key): it returns true if obj has its own (not inherited) property named key.

```

for(let prop in rabbit) {
  let isOwn = rabbit.hasOwnProperty(prop);

  if (isOwn) {
    alert(`Our: ${prop}`); // Our: jumps
  } else {
    alert(`Inherited: ${prop}`); // Inherited: eats
  }
}
```

**Example:**

```
We have two hamsters: speedy and lazy inheriting from the general hamster object.

When we feed one of them, the other one is also full. Why? How can we fix it?

let hamster = {
  stomach: [],

  eat(food) {
    this.stomach.push(food);
  }
};

let speedy = {
  __proto__: hamster
};

let lazy = {
  __proto__: hamster
};

// This one found the food
speedy.eat("apple");
alert( speedy.stomach ); // apple

// This one also has it, why? fix please.
alert( lazy.stomach ); // apple
```

**Changed:**

```
let hamster = {
  stomach: [],
  eat(food) {
    // assign to this.stomach instead of this.stomach.push
    this.stomach = [food];
  }
};

```

<!-- another way -->

```
let speedy = {
  __proto__: hamster,
  stomach: []
};

let lazy = {
  __proto__: hamster,
  stomach: []
};

```

- We can use constructor property to create a new object using the same constructor as the existing one.

- any object that we have created the JS Engine will add prototype object with it which contains built in methods that we can apply on object. It is also same in the case of array and function.

```
let obj = {a:"Dsa"}
obj.__proto__ which is same as Object.prototype

let arr = [];
arr.__proto__.__proto__ which is same as Object.prototype


let arr = [1, 2, 3];

// it inherits from Array.prototype?
alert( arr.__proto__ === Array.prototype ); // true

// then from Object.prototype?
alert( arr.__proto__.__proto__ === Object.prototype ); // true

// and null on the top.
alert( arr.__proto__.__proto__.__proto__ ); // null


function f() {}

alert(f.__proto__ == Function.prototype); // true
alert(f.__proto__.__proto__ == Object.prototype); // true, inherit from objects

```

## Inheritence:

- we have super() method using which we can access the properties of parent class in child class. we can also
- Classes provide "super" keyword for that.
- super.method(...) to call a parent method.
- super(...) to call a parent constructor (inside our constructor only)

- `Overriding constructor`

```
class Animal {

  constructor(name) {
    this.name = name;
  }

}

class Rabbit extends Animal {
  constructor(name) {
    this.name = name;
    this.created = Date.now();
  }
}

let rabbit = new Rabbit("White Rabbit"); // Error: this is not defined
alert(rabbit.name);
```

- to solve this we have to use super method for call parent constructor and then add extra property or method in that

## Static properties and methods

- We can also assign a method to the class as a whole. Such methods are called static.
- In a class declaration, they are prepended by static keyword, like this:

```
class User {
  static staticMethod() {
    alert(this === User);
  }
}

User.staticMethod(); // true
```

## Protected & Private properties:

- Protected fields start with `_`. That’s a well-known convention, not enforced at the language level. Programmers should only access a field starting with `_` from its class and classes inheriting from it.

- Private fields start with #. JavaScript makes sure we can only access those from inside the class.

## Class checking: "instanceof"

- The instanceof operator allows to check whether an object belongs to a certain class. It also takes inheritance into account.

## The instanceof operator

- The syntax is:
  `obj instanceof Class`

- It returns true if obj belongs to the Class or a class inheriting from it.

## Types with object

- For a number, it will be [object Number]
- For a boolean, it will be [object Boolean]
- For null: [object Null]
- For undefined: [object Undefined]
- For arrays: [object Array]

## Mixins

- In JavaScript we can only inherit from a single object. There can be only one [[Prototype]] for an object. And a class may extend only one other class.
- we have a class User and a class EventEmitter that implements event generation, and we’d like to add the functionality of EventEmitter to User, so that our users can emit events.
- There’s a concept that can help here, called “mixins”.
- a mixin is a class containing methods that can be used by other classes without a need to inherit from it.
- In other words, a mixin provides methods that implement a certain behavior, but we do not use it alone, we use it to add the behavior to other classes.

**Example:**

```
// mixin
let sayHiMixin = {
  sayHi() {
    alert(`Hello ${this.name}`);
  },
  sayBye() {
    alert(`Bye ${this.name}`);
  }
};

// usage:
class User {
  constructor(name) {
    this.name = name;
  }
}

// copy the methods
Object.assign(User.prototype, sayHiMixin);

// now User can say hi
new User("Dude").sayHi(); // Hello Dude!
```

## Error object

When an error occurs, JavaScript generates an object containing the details about it. The object is then passed as an argument to catch:

**name**
Error name. For instance, for an undefined variable that’s "ReferenceError".

**message**
Textual message about error details.
There are other non-standard properties available in most environments. One of most widely used and supported is:

**stack**
Current call stack: a string with information about the sequence of nested calls that led to the error. Used for debugging purposes.

## “Throw” operator

- The throw operator generates an error.

The syntax is:

```
throw <error object>
```

- JavaScript has many built-in constructors for standard errors: Error, SyntaxError, ReferenceError, TypeError and others.

```
let error = new Error(message);
// or
let error = new SyntaxError(message);
let error = new ReferenceError(message);
```

```
try {
   ... try to execute the code ...
} catch (err) {
   ... handle errors ...
} finally {
   ... execute always ...
}
```

# BOM:

## how to create cutome html element?
- customeElement.define(name,constructor,?options)

**clientWidth & clientHeight:**

- content height + padding.
- **margine, border,scroll height/width not included.**
- clientWidth and clientHeight does NOT work with inline HTML elements (like span, em, or a). It’ll just return 0!

**offsetWidth & offsetHeight**

- content height + padding + border + scrollbar
- **margin not included**.
- offsetWidth/offsetHeight – “outer” width/height of an element including borders.
- ![MicrosoftTeams-image](https://github.com/gunjan2012/documentations/assets/125242584/4ebf933d-e831-40c6-9da8-5d5baeae6bf3)

- **let coords = elem.getBoundingClientRect()**

**scrollWidth/Height**
- content which was overflow that height.

## The difference: CSS width versus clientWidth

- clientWidth is numeric, while getComputedStyle(elem).width returns a string with px at the end.
- getComputedStyle may return non-numeric width like "auto" for an inline element.
- clientWidth is the inner content area of the element plus paddings, while CSS width (with standard box-sizing) is the inner content area without paddings.
- The clientWidth property is always the same: scrollbar size is substracted if reserved.

**Place the ball in the field center:**

```
ball.style.left = Math.round(field.clientWidth / 2 - ball.offsetWidth / 2) + 'px';
ball.style.top = Math.round(field.clientHeight / 2 - ball.offsetHeight / 2) + 'px';
```

## addEventListener

- The fundamental problem of the aforementioned ways to assign handlers is that we can’t assign multiple handlers to one event.
- `element.addEventListener(event, handler, [options]);`

**options**

- An additional optional object with properties:

- `once`: if true, then the listener is automatically removed after it triggers.
- `capture`: the phase where to handle the event {capture: false/true}. for bubbling and capturing.
- `passive`: if true, then the handler will not call `preventDefault()`

- same for removeEventListeners
- `element.removeEventListener(event, handler, [options]);`

## `DOMContentLoaded`:

- That triggers when the document is loaded and the DOM has been built.

```
document.addEventListener("DOMContentLoaded", function() {
  alert("DOM built");
});
```

## Event Object:

- Some properties of event object:

- `event.type`
  Event type, here it’s "click".
- `event.currentTarget`
  Element that handled the event.
- `event.eventPhase`
  The current phase (capturing=1, target=2, bubbling=3).
- `event.clientX / event.clientY`
  Window-relative coordinates of the cursor, for pointer events.

- When an event occurs, its handleEvent method is called.

**Example:**

- Create a button that hides itself on click.
- `<input type="button" onclick="this.hidden=true" value="Click to hide">`

### Which handlers run?

```
button.addEventListener("click", () => alert("1"));

button.removeEventListener("click", () => alert("1"));

button.onclick = () => alert(2);
```

- The answer is 1 and 2.

## Bubbling

- The bubbling principle is simple.
- When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

**Ex:**

- if we have `FORM > DIV > P`
- So if we click on <p>, then we’ll see 3 alerts: `p → div → form`.
- The process is called “`bubbling`”, because events “bubble” from the inner element up through parents like a bubble in the water.
- For instance, a focus event does not bubble.

## event.target

- A handler on a parent element can always get the details about where it actually happened.
- The most deeply nested element that caused the event is called a target element, accessible as event.target.
- Note the differences from this (=event.currentTarget):
- **event.target** – is the “target” element that initiated the event, it doesn’t change through the bubbling process.
  **this** – is the “current” element, the one that has a currently running handler on it.

- so in the above example the `this` refers to current element which is form. event.target is the actual element inside the form that was clicked.

## Stopping bubbling

- A bubbling event goes from the target element straight up. Normally it goes upwards till `<html>`, and then to document object, and some events even reach window, calling all handlers on the path.
- But any handler may decide that the event has been fully processed and stop the bubbling.
- The method for it is **event.stopPropagation()**

## event.stopImmediatePropagation()

- If an element has multiple event handlers on a single event, then even if one of them stops the bubbling, the other ones still execute.
- In other words, event.stopPropagation() stops the move upwards, but on the current element all other handlers will run.
- To stop the bubbling and prevent handlers on the current element from running, there’s a method event.stopImmediatePropagation(). After it no other handlers execute.

## Capturing

- There’s another phase of event processing called “capturing”. It is rarely used in real code, but sometimes can be useful.

- The standard DOM Events describes 3 phases of event propagation:
- `Capturing phase` – the event goes down to the element.
- `Target phase` – the event reached the target element.
- `Bubbling phase` – the event bubbles up from the element.

- To catch an event on the capturing phase, we need to set the handler capture option to true
- false value is by default.

```
elem.addEventListener(..., {capture: true})

// or, just "true" is an alias to {capture: true}
elem.addEventListener(..., true)
```

- In other words, normally the event goes first down (“capturing”) and then up (“bubbling”). But if event.stopPropagation() is called during the capturing phase, then the event travel stops, no bubbling will occur.

## Event delegation

- Capturing and bubbling allow us to implement one of the most powerful event handling patterns called event delegation.
- The idea is that if we have a lot of elements handled in a similar way, then instead of assigning a handler to each of them – we put a single handler on their common ancestor.
- In the handler we get event.target to see where the event actually happened and handle it.
- The method event.target.closest(selector) returns the nearest ancestor that matches the selector.

- There are other uses for event delegation.
- Let’s say, we want to make a menu with buttons “Save”, “Load”, “Search” and so on. And there’s an object with methods save, load, search… How to match them?
- The first idea may be to assign a separate handler to each button. But there’s a more elegant solution. We can add a handler for the whole menu and data-action attributes for buttons that has the method to call:
- `<button data-action="save">Click to Save</button>`
- in js we can access this by adding `event.target.dataset.action`

### The “behavior” pattern:

- The pattern has two parts:

- We add a custom attribute to an element that describes its behavior.
- A document-wide handler tracks events, and if an event happens on an attributed element – performs the action.

## Behavior: Counter

- For instance, here the attribute data-counter adds a behavior: “increase value on click” to buttons:
- we can access the data attribute using `dataset.here_we_provide_dataattribute name`

## Behavior: Toggler

- One more example of behavior. A click on an element with the attribute data-toggle-id will show/hide the element with the given id

## Benefits of event delegation:

1. improves memory space
2. mitigates risk of performance bottle neck
3. Dom manipulation
4. when elements get added dynamically,the process of adding events is slow

## Limitations:

1. All the events are not bubbled up, some events like blur, focus are not bubbled up
2. if e.stopPropogation is used in child, then events are not bubbled up

## Event constructor:

```
let event = new Event(type[, options]);
```

**Arguments:**

- `type` – event type, a string like "click" or our own like "my-event".
- `options` – the object with two optional properties:
  - `bubbles`: true/false – if true, then the event bubbles.
  - `cancelable`: true/false – if true, then the “default action” may be prevented. Later we’ll see what it means for custom events.

By default both are false: {bubbles: false, cancelable: false}.

## dispatchEvent

- After an event object is created, we should “run” it on an element using the call `elem.dispatchEvent(event)`.

## event.preventDefault()

- Many browser events have a “default action”, such as navigating to a link, starting a selection, and so on.
- By calling event.preventDefault(), an event handler may send a signal that those actions should be canceled.

## Crossorigin policy

- There’s a rule: scripts from one site can’t access contents of the other site. So, e.g. a script at https://facebook.com can’t read the user’s mailbox at https://gmail.com.
- Or, to be more precise, one origin (domain/port/protocol triplet) can’t access the content from another one. So even if we have a subdomain, or just another port, these are different origins with no access to each other.
- To allow cross-origin access, the `<script>` tag needs to have the crossorigin attribute, plus the remote server must provide special headers.

- `No crossorigin attribute` – access prohibited.
- `crossorigin="anonymous`" – access allowed if the server responds with the header Access-Control-Allow-Origin with \* or our origin. Browser does not send authorization information and cookies to remote server.
- `crossorigin="use-credentials"` – access allowed if the server sends back the header Access-Control-Allow-Origin with our origin and Access-Control-Allow-Credentials: true. Browser sends authorization information and cookies to remote server.

## Mutation observer

- MutationObserver is a built-in object that observes a DOM element and fires a callback when it detects a change.

## Syntax:

- Easy to use
- First, we create an observer with a callback-function:
- `let observer = new MutationObserver(callback);`
- `observer.observe(node, config);`

config is an object with boolean options “what kind of changes to react on”:

`childList` – changes in the direct children of node,
`subtree` – in all descendants of node,
`attributes` – attributes of node,
`attributeFilter` – an array of attribute names, to observe only selected ones.
`characterData` – whether to observe node.data (text content),

## When such thing may be useful?

Imagine the situation when you need to add a third-party script that contains useful functionality, but also does something unwanted, e.g. shows ads `<div class="ads">Unwanted ads</div>`.

Naturally, the third-party script provides no mechanisms to remove it.

Using MutationObserver, we can detect when the unwanted element appears in our DOM and remove it.

There are other situations when a third-party script adds something into our document, and we’d like to detect, when it happens, to adapt our page, dynamically resize something etc.

MutationObserver allows to implement this.

## Additional methods

There’s a method to stop observing the node:

`observer.disconnect()` – stops the observation.
When we stop the observing, it might be possible that some changes were not yet processed by the observer. In such cases, we use
`observer.takeRecords()` – gets a list of unprocessed mutation records – those that happened, but the callback has not handled them.

```
console.log(1); //1

setTimeout(() => console.log(2)); // callback 1 = 5

Promise.resolve().then(() => console.log(3)); // micro 1 = 3

Promise.resolve().then(() => setTimeout(() => console.log(4))); // micro 2 and when m2 C3  = 6

Promise.resolve().then(() => console.log(5)); // M3 = 4

setTimeout(() => console.log(6)); // C2 = 7

console.log(7); // 2
```

## storing data in browser:

### `cookie`:

- Cookies are small strings of data that are stored directly in the browser. They are a part of the HTTP protocol.
- Cookies are usually set by a web-server using the response Set-Cookie HTTP-header. Then, the browser automatically adds them to (almost) every request to the same domain using the Cookie HTTP-header.
- One of the most widespread use cases is authentication:
- We can also access cookies from the browser, using document.cookie property.
- One cookie may not exceed 4KB in size. The number of cookies allowed on a domain is around 20+ (varies by browser).
- the cookie dies when the browser is closed.

### sessionStorage

- The sessionStorage object is used much less often than localStorage.

- Properties and methods are the same, but it’s much more limited:
- The sessionStorage exists only within the current browser tab.
- Another tab with the same page will have a different storage.
- But it is shared between iframes in the same tab (assuming they come from the same origin).
- The data survives page refresh, but not closing/opening the tab.

- The limit is 5mb+,
