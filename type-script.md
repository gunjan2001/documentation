# Typescript:

## Features:

- Superset of Java Script (Java Script plus some other Feature)
- TypeScript is an Object-Oriented language
- It has a feature known as Static typing
- Typscript -> compile -> Java Script : **command -> tsc <filename>.ts**
- Used in Front End also Backend with Node.js
- Includes most features from ES6 , ES7
- extenctions : .ts and .tsx
- tsconfig.json file used to configure how Typescript works

## Dynamic vs Static Typing:

- `Dynamically Typed Languages`, the types are associated with run-time values and not named explicitly in your code Eg : JavaScript , PHP , Python
- `Statically Typed Languages`, you explicitly assign types to variables, function paramers , return values. Eg : Java , C , C++ , Go

## Installation

`npm i -g typescript` </br>
`tsc --init`

## Why do we need TypeScript?

- Static Typing
- Type Inference
- Better IDE Support: The development experience with TypeScript is a great improvement over JavaScript.
- Strict Null Checking: Errors, like **cannot read property ‘x’ of undefined**, is common in JavaScript programming. You can avoid most of these kinds of errors since one cannot use a variable that is not known to the TypeScript compiler.

## What are the Components of TypeScript?

- There are three different types of components in TypeScript which includes:

1. **Language** − It comprises of the syntax, keywords, and type annotations.
2. **The TypeScript Compiler** − This compiler (tsc) converts the instructions written in TypeScript to its JavaScript equivalent.
3. **The TypeScript Language Service** − The Language Service exposes an additional layer around the core compiler pipeline, editor-like applications.

## Can we combine multiple .ts files into a single .js file?

- Yes, we can combine multiple files. While compiling, we need to add –outFILE [OutputJSFileName] option.
- Ex: `tsc --outFile comman.js file1.ts file2.ts file3.ts`

## What are the different types of TypeScript?

- Built-in: This includes number, string, boolean, void, null and undefined.
- User-defined: It includes Enumerations (enums), classes, interfaces, arrays, and tuple.

## List some of the utility types provided by TypeScript and explain their usage.

- `**Partial<Type>**` Constructs a type with all properties of Type set to optional.
- `**Required<Type>**` Constructs a type consisting of all properties of Type set to required.
- `**Readonly<Type>**` Constructs a type with all properties of Type set to readonly.
- `**Record<Keys, Type>**` Constructs an object type with property keys are of type Keys, and values are Type.

## What are the ‘implements’ clauses in TypeScript?

- An implements clause is used to check that a class satisfies the contract specified by an interface. If a class implements an interface and doesn’t implement that interface, the TypeScript compiler issues an error.

```
interface Runnable {
run(): void;
}

class Job implements Runnable {
run() {
  console.log("running the scheduled job!");
}
}
```

## Is it possible to compile .ts automatically with real-time changes in the .ts file?

- Yes, we can compile “.ts” automatically with real-time changes in the .ts file. This can be done by using –watch compiler option:
- `tsc --watch file1.ts`

## What are Mixins?

- mixins are a way to extend the behavior of a class by combining the functionalities of multiple classes into a single class.
- They allow you to reuse and compose code from different sources, enabling you to create more flexible and modular code.
- The basic idea behind mixins is to create smaller, specialized classes with specific features and then mix them together to form a larger, more complex class. This approach promotes code reusability and keeps your classes focused on specific concerns, making your code easier to maintain and understand.
- The idea is simple, instead of a class A extending class B to get its functionality, function B takes class A and returns a new class with this added functionality. Here, function B is a mixin.

## what is .d.ts file?

- d. ts files are called type declaration files. They exist for one purpose only: to describe the shape of an existing module and they only contain type information used for type checking.

## What are Ambients in TypeScripts and when to use them?

- Ambient declarations files are like docs files. If the source changes, the docs need to be kept updated and if the ambient declaration file is not updated, then you will get compiler errors.
- "ambient" refers to declarations that describe types and symbols from external JavaScript libraries or environments that are not natively written in TypeScript. When you want to use an external library in your TypeScript project, but that library doesn't come with its own type declarations, you can create ambient declarations to provide type information for the library.

- The ambient declarations, also known as "ambient type declarations" or "ambient module declarations," are typically defined in declaration files with a .d.ts extension. These files contain TypeScript type declarations without any associated implementation. They serve as a way to tell the TypeScript compiler about the shape and types of variables, functions, classes, and other constructs that exist outside of the TypeScript codebase.

## Types:

Here is a list of some commonly used types in TypeScript:

1. `number`: Represents numeric values, including integers and floating-point numbers.

2. `string`: Represents textual values or strings of characters.

3. `boolean`: Represents a logical value, either `true` or `false`.

4. `object`: Represents a non-primitive value that can be an instance of a class, an array, or a plain JavaScript object. **`create interface`**

5. `Array<T>`: Represents an array of elements of type `T`. Ex. **`const data: number[] = [1,2,3,4]`**

6. `Tuple`: Represents an array with a fixed number of elements of different types, where the type of each element is known. **`Ex: let rgb : [number, number, number] = [255,122,154];`**

