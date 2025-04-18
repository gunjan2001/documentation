## **Fetch:**
- Built-in browser API, no installation needed.
- works with modern browsers.
- Introduce in ES6
- Data must be stringified using JSON.stringify().
- Automatically parses JSON responses.	
- This method returns a Promise that resolves with the response to the request.
- The .then() method -> handles the successful response
- The .catch() method -> handles any errors that occur during the request.
- **Syntax:**
```
fetch('url-to-resource')
  .then(response => {
    // Handle the response here
  })
  .catch(error => {
    // Handle errors here
  });
```

## **Axios:**
- Third-party library that needs installation..
- Works with both Node.js and browsers.
- Introduce in ES6
- Sends JavaScript objects directly.
- You must call .json() to parse the response.
- 
- extra features:
    - **request/response interception**,
    - **error handling**
    - **support for cancellation**.
- **Syntax:**
```
axios.get('url')
  .then((response) => {
    // Code for handling the response
  })
  .catch((error) => {
    // Code for handling the error
  })
```

## **When to Use Fetch**
- Fetch is a great choice if you prefer a lightweight, native solution without the need for additional libraries.

**Native Solution**: Fetch is built into modern browsers, so no installation is needed.
**Lightweight**: If you prefer minimal dependencies, Fetch keeps your codebase slim.
**Custom Error Handling & Parsing**: You’ll need to manually handle error catching and JSON parsing, but this gives more control.
