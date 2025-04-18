## useLayoutEffect vs useEffect:

| Feature                     | useEffect                                                                                   | useLayoutEffect                                                                                   |
|-----------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| **Execution**               | Runs asynchronously after component render and after the DOM has been updated and painted. | Runs synchronously after render but before the browser paints (before DOM update is visible).   |
| **Dependencies Array**      | Optional; specifies dependencies to control when the effect runs.                          | Optional; same usage as useEffect, but effect runs synchronously before paint.                  |
| **Can be used to**          | Perform side effects like fetching data, API calls, or updating the DOM after paint.       | Perform side effects related to layout, like measuring or setting element position/size.        |
| **Cleanup Function**        | Supports cleanup on unmount and when dependencies change.                                  | Supports cleanup on unmount and when dependencies change.                                       |
| **Can cause performance problems** | Yes, if used for side effects that should run synchronously or affect layout, can cause visual flicker. | Yes, if overused or contains heavy computations, can block painting and make UI sluggish.       |