7. `any`: Represents any type and allows dynamic typing. It disables static type checking and is generally not recommended unless necessary.

8. `void`: Represents the absence of a value. Typically used as the return type of functions that do not return a value.

9. `null` and `undefined`: Represents the absence of a value or uninitialized variables.

10. `never`: Represents a type that never occurs. It is used to indicate functions that never return or variables that cannot have a value. But on that case we can return error from that function.

11. `unknown`: Represents a value that could be of any type. It is similar to `any`, but with type checking required before performing operations.

12. `enum`: Represents a set of named values or constants.

13. `union`: Represents a type that can be one of several possible types. It is denoted by using the `|` operator between types.

14. `intersection`: Represents a type that combines multiple types. It is denoted by using the `&` operator between types.

15. `type`: Allows creating custom types using type aliases or type literals. It provides the ability to define complex types and reuse them.

16. `interface`: Defines the structure and contract of an object. It describes the properties, methods, and behavior that an object should have.

17. `class`: Represents a blueprint for creating objects with properties and methods.

## type `any`:

```

let anyvalue:any = true;
let name:string = anyvalue;
console.log(typeof name);

here the type of name is boolean.
```

- But if we have write boolean insted of any so it will give error like `type boolean is not assignable to type string`.

## Implicit Type:

```

let cid : number = 45;
let pname : string = "hsd"

```

## Expicitly Type | Type Assertions:

```
let cid: any = 1;
let customerId1 = `<number>`cid
let customerId1 = cid as number;
```

## Top and bottom types:

## Top Types:

- TypeScript provides two of these types: `any` and `unknown`.
- Like any, unknown can accept any value.

## Bottom Types:

- TypeScript provides one bottom type: `never`.

## Type casting:

```
let customerId2 = cid as string
```

## Literal Types:

```
const constantString = "Hello World";
// Because `constantString` can only represent 1 possible string, it
// has a literal type representation
constantString;

`const constantString: "Hello World"`
```

- difference between string literal type and string values type:
- Example :

  ```
  type name = "gunjan" // literal type - only asigned string it will take
  type name = string // any string value can take this
  ```

- But by combining literals into unions, you can express a much more useful concept - for example, functions that only accept a certain set of known values:

```
function printText(s: string, alignment: "left" | "right" | "center") {
  // ...
}
```

- There’s one more kind of literal type: boolean literals.
- There are only two boolean literal types, and as you might guess, they are the types true and false. The type boolean itself is actually just an alias for the union `true | false`.

```
declare function handleRequest(url: string, method: "GET" | "POST"): void;

const req = { url: "https://example.com", method: "GET" };
handleRequest(req.url, req.method); //gives error
```

- There are two ways to work around this.

1. You can change the inference by adding a type assertion in either location:

```
// Change 1:
const req = { url: "https://example.com", method: "GET" as "GET" };
// Change 2
handleRequest(req.url, req.method as "GET");
```

2. You can use as const to convert the entire object to be type literals:

```
const req = { url: "https://example.com", method: "GET" } as const;
handleRequest(req.url, req.method);
```

## Non null assertion:

- use `!` when you know that the value can’t be null or undefined.

## generics:

generics allow you to create reusable components and functions that can work with a variety of data types while preserving type safety.

**1. Generic Interfaces:** Interfaces can also be defined with generic type parameters. This allows you to create interfaces that can work with different types.

```
interface List<T> {
  add(item: T): void;
  get(index: number): T;
}

```

**4. Constraints:** TypeScript provides a way to add constraints to generic type parameters.

```
interface Lengthwise {
  length: number;
}

function logLength<T extends Lengthwise>(arg: T): void {
  console.log(arg.length);
}

```

## Type inference:

- when we intialize any variable and at that time if we give value to that variable without giving it's type so typescript will autometically infer it's type, this is called `type inference`.

**If our function will not return something then it is good to write void in that**

## void & never:

- `void` will return `nothing` where `never` will never return.

## type `unknown` vs type `any`:

- Anything is assignable to unknown , but type `unknown` isn't assignable to anything.
- This means that if you have a variable of type unknown you cannot perform any operation on it without first checking its type using a type guard or casting it to a different type.
- while we are using type **any** so typescript will never check the type of particular where in **unknown** type typescript will check the type of that particular.

```

let myVariable: any = "hello";
console.log(myVariable.length); // This works, even though length is not a property of any

let myOtherVariable: unknown = "world";
console.log(myOtherVariable.length); // This generates an error, because length is not a property of unknown

if (typeof myOtherVariable === "string") {
console.log(myOtherVariable.length); // This works, because myOtherVariable is now narrowed down to a string
}

```

## Type Alias:

```
type details = {
  id:number | string,
  name:string
}
```

## InterFaces

InterFaces : Custom Types or Specific Structure to an Object or Function Can not use Interface with Premitives or Union

```
// Interface Over Type

  interface EmployeeInterface {
      readonly id: number,
      name: string,
      age: number,
      atOffice?: boolean,
      status: boolean
  }

  const Employees1: EmployeeInterface = {
      id: 1,
      name: 'Prince',
      age: 23,
      status: true
  }

```

