In React, `useState` is a **Hook** that lets a functional component **store and update state (data that changes over time)**.

---

## 🧠 What `useState` does

* Adds **state** to a functional component
* Returns **two things**:

  1. The current state value
  2. A function to update that value
* When you update the state → React **re-renders** the component automatically

---

## ✨ Basic Syntax

```javascript
const [state, setState] = useState(initialValue);
```

* `state` → current value
* `setState` → function to update it
* `initialValue` → starting value

---

## 🔢 Simple Example: Counter

```javascript
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Current count: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default Counter;
```

---

## 🔍 What happens here?

1. `useState(0)` → initializes `count` with `0`
2. Clicking the button calls `setCount(count + 1)`
3. React updates `count`
4. Component re-renders → UI shows new value

---

## 💡 Another Example: Input Field

```javascript
import { useState } from "react";

function NameInput() {
  const [name, setName] = useState("");

  return (
    <div>
      <input
        value={name}
        onChange={(e) => setName(e.target.value)}
        placeholder="Enter your name"
      />
      <p>Hello, {name}!</p>
    </div>
  );
}
```

👉 Here, `useState` keeps track of what the user types.

---

## ⚠️ Important Notes

* State updates are **asynchronous**
* You should **never modify state directly**

  ```javascript
  // ❌ Wrong
  count = count + 1;

  // ✅ Correct
  setCount(count + 1);
  ```
* You can have **multiple `useState` calls** in one component

---

If you want, I can show you:

* how `useState` works under the hood
* or how it compares to class-based `setState`
* or build a small real project using it (like a todo app)

