## 1. Call, Apply, Bind → Difference
- JavaScript provides the call(), apply(), and bind() methods for setting the "this" context within a function.
- These methods are especially useful when working with object-oriented code or handling different function contexts.

### Difference:
- The core difference is **when the function is executed and how arguments are passed**.

*   **`call()`**
    *   **Execution:** Executes the function **immediately**.
    *   **Arguments:** Takes **individual arguments** (comma-separated) after the first `this` argument.
    *   **Use Case:** Ideal for immediate execution when arguments are known individually.
    *   **Syntax**:
    ```
    call(objectInstance)
    call(objectInstance, arg1, /* …, */ argN)
    ```

*   **`apply()`**
    *   **Execution:** Executes the function **immediately**.
    *   **Arguments:** Takes a single **array** of arguments after the first `this` argument.
    *   **Use Case:** Ideal for immediate execution when arguments are already grouped in an array or the number of arguments is dynamic.
    *   **Syntax**:
    ```
    apply(objectInstance)
    apply(objectInstance, argsArray)
    ```

*   **`bind()`**
    *   **Execution:** **Does not** execute immediately. It returns a **new function** with the context permanently bound.
    *   **Arguments:** Can take individual arguments when bound, and more arguments when the new function is finally called.
    *   **Use Case:** Ideal for scenarios where the function needs to be passed as a callback or executed later (e.g., event handlers).
    *   **Syntax**:
    ```
    bind(thisArg)
    bind(thisArg, arg1, arg2, /* …, */ argN)
    ```