## Interfaces with Function

```
interface MathFunc {
(x: number, y: number): number
}

const add: MathFunc = (x: number, y: number): number => x + y
const sub: MathFunc = (x: number, y: number): number => x - y
```

## `type` extending OR Mix & Match:

```

type cardNumber = {
  cardnumber: string
}
type cardDate  = {
  cardDate: string
}
// this is called mix & match
type cardDetails = cardNumber & cardDate & {
  cvv:number
}

```

## reopening of the interface:

- we can add new item in our interface later in time: see below

```
interface User2{
  githubtoken: string
}
```

## What is method overriding in TypeScript?

- If the subclass or the child class has the same method as declared in the parent class, it is known as method overriding. Basically, it redefines the base class methods in the derived class or child class.

Rules for Method Overriding:

- The method must have the same name as in the parent class
- It must have the same parameter as in the parent class.
- There must be an IS-A relationship or inheritance.

## Differences Between Type Aliases and Interfaces:

- **Syntax:** The syntax for defining a type and an interface is different.
- **Declaration Merging:** Interfaces support declaration merging, which means you can define an interface with the same name multiple times, and the declarations will be merged into a single interface.On the other hand, type aliases created with type cannot be merged.
- **Implements Clause:** Interfaces can be used to describe the shape of a class using the implements clause. Type aliases created with type cannot be used in this manner.
- **interface** is commonly used for defining object shapes, inheritance, and class contracts, while **type** is often used for creating aliases, union types, and mapped types.

## inheritence in interface:

- we can inherit all properties from one interface to another

```
interface admin extends User2 {
  role: string
}
```

## Enum:

- Enums are one of the few features TypeScript has which is not a type-level extension of JavaScript.
- Enums allow a developer to define a set of named constants.
- Using enums can make it easier to document intent, or create a set of distinct cases. TypeScript provides both numeric and string-based enums.
- One real-life example of using an enum in TypeScript is representing the days of the week.

**Example:**

```
enum Direction {
  Up,
  Down,
  Left,
  Right,
}
```

- Here, Up would have the value 0, Down would have 1, etc.
- If we give number in first and we give string in second so we have to assign all the string value to all enum property.
- Here The `enum` will produce the IIFE in javascript.
- By using `const` before enum we will not get IIFE in JS.
- If we have numeric index assign to enum values so it will be accessible by both that value and member it self but it is not possible in the case of string enum member Means **Keep in mind that string enum members do not get a reverse mapping generated at all.**
- It is a compile time error for constant enum expressions to be evaluated to NaN or Infinity.
- The `enum` will produce the below javascript code:

```

var choice;
(function (choice) {
choice[choice["AISLE"] = 0] = "AISLE";
choice[choice["MIDDEL"] = 8] = "MIDDEL";
choice[choice["WINDOW"] = 9] = "WINDOW";
})(choice || (choice = {}));
let seat1 = 8;
if (seat1 === choice.MIDDEL) {
console.log("middle seat");
}

```

**Enum constat member and computed member**

```
enum FileAccess {
  // constant members
  None,
  Read = 1 << 1,
  Write = 1 << 2,
  ReadWrite = Read | Write,
  // computed member
  G = "123".length,
}
```

## Ambient enums

- Ambient enums are used to describe the shape of already existing enum types.

```
declare enum Enum {
  A = 1,
  B,
  C = 2,
}
```

- One important difference between ambient and non-ambient enums is that, in regular enums, members that don’t have an initializer will be considered constant if its preceding enum member is considered constant.
- By contrast, an ambient (and non-const) enum member that does not have an initializer is always considered computed.

## Objects vs Enums

- In modern TypeScript, you may not need an enum when an object with as const could suffice:

```
const enum EDirection {
  Up,
  Down,
  Left,
  Right,
}

const ODirection = {
  Up: 0,
  Down: 1,
  Left: 2,
  Right: 3,
} as const;

// Using the enum as a parameter
function walk(dir: EDirection) {}

// It requires an extra line to pull out the values
type Direction = typeof ODirection[keyof typeof ODirection];
function run(dir: Direction) {}

walk(EDirection.Left);
run(ODirection.Right);
```

## Type narrowing:

- In TypeScript, type narrowing is the removal of types from a union.
- To narrow a variable to a specific type, we use the type guard.
- We can use the typeof operator with the variable name and compare it with the type that you expect for the variable.

```

function padLeft(padding: number | string, input: string) {
if (typeof padding === "number") > { // this checking of type is called `type gaurd`
return " ".repeat(padding) + input;
}
return padding + input;
}

```

## typeof type guards:

- `"string"`
- `"number"`
- `"bigint"`
- `"boolean"`
- `"symbol"`
- `"undefined"`
- `"object"`
- `"function"`

## how to implement narrowing in the object type:

- the below will give error like strs is null type also.

