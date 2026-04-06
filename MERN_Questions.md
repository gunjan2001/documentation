# Javascript:

## Temporal Dead Zone (TDZ):
- The Temporal Dead Zone (TDZ) is the period in JavaScript where a variable declared with let or const is in a "dead zone" and cannot be accessed. This zone starts at the beginning of a block's scope (like a function or curly braces {...}) and ends when the variable is actually declared and initialized. During this time, the variable exists in memory but is uninitialized, so any attempt to access it will result in a ReferenceError.

```
function exampleFunction() {
  // This is the start of the Temporal Dead Zone for 'myVariable'
  // console.log(myVariable); // This would throw a ReferenceError

  let myVariable = 10; // The TDZ ends here
  console.log(myVariable); // This will work correctly
}

exampleFunction();

```
**Benefits:**

- The TDZ helps prevent bugs by stopping developers from using variables before they are properly initialized.
- It makes code more predictable and easier to understand.


# ReactJs:

## What is the Virtual DOM in React? Why is it useful?

**STRONG ANSWER**: "The Virtual DOM is a lightweight JavaScript representation of the actual DOM. Here's how it works:

- State changes trigger React to create a new Virtual DOM tree
- Diffing algorithm compares new Virtual DOM with previous one
- Reconciliation identifies minimal changes needed
- Batch update applies only necessary changes to real DOM

Benefits:
 
- **Performance**: Only updates changed elements instead of re-rendering entire page
- **Efficiency**: Batches multiple updates together

---

## Explain useState and useEffect hooks.

"**useState**":
- Creates state variables in functional components.
- First value is the state
- Second value is the setter function
- React re-renders when state changes

**useEffect**: 
- Handles side effects like API calls, subscriptions, timers.
- Runs after render
- Dependency array controls when it runs
- Empty array [] = runs once on mount
- With dependencies = runs when they change
- Return function = cleanup

## Explain async/await vs Promises:

- Both handle asynchronous operations, but async/await is syntactic sugar over Promises.

**Advantages of async/await:**

1. Readability: Looks like synchronous code
2. Error Handling: Use try-catch instead of .catch()
3. Debugging: Easier to set breakpoints
4. Control Flow: Simpler conditional logic

**When I used each:**

- Async/await: API calls in controllers and components
- Promises: Axios requests, as axios returns promises

**Important: async functions always return a Promise, and await only works inside async functions.**

## What is the most challenging task you handled in your project?
- 
---
## Is JavaScript tightly coupled or loosely coupled?
- 
---
## 7. How does Redux work, from installation to usage in a project?
- 
---
## 9. What is the difference between bind and apply in JavaScript?
- 
---
## 10. What has been your experience with useCallback and useMemo in real projects?
- 
---
## 11. What is the role of the dependency array in useEffect?
- 
---

# Database:

## What is MongoDB and why use it over SQL databases?

MongoDB is a NoSQL document database that stores data in JSON-like documents (BSON format).

Advantages:

- Flexible Schema: Products can have varying fields without migrations
- JSON-like Structure: Perfect match for JavaScript/Node.js
- Easy Scaling: Horizontal scaling through sharding
- Fast Reads: Embedded documents reduce joins
- Array Support: Categories array is native, no junction table needed

When to use SQL instead:

- Complex relationships and joins
- ACID transaction requirements
- Financial data needing strict consistency
- Structured data that rarely changes

## What is Mongoose and why do we need it?

STRONG ANSWER: "Mongoose is an ODM (Object Data Modeling) library for MongoDB and Node.js. 

**Key Features:**

1. Schema Definition: Structure for documents
2. Validation: Built-in and custom validators
3. Middleware: Pre/post hooks for operations
4. Type Casting: Automatic type conversion
5. Queries: Powerful query builder
6. Population: Joins between collections

Why we need it:
- Native MongoDB driver is low-level. Mongoose adds:

- Structure and validation
- Better error handling
- Model methods
- Virtual properties
- Plugins

## what is collections in the MongoDB?
- Collections is the set of documents.
- In simple terms collection is our table name, and data which was stored in this named as documents.

## What is the term "indexing" in the Mongodb?
- In mongodb, indexing plays a crucial role in optimizing the query resolutions.
- Essentially, an index stores a compact portion of the dataset in a format, conductive to efficient traversal.

## How can you use the like operator to query MongoDB?

- In MongoDB, you can implement a functionality similar to the "like" operator by employing regular expressions with the `$regex` operator in the `$match` pipeline stage of an aggregation query. For instance, the subsequent query identifies documents in which the "name" field commences with "Nick":

```
db.myCollection.aggregate([
  { $match: { name: { $regex: /^Nick/ } } }
])
```

## What is CORS and why did you use it?

- CORS (Cross-Origin Resource Sharing) is a security mechanism that allows controlled access to resources from different origins.

The Problem:
- By default, browsers block requests from one origin (domain/port) to another. My setup:

- Frontend: http://localhost:3000
- Backend: http://localhost:5000 Without CORS, the browser blocks API calls.

Solution:
```
app.use(cors());

In production, I would restrict it:
app.use(cors({
  origin: 'https://myapp.com',
  credentials: true
}));
```

**How it works:**

- Browser sends preflight OPTIONS request
- Server responds with allowed origins/methods
- Browser allows/blocks actual request

# NodeJs:

## What are streams in Nodejs?
- A stream is a sequence of the data that is being moved from one point to another point over time.
- In streams the data is arrived in the chunks and we can watch the chunks and the rest of the data arrives over time.
- It prevents unnecessary downloads and memory usage.
- Ex: Watching a youtube video. here data arrives in the chunks not fully download the video.

## Buffers:
- Nodejs cannot control at which data arrives in the stream.
- It can only decide when is the right time to send the data for processing.
- If there is data already processed or too little data to process, Node puts the arriving data in the buffer.
- It is an intentionally small area that node maintains in the runtime to process a stream of data.


# Behavioral Questions

## How do you handle tight deadlines?
