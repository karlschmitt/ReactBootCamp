React: What is JSX and what is a component?

In React, **JSX** and **Components** are the two fundamental building blocks that work together to create a user interface.

---

### 1. What is JSX?
**JSX** stands for **JavaScript XML**. It is a syntax extension for JavaScript that allows you to write HTML-like code directly inside your JavaScript files.

*   **The Look:** It looks like HTML (e.g., `<h1>Hello World</h1>`), but it is actually JavaScript.
*   **The Logic:** Because it is JavaScript, you can embed logic inside it. By using curly braces `{}`, you can inject variables, function calls, or math directly into your markup.
*   **The "Magic":** Browsers cannot read JSX directly. Tools like **Babel** "transpile" (convert) your JSX into regular JavaScript function calls (`React.createElement`) before the browser runs it.

**Example of JSX:**
```javascript
const name = "Alice";
const element = <h1>Hello, {name}!</h1>; // JSX with a variable
```

---

### 2. What is a Component?
A **Component** is a self-contained, reusable piece of code that represents a part of the UI. Think of components like **LEGO bricks**: you build small pieces (like a Button, a SearchBar, or a UserProfile) and then snap them together to create a full application.

*   **Purpose:** To split the UI into independent, reusable pieces so you can think about each piece in isolation.
*   **Functionality:** A component is essentially a JavaScript function that **returns JSX**.
*   **Naming Rule:** Component names must always start with a **Capital Letter** (e.g., `<MyComponent />`). If it starts with a lowercase letter (e.g., `<div />`), React treats it as a standard HTML tag.

There are two types of components:
1.  **Function Components (Modern Standard):** Plain JavaScript functions.
2.  **Class Components (Older):** ES6 classes. (These are mostly replaced by Function Components + Hooks in modern React).

---

### 3. How they work together
A Component is the **"Factory"**, and JSX is the **"Blueprint"** it produces.

**Example:**
```javascript
// This is a Component (the Factory)
function WelcomeMessage() {
  const timeOfDay = "morning";

  // This is JSX (the Blueprint)
  return (
    <div className="container">
      <h1>Good {timeOfDay}!</h1>
      <p>Welcome to our React app.</p>
    </div>
  );
}

// You use the component like a custom HTML tag:
// <WelcomeMessage />
```

### Summary Comparison

| Feature | JSX | Component |
| :--- | :--- | :--- |
| **What is it?** | A syntax (HTML-in-JS). | A piece of the UI (A JS function). |
| **Role** | Describes *what* the UI looks like. | Describes *how* the UI behaves and stays organized. |
| **Result** | Becomes a React Element. | Returns JSX to be rendered. |
| **Analogy** | The blueprint for a wall. | The bricklayer who builds the wall. |