```

function printAll(strs: string | string[] | null) {
  if (typeof strs === "object") {
    for (const s of strs) {
      console.log(s);
    }
  } else if (typeof strs === "string") {
    console.log(strs);
  }
}

```

- To avoid we will give that strs are not null so for that add && strs in if condition:

```
function printAll(strs: string | string[] | null) {
  if (typeof strs === "object" && strs) { // this will give that strs are non null
    for (const s of strs) {
      console.log(s);
    }
  } else if (typeof strs === "string") {
    console.log(strs);
  }
}
```

## Using type predicates

- Type predicates are particularly useful when working with union types or when you want to perform type checking at runtime.

- A type predicate takes the form of a function that returns a boolean value. It has a special syntax where you use the parameterName is Type syntax. If the function returns true, TypeScript will consider the parameter to be of the specified type.

**Example:**

```
function isFish(pet: Fish | Bird): pet is Fish {
  return (pet as Fish).swim !== undefined;
}
```

- pet is Fish is our type predicate in this example. A predicate takes the form parameterName is Type, where parameterName must be the name of a parameter from the current function signature.

- They enable the TypeScript compiler to narrow down the possible types of variables, avoiding unnecessary type assertions and reducing the risk of runtime errors. By using type predicates, you can take advantage of TypeScript's static typing capabilities to write safer and more robust code.

## Assertion Functions:

- There’s a specific set of functions that throw an error if something unexpected happened. They’re called “assertion” functions. As an example, Node.js has a dedicated function for this called assert.

## Discriminated unions:

- Discriminated unions are useful for more than just talking about circles and squares. They’re good for representing any sort of messaging scheme in JavaScript, like when
  sending messages over the network (client/server communication), or encoding mutations in a state management framework.

Why we use this the below example will explain this :

```
interface Shape {
  kind: "circle" | "square";
  radius?: number;
  sideLength?: number;
}

function getArea(shape: Shape) {
  if (shape.kind === "circle") {
    return Math.PI * shape.radius! ** 2;
  }
}
```

- But this doesn’t feel ideal. We had to shout a bit at the type-checker with those non-null assertions (!) to convince it that shape.radius was defined, but those assertions are error-prone if we start to move code around.
- The problem with this encoding of Shape is that the type-checker doesn’t have any way to know whether or not radius or sideLength are present based on the kind property.

```
interface Circle {
  kind: "circle";
  radius: number;
}

interface Square {
  kind: "square";
  sideLength: number;
}

type Shape = Circle | Square;
```

```
function getArea(shape: Shape) {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "square":
      return shape.sideLength ** 2;
  }
}
```

## The never type

- When narrowing, you can reduce the options of a union to a point where you have removed all possibilities and have nothing left. In those cases, TypeScript will use a never type to represent a state which shouldn’t exist.
- The never type is assignable to every type; however, no type is assignable to never
- we can add this default to above switch where we can take default as never type.

```
default:
      const _exhaustiveCheck: never = shape;
      return _exhaustiveCheck;
```

## Functions:

### Types:

**1. Function Type Expressions**

- The simplest way to describe a function is with a function type expression. These types are syntactically similar to arrow functions:

```
function greeter(fn: (a: string) => void) {
  fn("Hello, World");
}

function printToConsole(s: string) {
  console.log(s);
}

greeter(printToConsole);
```

**2. Call Signature:**

```
type DescribableFunction = {
  description: string;
  (someArg: number): boolean; // Call Signature
};

```

**3. Construct Signatures**

```
type SomeConstructor = {
  new (s: string): SomeObject;
};
function fn(ctor: SomeConstructor) {
  return new ctor("hello");
}
```

**4. Generic Functions**

- In TypeScript, generics are used when we want to describe a correspondence between two values. We do this by declaring a type parameter in the function signature.

```
function firstElement<Type>(arr: Type[]): Type | undefined {
  return arr[0];
}
```

## Function overloading in Typescript:

**Scenario: how to create one function which is return string when one argument is passed and return number when two argument are pass to that function**

```
function add(a: Combinable, b: Combinable) {
if (typeof a === 'string' || typeof b === 'string') {
  return a.toString() + b.toString();
}
  return a + b;
}

const result = add("Gunjan","Dalwadi")
const result1 = add(8,5)

console.log(result);
console.log(result1);
```

- here the problem is that if we had check type of result it will give us string | number as type so we will not directly apply any method on result so solution is explicitly apply type to particular variable or we use function overloading.
- Below shows overloading By adding below code in above:

```
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: string, b: number): string;
function add(a: number, b: string): string;
```

## `readonly` keyword:

- using this keyword once we given any value to that object's item then we will not able to change that value.

```
type User = {
  readonly _id: string
  name: string
  email: string
  isActive: boolean
  }

  let myUser: User = {
  _id: "1245",
  name: "h",
  email: "h@h.com",
  isActive :false
}

myUser._id = "5476" // gives error : `Cannot assign to '_id' because it is a read-only property.`
```

- If we create readonly object then we can read and update property but not reassignable:

