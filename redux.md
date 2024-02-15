## What is Redux?
- Redux is an open-source library made using the scripting language JavaScript. Redux's primary use lies in managing and centralizing application state and it is usually used along with JavaScript libraries
- Redux is very small in size (around 2 kilobytes) and has no dependencies.

## What is Flux?
- Flux is an application design paradigm just like the Model View Controller design pattern. Flux is nothing but a new kind of architecture that complements React and the concept of Unidirectional Data Flow.

## Difference between Redux and Flux
![image](https://github.com/gunjan2001/documentation/assets/85817658/d1d25730-2aca-4e3e-911f-fd21d3714a04)

## What is Redux in React js?
Redux in React is the official React binding for Redux which allows the components in React to read data from a Redux Store, and dispatch Actions to the Store for updating the data.

## State the core principles of Redux.
The core principles of Redux are as follows:

- **Single source of truth**: The global state of our application is always put away in an object tree inside one store.
- **The state is read-only**: The only way to change the state of our application is by emitting an action, an object explaining what has happened.
- **Changes are made with pure functions**: This principle means that in order to define how the state tree is being transformed by the actions, we have to write pure reducers.

## What are the advantages of using Redux?
- Some of the advantages of using Redux are as follows:

- Redux provides extremely easy state transfer between the components.
- The states are always predictable in Redux and its maintenance is relatively easy.
- Debugging and testing code in Redux is simple through logging behaviour and status.
- Redux provides great performance. It might occur to us that keeping the application's state global would result in bad performance. However, usually, that is not the case as 
- React Redux implements a lot of performance optimizations internally so that our own connected component only re-renders when it actually needs to.
- Redux also offers state persistence by storing the application's state to local storage and restoring it after a refresh.

## What do you understand about Redux Toolkit?
- Redux Toolkit is Redux's official, opinionated, batteries included toolset for efficient Redux development. It also consists of the most widely used Redux add-ons, for instance, Redux Thunk for asynchronous logic

## What do you understand by an action in Redux's architecture?
- In the Redux architecture, actions are nothing but the plain JavaScript objects which contain a type field.
- Actions contain only a tiny bit of information that is required to mention what has happened.

## What are constants in Redux?
- Constants in Redux help us in easily finding all the usages of a particular functionality across our entire project

## What is the mental model of redux saga?
- Redux Saga functions as a separate thread in our programme which is solely responsible for side effects. Redux Saga is a redux middleware. In other words, it means that it can be started, paused, and aborted from the main application using standard Redux actions,

## Name all the Redux Store methods.
All the Redux Store Methods are as follows:

getState()
subscribe(listener)
dispatch(action)
replaceReducer(nextReducer)

## What do you understand about the Redux Saga?
- Redux Saga is a middleware library that can be useful for allowing a Redux store to interact with the resources outside of itself in an asynchronous manner, for example, making HTTP requests to external services, accessing browser storage, executing Input/Output operations and many more. These operations are also called side effects.

