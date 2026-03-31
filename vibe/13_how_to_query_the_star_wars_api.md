To query the **Star Wars API (SWAPI)** from React, you basically:

1. Call the API
2. Store the result in state
3. Render it

I’ll show you the **clean, modern way** (fits perfectly with your Vite + React setup).

---

# 🌐 1. The API you’ll use

The Star Wars API endpoint:

* [https://swapi.dev/api/people/](https://swapi.dev/api/people/)

This returns characters like Luke Skywalker, Darth Vader, etc.

---

# ⚛️ 2. Simple React example (with `fetch`)

```jsx
import { useEffect, useState } from "react";

function App() {
  const [people, setPeople] = useState([]);

  useEffect(() => {
    fetch("https://swapi.dev/api/people/")
      .then(res => res.json())
      .then(data => setPeople(data.results));
  }, []);

  return (
    <div>
      <h1>Star Wars Characters</h1>
      <ul>
        {people.map((person) => (
          <li key={person.name}>{person.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

---

# 🔁 What’s happening here

* `useEffect(...)` → runs once when component loads
* `fetch(...)` → calls the API
* `setPeople(...)` → stores the data
* `map(...)` → renders the list

---

# ⚡ 3. Same thing with Axios (cleaner)

Using Axios:

```jsx
import { useEffect, useState } from "react";
import axios from "axios";

function App() {
  const [people, setPeople] = useState([]);

  useEffect(() => {
    axios.get("https://swapi.dev/api/people/")
      .then(res => setPeople(res.data.results));
  }, []);

  return (
    <ul>
      {people.map(p => (
        <li key={p.name}>{p.name}</li>
      ))}
    </ul>
  );
}
```

---

# 🧠 4. Better version (async/await)

```jsx
import { useEffect, useState } from "react";
import axios from "axios";

function App() {
  const [people, setPeople] = useState([]);

  useEffect(() => {
    async function loadData() {
      const res = await axios.get("https://swapi.dev/api/people/");
      setPeople(res.data.results);
    }

    loadData();
  }, []);

  return (
    <ul>
      {people.map(p => (
        <li key={p.name}>{p.name}</li>
      ))}
    </ul>
  );
}
```

---

# 🧱 5. Add loading + error handling (real-world)

```jsx
function App() {
  const [people, setPeople] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("https://swapi.dev/api/people/")
      .then(res => res.json())
      .then(data => {
        setPeople(data.results);
        setLoading(false);
      });
  }, []);

  if (loading) return <p>Loading...</p>;

  return (
    <ul>
      {people.map(p => <li key={p.name}>{p.name}</li>)}
    </ul>
  );
}
```

---

# 🧭 6. What you should try next

To really learn this, extend it:

* Show more fields (height, birth year)
* Add a **search input**
* Add **pagination** (`/people/?page=2`)
* Click a character → show details

---

# ⚡ One-line takeaway

> Use `useEffect` to call the API, store the result in `useState`, and render it with `map()`.

---

If you want, I can help you turn this into a **clean mini app (list + detail view + routing)**—that’s the point where React really clicks.