```
interface Home {
  readonly resident: { name: string; age: number };
}

function visitForBirthday(home: Home) {
  // We can read and update properties from 'home.resident'.
  console.log(`Happy birthday ${home.resident.name}!`);
  home.resident.age++;
}

function evict(home: Home) {
  // But we can't write to the 'resident' property itself on a 'Home'.
  home.resident = {
`Cannot assign to 'resident' because it is a read-only property`
    name: "Victor the Evictor",
    age: 42,
  };
}

```

- if we have one object in which we are giving values and create one interface which has same `readonly` property and we can create one object which has this readonly inerface and assign it the previous object. for example:

```
interface Person {
  name: string;
  age: number;
}

interface ReadonlyPerson {
  readonly name: string;
  readonly age: number;
}

let writablePerson: Person = {
  name: "Person McPersonface",
  age: 42,
};

// works
let readonlyPerson: ReadonlyPerson = writablePerson;

console.log(readonlyPerson.age); // prints '42'
writablePerson.age++;
console.log(readonlyPerson.age); // prints '43'
```

- Using mapping modifiers, you can remove readonly attributes.

## `?` = optional

- for example we have one property in our object that is not necessory or that is optional so for that we use `?` operator.

```

type User = {
  readonly _id: string
  name: string
  email: string
  isActive: boolean
  crediCard ?: number
  }

```

## Index Signatures:

- Sometimes you don’t know all the names of a type’s properties ahead of time, but you do know the shape of the values.

```
interface StringArray {
  [index: number]: string;
}
```

- Only some types are allowed for index signature properties: string, number, symbol , template string patterns, and union types consisting only of these.

## Intersections

- An intersection type allows you to combine multiple types into a single type. It creates a new type that has all the properties and methods of the intersected types.
- The resulting type will have all the members (properties and methods) from each of the intersected types.
- Intersection types are denoted using the & operator.
- Intersection types are useful when you want to create a type that must satisfy multiple conditions.

```
type Admin = {
  name: string;
};

type Employee = {
  age: number;
};

type NewType = Admin & Employee;
```

## Interfaces vs. Intersections:

- interfaces are primarily used for defining object or class structures, while intersection types are used to combine multiple types into a single type, allowing you to create more complex type definitions.
- The principal difference between the two is how conflicts are handled. see below example:

```
interface NumberToStringConverter {
  convert: (value: number) => string;
}

interface BidirectionalStringNumberConverter extends NumberToStringConverter {
  convert: (value: string) => number;
}
```

- Here in above it will give error like : `  Types of property 'convert' are incompatible.`

```
type NumberToStringConverter2 = {
  convert: (value: number) => string;
}

type BidirectionalStringNumberConverter = NumberToStringConverter2 & {
  convert: (value: string) => number;
}
```

## The Array Type:

- Much like the Box type above, Array itself is a generic type.

## The ReadonlyArray Type:

- The `ReadonlyArray` is a special type that describes arrays that shouldn’t be changed.

```
function doStuff(values: ReadonlyArray<string>) {
  // We can read from 'values'...
  const copy = values.slice();
  console.log(`The first value is ${values[0]}`);

  // ...but we can't mutate 'values'.
  values.push("hello!");
Property 'push' does not exist on type 'readonly string[]'.
}
```

- Unlike Array, there isn’t a ReadonlyArray constructor that we can use.

```
new ReadonlyArray("red", "green", "blue");
```

```
const roArray: ReadonlyArray<string> = ["red", "green", "blue"];
```

- `ReadonlyArray<Type>` is same as `readonly Type[]`.

- One last thing to note is that unlike the readonly property modifier, assignability isn’t bidirectional between regular Arrays and ReadonlyArrays.

```
let x: readonly string[] = [];
let y: string[] = [];

x = y;
y = x;
`The type 'readonly string[]' is 'readonly' and cannot be assigned to the mutable type 'string[]'.`
```

## Tuple Types:

- A tuple type is another sort of Array type that knows exactly how many elements it contains, and exactly which types it contains at specific positions.

```
let rgb : [number, number, number] = [255,122,154];
rgb[1] = 545;
console.log(rgb);

```

## we can also create custome array elements types:

- **create array type which has first two elements is string and boolean and followed any numbers of number type element?**
- `type customeArr = [string,boolean,...number[]]`

- same as `type StringNumberBooleans = [string, number, ...boolean[]];`
  `type StringBooleansNumber = [string, ...boolean[], number];`
  `type BooleansStringNumber = [...boolean[], string, number];`

## readonly Tuple Types

- One final note about tuple types - tuple types have readonly variants, and can be specified by sticking a readonly modifier in front of them - just like with array shorthand syntax.

```
function doSomething(pair: readonly [string, number]) {
// ...
}

```

- This is also important given that array literals with const assertions will be inferred with readonly tuple types.

```
let point = [3, 4] as const;

function distanceFromOrigin([x, y]: [number, number]) {
  return Math.sqrt(x ** 2 + y ** 2);
}

distanceFromOrigin(point); //  The type 'readonly [3, 4]' is 'readonly' and cannot be assigned to the mutable type '[number, number]'.
```

## Generic Classes

