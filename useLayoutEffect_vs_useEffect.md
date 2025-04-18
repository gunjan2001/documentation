## useLayoutEffect vs useEffect:

| Feature                     | useEffect                                                                                   | useLayoutEffect                                                                                   |
|-----------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| **Execution**               | Runs asynchronously after component render and after the DOM has been updated and painted. | Runs synchronously after render but before the browser paints (before DOM update is visible).   |
| **Dependencies Array**      | Optional; specifies dependencies to control when the effect runs.                          | Optional; also accepts a dependencies array, but its behavior is more synchronous.                  |
| **Can be used to**          | Perform side effects like fetching data, API calls, or updating the DOM after paint.       | Perform side effects related to layout, like measuring or setting element position/size.        |
| **Cleanup Function**        | Supports cleanup on unmount and when dependencies change.                                  | Supports cleanup on unmount and when dependencies change.                                       |
| **Can cause performance problems** | Yes, if it is used to perform side effects that do not need to be executed synchronously. | No, because it is executed synchronously.
