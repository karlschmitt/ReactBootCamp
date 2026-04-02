In React, **props** is short for **“properties.”**

They are how you **pass data from one component to another**—typically from a parent component to a child.

---

## 🧩 Simple analogy

Think of props like **parameters in a Java method**:

```java
String greet(String name) {
    return "Hello " + name;
}
```

👉 `name` is input

In React:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

👉 `props.name` is the input

---

## 📦 How props work

### 1. Pass props (parent → child)

```jsx
<Welcome name="Karl" />
```

### 2. Receive props

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

---

## ✨ Cleaner syntax (destructuring)

Instead of `props.name`, you’ll usually see:

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}</h1>;
}
```

---

## 🔁 Key characteristics

* ✅ **Read-only** → a component should NOT modify its props
* ✅ Passed **top-down** (parent → child)
* ✅ Can be **any type**: string, number, object, function, even other components

---

## 🧠 Example with multiple props

```jsx
function User({ name, age }) {
  return (
    <p>
      {name} is {age} years old
    </p>
  );
}
```

Usage:

```jsx
<User name="Karl" age={30} />
```

---

## 🔥 Props vs State (quick contrast)

| Props                  | State                    |
| ---------------------- | ------------------------ |
| Passed from parent     | Managed inside component |
| Read-only              | Can be changed           |
| External configuration | Internal data            |

---

## ⚡ One-line definition

> Props are inputs to a React component, used to pass data from a parent to a child.

---

If you want, I can show you a **real-world example (like a product card or API data flow)** so this becomes very concrete.