A generic class has a similar shape to a generic interface. Generic classes have a generic type parameter list in angle brackets (<>) following the name of the class.

```
class GenericNumber<NumType> {
  zeroValue: NumType;
  add: (x: NumType, y: NumType) => NumType;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function (x, y) {
  return x + y;
};

```

## Generic Constraints:

```
function loggingIdentity<Type>(arg: Type): Type {
  console.log(arg.length); //Property 'length' does not exist on type 'Type'.
  return arg;
}
```

- Instead of working with any and all types, we’d like to constrain this function to work with any and all types that also have the .length property.
- To do so, we’ll create an interface that describes our constraint. Here, we’ll create an interface that has a single .length property and then we’ll use this interface and the extends keyword to denote our constraint.

```
interface Lengthwise {
  length: number;
}

function loggingIdentity<Type extends Lengthwise>(arg: Type): Type {
  console.log(arg.length); // Now we know it has a .length property, so no more error
  return arg;
}
```

## Using Type Parameters in Generic Constraints

- You can declare a type parameter that is constrained by another type parameter.
- For example, here we’d like to get a property from an object given its name. We’d like to ensure that we’re not accidentally grabbing a property that does not exist on the obj, so we’ll place a constraint between the two types:

```
function getProperty<Type,Key extend keyof Type>(obj:Type,key:Key){
  return obj[key];
}
let x = {a:1,b:3}
getProperty(x,"a")
getProperty(x,"c") //gives error
```

## The keyof type operator:

- The keyof operator takes an object type and produces a string or numeric literal union of its keys. The following type P is the same type as “x” | “y”:

```

type Point = { x: number; y: number };
type P = keyof Point;

```

```
type Mapish = { [k: string]: boolean };
type M = keyof Mapish;
```

- Note that in this example, M is string | number — this is because JavaScript object keys are always coerced to a string, so `obj[0]` is always the same as `obj["0"]`.

## ReturnType<T>.

- It takes a function type and produces its return type:

```
type Predicate = (x: unknown) => boolean;
type K = ReturnType<Predicate>; // type K = boolean
```

```
function f() {
  return { x: 10, y: 3 };
}
type P = ReturnType<typeof f>; p is {x:number,y:number}
```

- Insted of using this `let shouldContinue: typeof msgbox("Are you sure you want to continue?");` we will use this `ReturnType<typeof msgbox>`

## Indexed Access Types:

- We can use an indexed access type to look up a specific property on another type.

```
type Person = { age: number; name: string; alive: boolean };
type Age = Person["age"]; // type Age = number
```

- The indexing type is itself a type, so we can use unions, keyof, or other types entirely:

```
type I1 = Person["age" | "name"];type I1 = string | number

type I2 = Person[keyof Person]; //type I2 = string | number | boolean

type AliveOrName = "alive" | "name";
type I3 = Person[AliveOrName]; //type I3 = string | boolean
```

### With array:

```
const MyArray = [
  { name: "Alice", age: 15 },
  { name: "Bob", age: 23 },
  { name: "Eve", age: 38 },
];

type Person = typeof MyArray[number];

---
type Person = {
    name: string;
    age: number;
  }
---

type Age = typeof MyArray[number]["age"];
//
Or
//
type Age = typeof MyArray[number]["age"];


```

```
const key = "age";
type Age = Person[key]; // Type 'key' cannot be used as an index type.
```

```
type key = "age";
type Age = Person[key];
```

## Conditional Types:

- Conditional types help describe the relation between the types of inputs and outputs.
- Syntax:

- **`SomeType extends OtherType ? TrueType : FalseType;`**

```
interface Animal {
  live(): void;
}
interface Dog extends Animal {
  woof(): void;
}

type Example1 = Dog extends Animal ? number : string;
// type Example1 = number

type Example2 = RegExp extends Animal ? number : string;
// type Example2 = string

```

**Another Example:**

```
interface IdLabel {
  id: number /* some fields */;
}
interface NameLabel {
  name: string /* other fields */;
}

function createLabel(id: number): IdLabel;
function createLabel(name: string): NameLabel;
function createLabel(nameOrId: string | number): IdLabel | NameLabel;
function createLabel(nameOrId: string | number): IdLabel | NameLabel {
  throw "unimplemented";
}
```

- insted of doing this we can use conditional types:

```
type NameOrId<T extends number | string> = T extends number
  ? IdLabel
  : NameLabel;
```

- We can then use that conditional type to simplify our overloads down to a single function with no overloads.

```
function createLabel<T extends number | string>(idOrName: T): NameOrId<T> {
  throw "unimplemented";
}
```

- More read documentation

## Flatten Type:

```
type Flatten<T> = T extends any[] ? T[number] : T;

// here T[number] which will takes that index's type.

// Extracts out the element type.
type Str = Flatten<string[]>;
//   ^?

// Leaves the type alone.
type Num = Flatten<number[]>;
//   ^?

type Bool = Flatten<boolean[]>;
//   ^?


```

- We can also define it using `infer` keyword.
- `type Flatten<Type> = Type extends Array<infer Item> ? Item : Type;`

