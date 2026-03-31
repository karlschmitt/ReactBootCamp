`useState` is the most fundamental Hook in React. It allows you to add **state** to a functional component—meaning it lets the component "remember" data (like a counter, a form input, or a loading status) between re-renders.

### 1. How it works (The Mechanism)
In standard JavaScript, variables inside a function are "reset" every time the function runs. Since a React component is just a function that runs every time something changes, a normal variable like `let count = 0` would be reset to `0` every time React re-renders the UI.

`useState` tells React: *"Hey, keep this piece of data in your internal memory. Even if you re-run this function, give me back the latest value."*

**The Syntax:**
```javascript
const [state, setState] = useState(initialValue);
```
- **`state`**: The current value of the data.
- **`setState`**: A function you call to update the value.
- **`initialValue`**: The value you want the state to start with (only used on the first render).

### 2. Why do we need the `setState` function?
You cannot update the state by doing `state = newValue`. React wouldn't know that the data changed, so it wouldn't update the screen. When you use the **setter function** (`setState`), it does two things:
1. It updates the value in React's memory.
2. It triggers a **re-render**, telling React to update the UI on the screen.

---

### 3. Practical Example: A Simple Counter
This is the "Hello World" of React state. Every time you click the button, the `setCount` function runs, the value increases, and React automatically updates the text on the screen.

```jsx
import React, { useState } from 'react';

function Counter() {
  // 1. Declare a state variable called "count", initialized to 0
  const [count, setCount] = useState(0);

  return (
    <div style={{ padding: '20px', textAlign: 'center' }}>
      <p>You clicked {count} times</p>
      
      {/* 2. Update the state when the button is clicked */}
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
      
      <button onClick={() => setCount(count - 1)}>
        Decrease
      </button>
    </div>
  );
}

export default Counter;
```

---

### 4. Important "Rules" to Remember
*   **Top Level Only:** You must call `useState` at the very top of your function. Never put it inside an `if` statement, a loop, or a nested function. React relies on the **order** of these calls to know which state is which.
*   **Asynchronous Nature:** If you call `setCount(count + 1)` and then immediately `console.log(count)`, the log will still show the **old** value. The new value is only available in the *next* render.
*   **Replacing, not Merging:** If your state is an object (e.g., `{ name: 'John', age: 30 }`) and you want to update just the name, you must spread the old state:
    ```javascript
    setUser({ ...user, name: 'Jane' });
    ```
    If you just did `setUser({ name: 'Jane' })`, the `age` property would be deleted.