## Distributive Conditional Types:

- When conditional types act on a generic type, they become distributive when given a union type.

```
type ToArr<Type> = Type extends any ? Type[] : never;
```

## Index Access Types:

- for example we have a interface with some property assosiated with types so if we have to access that property's value then we can use index access types, see below example:

```

type Person = {
age: number;
name: string;
alive: boolean
};
type Age = Person["age"];

// here the type of age is `number`

```

## Defining function in interface:

```

interface User2 {
readonly dbId: number
userId: number,
googleId?: string
// startTrail: () => string
startTrail(): string,
getCoupon (couponname: string, value: number):number
}
```

## Making one or more types of single array:

```
const data: number[] = [1,2,3,4] // only number
const data1: string[] = ["1","2","3","4"] // only string
const data2: number[] | string[] = ["1","2","3","4"] // either number or string
const data3: (number | string)[] = ["1",2,3,"4"] // both allowed number & string
```

## classes:

```

class Point {
x: number;
y: number;
}

const pt = new Point();
pt.x = 0;
pt.y = 0;

```

- here this will give error because we have declare but we did not have assign any value or we have not create any constructor for that. if we want to ignore this error then we can use `!` opearator it is Non-null Assertion Operator (Postfix`!`).

```

class Person {
id: number
name: string

      // constructor is a method which is called automaticaly whenever an object is instantiated from that class
      constructor(id: number, name: string) {
          this.id = id;
          this.name = name;
      }

}

const gunjan = new Person(1, 'Gunjan');
const jimit = new Person(2, 'jimit');

console.log(Gunjan, jimit);

```

## What are the access modifiers supported by TypeScript?

- TypeScript supports access modifiers public, private andprotected which determine the accessibility of a class member as given below:

- **Public** – All the members of the class, its child classes, and the instance of the class can access.
- **Protected** – All the members of the class and its child classes can access them. But the instance of the class can not access.
- **Private** – Only the members of the class can access them.

## Private and Public:

```

class Pizzas2{

toppings:string[] = [];

constructor(private name:string){}

    addTopps(topps:string) {
      this.toppings.push(topps);
    }

}

const pizo2 = new Pizzas2('doublecheez margerita');
pizo2.addTopps("amul cheeze");
pizo2.addTopps("go cheeze");
console.log(pizo2);

```

## getter and setter :

- `get`: for get any private property.

- `set`: for set any private property. Setter has no return type.

```

class User {

    protected _courseCount = 1

    readonly city: string = "Jaipur"
    constructor(
        public email: string,
        public name: string,
        // private userId: string
        ){
    }
    private deleteToken(){
        console.log("Token deleted");

    }

    get getAppleEmail(): string{
        return `apple${this.email}`
    }

    get courseCount(): number {
        return this._courseCount
    }

    set courseCount(courseNum) {
        if (courseNum <= 1) {
            throw new Error("Course count should be more than 1")
        }
        this._courseCount = courseNum
    }

}

class SubUser extends User {
isFamily: boolean = true
changeCourseCount(){
this.\_courseCount = 4
}
}

const gunjan = new User("h@h.com","gunjan")

```

## abstract classes:

- abstract classes can not read object of it's own but they help to define class who are inheriting them .
- abstract class can not be instantiated.

```

abstract class Pizzas2{

toppings:string[] = [];

constructor(private name:string){}

    addTopps(topps:string) {
      this.toppings.push(topps);
    }

}

const pizo2 = new Pizzas2('doublecheez margerita'); // give error that can not create instance of an abstract class.
pizo2.addTopps("amul cheeze");
pizo2.addTopps("go cheeze");
console.log(pizo2);

// and if we extend that class and create an instance so it will create an instance.

class pizzas3 extends Pizzas2{

}

const pizo2 = new pizzas3 ('doublecheez margerita');
pizo2.addTopps("amul cheeze");
pizo2.addTopps("go cheeze");
console.log(pizo2);

```

## static keyword:

- we can access the member of class without creating the instance of class using static key word.
- Example:

```

class coupon{
data = ["Dasdfasd","Fdsfer"];
}

console.log(coupon.data); //gives error because we had not create any instance

//
class coupon{
static data = ["Dasdfasd","Fdsfer"];
}

console.log(coupon.data); // now it is accessible

```

## singleton pattern :

- In oops this patterns ensuring that an instance is only of the single class only.

## Symbol Type:

- symbol type represents a unique and immutable data type.

**Usage**:

- Symbols are often used as keys for object properties to ensure their uniqueness and to prevent unintended property name collisions.

**Syntax:**

- Symbols are created using the Symbol() function, which returns a new unique symbol value each time it is called.

Ex:

```
const mySymbol = Symbol('myProperty');
const secondSymbol = Symbol('myProperty');

const obj = {
  [mySymbol]: 'Value assigned to symbol key'
};

console.log(secondSymbol === mySymbol);
```

## Mapped Types:

- Mapped types are a feature in TypeScript that allow you to transform and manipulate the properties of an existing type to create a new type.
- They provide a way to programmatically iterate over the properties of a type and apply transformations or constraints to each property.

- **There are several mapped type modifiers available in TypeScript:**

```
type Person = {
  name: string;
  age: number;
  email: string;
};
type PartialPerson = Partial<Person>; // All properties of Person become optional
type ReadonlyPerson = Readonly<Person>; // All properties of Person become read-only
type PickPerson = Pick<Person, 'name' | 'age'>; // Only 'name' and 'age' properties are selected
type RecordPerson = Record<'id' | 'name', string>; // Object with 'id' and 'name' properties of type string
```

## Record Type Example:

```
type Fruit = 'apple' | 'banana' | 'orange';
type Inventory = Record<Fruit | "mango", number>;

const fruitInventory: Inventory = {
apple: 10,
banana: 5,
orange: 3,
mango: 15,
};

console.log(fruitInventory.apple); // Output: 10
console.log(fruitInventory.banana); // Output: 5
console.log(fruitInventory.orange); // Output: 3
console.log(fruitInventory.mango);
```

## Explain Decorators in TypeScript.

- A Decorator is a special kind of declaration that can be applied to classes, methods, accessor, property, or parameter. Decorators are functions that are prefixed @expression symbol, where expression must evaluate to a function that will be called at runtime

## The in Operator Narrowing:

```

interface User {
name: string,
email?: string
}

interface Admin{
name: string,
email: string,
isAdmin: boolean
}

// give error
// function isAdminAccount1(account: User | Admin){
// return account.isAdmin
// }

function isAdminAccount(account: User | Admin) {
  if ("isAdmin" in account) {
    return account.isAdmin
  }
    return account;
}

const acc: User | Admin = {name:"gunjan", isAdmin:false}
console.log(isAdminAccount(acc))

```

## Descriminated Unions:

```
interface Square {
  kind: 'square';
  size: number;
}

interface Rectangle {
  kind: 'rectangle';
  width: number;
  height: number;
}

interface Circle {
  kind: 'circle';
  radius: number;
}

type Shape = Square | Rectangle | Circle;

function calculateArea(shape: Shape): number {
  switch (shape.kind) {
    case 'square':
      return shape.size * shape.size;
    case 'rectangle':
      return shape.width * shape.height;
    case 'circle':
      return Math.PI * shape.radius * shape.radius;
    default:
      throw new Error('Invalid shape');
  }
}

const square: Shape = { kind: 'square', size: 5 };
console.log(calculateArea(square));  // Output: 25

const circle: Shape = { kind: 'circle', radius: 3 };
console.log(calculateArea(circle));  // Output: 28.274333882308138


```

### What is Namespace and how to declare it?

- A namespace is a way to organize and encapsulate code by grouping related functionalities under a single name. It helps in avoiding naming conflicts and provides a modular structure to your codebase.
- Namespaces are particularly useful when working with large-scale applications or when integrating with external libraries.
- The namespace is used to group functionalities logically. To enable a single or a group of linked functionalities, a namespace can include interfaces, classes, functions, and variables.
- The namespace keyword, followed by the namespace name, can be used to construct a namespace.

Example:

```
namespace Shapes {
  export interface Shape {
    name: string;
    area(): number;
  }

  export class Circle implements Shape {
    constructor(public name: string, public radius: number) {}
    area(): number {
      return Math.PI * this.radius ** 2;
    }
  }
}
```

- In app.ts:

```
import Shapes = Shapes.Shapes;

const circle = new Shapes.Circle('Circle 1', 5);
console.log(circle.area()); // Output: 78.53981633974483
```

## Declaration Merging:

- Declaration merging is a feature in TypeScript that allows you to combine multiple declarations of the same entity (interfaces, classes, functions, enums, etc.) into a single definition.
- It enables you to extend or modify existing types by adding or modifying members, without the need for explicitly creating a new type that duplicates the original definition.

### Types:

1. Merging Interfaces:
2. Merging Namespaces:

Example:

```
namespace Animals {
  export class Zebra {}
}
namespace Animals {
  export interface Legged {
    numberOfLegs: number;
  }
  export class Dog {}
}
```

## DOM Manipulation:

**Accessing dom elements**

```

const form = document.querySelector('.class_name') as HTMLFormElement;
const type = document.querySelector('#type') as HTMLSelectElement;
const tofrom = document.querySelector('#tofrom') as HTML InputElement;
const details = document.querySelector('#details') as HTML InputElement
const amount = document.querySelector('#amount') as HTMLInputElement;

```

- here for amount it will take the input as a string so we can use `amount.valueAsNumber`.

## Difference between `children` and `childNodes`:

- **children** : if we can access child element using `div.children;` will give `HTMLCollection` contain only html element.
- **childNodes** : if we can access child element using `div.childNodes;` will give `NodeList` contain html element with other text also which has not wrap in any html element.

- Example:

```

<div>
  <p>Hello, World</p>
  TypeScript
</div>;
const div = document.getElementsByTagName("div")[0];
div.children;
// HTMLCollection(1) [p]
div.childNodes;
// NodeList(2) [p, text]

```
