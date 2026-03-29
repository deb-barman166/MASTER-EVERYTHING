# ⚛️ React — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Hook, Pattern, Secret & Hidden Power

> 📘 **The most complete React guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing React to **thinking** in React.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every hook, pattern, performance technique, hidden secret, and architectural insight that separates a 0.01% React developer from the rest.

---

## Table of Contents

1. [🧠 What is React?](#1-what-is-react-super-simple)
2. [🌍 Why React Exists & Dominates](#2-why-react-exists--dominates)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete Hooks System Breakdown](#4-complete-hooks-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice Projects](#6-hands-on-practice-projects)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [💀 0.01% Hidden Secrets](#10-001-hidden-secrets-ultra-elite)
11. [🗺️ Complete Roadmap](#11-complete-roadmap)
12. [🧩 Bonus Deep Insights](#12-bonus-deep-insights)
13. [📌 Summary & Cheat Sheet](#13-summary-quick-revision--cheat-sheet)

---

## 🧠 1. What is React? (Super Simple)

### The 12-Year-Old Explanation

Imagine you're building a LEGO city. Instead of building every building, road, and park from scratch each time, you create **reusable LEGO kits** — a "House Kit," a "Shop Kit," a "Traffic Light Kit." Whenever you need a house anywhere in the city, you just use your House Kit.

**React is a system for building websites using reusable pieces called components.** Instead of writing the same button HTML five different times, you build one `Button` component and use it everywhere. When you update the Button component, every button on your site updates automatically.

React was created by **Jordan Walke** at Facebook in 2011 and open-sourced in 2013. It was born from the pain of building Facebook's News Feed — a page where hundreds of data changes happened per second. React solved this by introducing a smart system where only the parts of the page that actually changed get updated, rather than reloading the entire page.

### Real-Life Analogy

💡 **Think of it like this:**
A traditional website is like painting a mural on a wall. Every time something changes — a new notification, a new message — you repaint the entire wall. It's slow, wasteful, and the wall flickers every time.

React is like having a digital display board with individual tiles. Each tile knows exactly what it should show. When new data arrives, only the changed tiles update. No flickering. No repainting. Just fast, targeted updates.

### One-Line Definition

> **React** is a JavaScript library for building user interfaces through composable, reusable components — managing how UI updates efficiently in response to changing data.

---

## 🌍 2. Why React Exists & Dominates

### The Problem It Solved

Before React, building dynamic UIs meant directly manipulating the DOM (the HTML structure) with JavaScript. This caused three massive problems:

1. **It was slow** — Every data change required scanning and updating the real DOM, which is expensive.
2. **It was unpredictable** — State scattered across event handlers and global variables caused bugs that were nearly impossible to track.
3. **It didn't scale** — Adding one feature often broke three others. There was no clean way to isolate UI logic.

React solved all three: a **component model** for isolation, a **virtual DOM** for performance, and **one-directional data flow** for predictability.

### Where React Is Used Today

| Company / Domain          | How React Is Used                                                    |
|---------------------------|----------------------------------------------------------------------|
| Meta (Facebook/Instagram) | The original birthplace — billion-user scale UIs                     |
| Netflix                   | Content browsing, account management, dashboard                      |
| Airbnb                    | Listing pages, booking flow, host dashboard                          |
| Uber                      | Driver and rider web apps                                            |
| Notion                    | The entire collaborative document editor                             |
| Linear, Vercel, Supabase  | Modern SaaS developer tools                                          |
| Discord (web)             | Real-time chat and server management                                 |
| WhatsApp Web              | Full messaging interface rebuilt in React                            |
| OpenAI ChatGPT            | The entire chat interface                                            |
| Your next job             | 80%+ of frontend job listings require React                          |

### Why YOU Should Learn It Deeply

1. **Most demanded frontend skill globally** — React appears in more job listings than any other UI framework. Period.
2. **Ecosystem multiplier** — Next.js, React Native, Remix, React Query, Zustand — mastering React unlocks an entire universe of tools.
3. **AI tools build React** — GitHub Copilot, v0, Claude — all generate React code. You need to understand it to evaluate and edit AI output.
4. **Transferable mental models** — Thinking in components, state, and effects transfers to Vue, Svelte, Angular, and beyond.
5. **Full-stack with Next.js** — React + Server Components + Server Actions = full-stack JavaScript in one framework.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: JSX — JavaScript + HTML Together

JSX is the syntax that lets you write HTML-like code inside JavaScript. It looks like HTML but IS JavaScript — it compiles to `React.createElement()` calls.

```jsx
// JSX:
const element = <h1 className="title">Hello, Aryan!</h1>;

// What it actually compiles to:
const element = React.createElement("h1", { className: "title" }, "Hello, Aryan!");

// JSX rules:
// 1. Every element must be closed (self-closing or with closing tag):
const img = <img src="photo.jpg" alt="Me" />;    // ✅ Self-closing

// 2. Use className instead of class (class is reserved in JS):
const div = <div className="container">...</div>; // ✅

// 3. Use camelCase for HTML attributes:
const input = <input type="text" onChange={fn} tabIndex={1} />;
// htmlFor instead of for: <label htmlFor="email">

// 4. One root element — wrap siblings in a Fragment:
// ❌ Wrong:
// return <h1>Title</h1><p>Subtitle</p>;

// ✅ Right — Fragment (no DOM element added):
return (
  <>
    <h1>Title</h1>
    <p>Subtitle</p>
  </>
);

// Long form Fragment (when you need a key):
return (
  <React.Fragment key={item.id}>
    <h1>{item.title}</h1>
  </React.Fragment>
);

// 5. Expressions in JSX use {} — not template literals:
const name = "Aryan";
const age = 17;
const greeting = <p>Hello {name}, you are {age} years old! {2 + 2} = 4</p>;

// 6. Conditional rendering in JSX:
const element2 = (
  <div>
    {isLoggedIn && <UserProfile />}          {/* Short-circuit */}
    {isLoggedIn ? <Dashboard /> : <Login />} {/* Ternary */}
    {count > 0 && <p>Count: {count}</p>}     {/* Guard */}
  </div>
);
```

---

### Concept 2: Components — The Building Blocks

A component is a JavaScript function that returns JSX. Components are the atoms of a React application.

```jsx
// ── FUNCTION COMPONENT (the only way in modern React) ─────────────────

// Simplest component:
function Greeting() {
  return <h1>Hello, World!</h1>;
}

// Arrow function component:
const Greeting = () => <h1>Hello, World!</h1>;

// Component with props:
function UserCard({ name, age, city, avatarUrl }) {
  return (
    <div className="user-card">
      <img src={avatarUrl} alt={`${name}'s avatar`} />
      <h2>{name}</h2>
      <p>{age} years old · {city}</p>
    </div>
  );
}

// Using a component — it looks like an HTML element!
function App() {
  return (
    <main>
      <UserCard
        name="Aryan"
        age={17}
        city="Kolkata"
        avatarUrl="/avatars/aryan.jpg"
      />
      <UserCard
        name="Priya"
        age={16}
        city="Mumbai"
        avatarUrl="/avatars/priya.jpg"
      />
    </main>
  );
}

// Component RULES:
// 1. Name MUST start with uppercase letter (PascalCase)
//    → lowercase = HTML element, Uppercase = React component
// 2. Must return JSX (or null for nothing)
// 3. Must be a PURE function (same props → same output, no side effects in render)
// 4. Never call a component like a regular function: Component() — use <Component />

// Default props:
function Button({ label = "Click me", variant = "primary", disabled = false }) {
  return (
    <button
      className={`btn btn--${variant}`}
      disabled={disabled}
    >
      {label}
    </button>
  );
}

// children prop — content between component tags:
function Card({ title, children, className = "" }) {
  return (
    <div className={`card ${className}`}>
      <h3 className="card__title">{title}</h3>
      <div className="card__body">{children}</div>
    </div>
  );
}

// Usage with children:
<Card title="My Profile">
  <p>This is the card body content.</p>
  <Button label="Edit Profile" />
</Card>
```

---

### Concept 3: Props — Passing Data Down

Props are how parent components pass data to child components. They are **read-only** — a component must never modify its own props.

```jsx
// Props can be any JavaScript value:
function DataDisplay({
  name,               // String
  age,                // Number
  isActive,           // Boolean
  skills,             // Array
  address,            // Object
  onUpdate,           // Function (callback)
  children,           // ReactNode (JSX)
  style,              // CSS object
}) {
  return (
    <div style={style}>
      <h2>{name} ({age})</h2>
      {isActive && <span className="badge">Active</span>}
      <ul>
        {skills.map((skill, index) => (
          <li key={index}>{skill}</li>
        ))}
      </ul>
      <p>{address.city}, {address.country}</p>
      <button onClick={() => onUpdate({ name, age: age + 1 })}>
        Birthday!
      </button>
      {children}
    </div>
  );
}

// Spreading props (pass all properties of an object as props):
const userProps = { name: "Aryan", age: 17, isActive: true };
<DataDisplay {...userProps} skills={["Python", "React"]} />

// Prop types validation (runtime warnings in development):
import PropTypes from 'prop-types';

DataDisplay.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
  isActive: PropTypes.bool,
  skills: PropTypes.arrayOf(PropTypes.string),
  onUpdate: PropTypes.func.isRequired,
};

DataDisplay.defaultProps = {
  isActive: false,
  skills: [],
};
```

---

### Concept 4: State — Data That Changes Over Time

State is data that belongs to a component and can change. When state changes, React re-renders the component automatically.

```jsx
import { useState } from 'react';

// Basic counter:
function Counter() {
  const [count, setCount] = useState(0);  // [value, setter]
  //                                ↑ initial value

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(count - 1)}>-</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}

// State with objects (MUST replace the whole object, not mutate!):
function ProfileEditor() {
  const [user, setUser] = useState({
    name: "Aryan",
    age: 17,
    city: "Kolkata",
  });

  // ❌ WRONG — direct mutation (React won't see the change!):
  // user.name = "Bob";  // Never do this!

  // ✅ RIGHT — create a new object with spread:
  const updateName = (newName) => {
    setUser(prev => ({ ...prev, name: newName }));
    //             ↑ functional update — always use when new state depends on old state
  };

  return (
    <div>
      <p>{user.name}, {user.age}, {user.city}</p>
      <input
        value={user.name}
        onChange={(e) => updateName(e.target.value)}
      />
    </div>
  );
}

// State with arrays (never push/pop — always create new array!):
function TodoList() {
  const [todos, setTodos] = useState([]);
  const [input, setInput] = useState("");

  const addTodo = () => {
    if (!input.trim()) return;
    setTodos(prev => [...prev, { id: Date.now(), text: input, done: false }]);
    setInput("");
  };

  const toggleTodo = (id) => {
    setTodos(prev => prev.map(todo =>
      todo.id === id ? { ...todo, done: !todo.done } : todo
    ));
  };

  const deleteTodo = (id) => {
    setTodos(prev => prev.filter(todo => todo.id !== id));
  };

  return (
    <div>
      <input value={input} onChange={e => setInput(e.target.value)} />
      <button onClick={addTodo}>Add</button>
      <ul>
        {todos.map(todo => (
          <li key={todo.id}>
            <input
              type="checkbox"
              checked={todo.done}
              onChange={() => toggleTodo(todo.id)}
            />
            <span style={{ textDecoration: todo.done ? 'line-through' : 'none' }}>
              {todo.text}
            </span>
            <button onClick={() => deleteTodo(todo.id)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

---

### Concept 5: Events — Reacting to User Input

```jsx
function EventExamples() {
  // Event handlers receive a SyntheticEvent (React's wrapper around browser events):
  const handleClick = (event) => {
    console.log(event.target);          // The clicked element
    event.preventDefault();            // Prevent default browser behavior
    event.stopPropagation();           // Stop bubbling to parent
  };

  const handleChange = (event) => {
    console.log(event.target.value);   // Current input value
  };

  const handleSubmit = (event) => {
    event.preventDefault();            // MUST prevent form reload!
    const formData = new FormData(event.target);
    const data = Object.fromEntries(formData);
  };

  const handleKeyDown = (event) => {
    if (event.key === 'Enter') { /* submit */ }
    if (event.key === 'Escape') { /* close modal */ }
    if (event.ctrlKey && event.key === 's') { /* save */ }
  };

  return (
    <div>
      {/* Inline arrow function — passes extra args: */}
      <button onClick={(e) => handleClick(e)}>Click</button>

      {/* Direct reference — no extra args: */}
      <button onClick={handleClick}>Click</button>

      {/* With custom argument: */}
      <button onClick={() => deleteItem(item.id)}>Delete</button>

      <input
        type="text"
        onChange={handleChange}
        onKeyDown={handleKeyDown}
        onFocus={() => console.log('focused')}
        onBlur={() => console.log('blurred')}
      />

      <form onSubmit={handleSubmit}>
        <input name="username" type="text" />
        <input name="password" type="password" />
        <button type="submit">Submit</button>
      </form>

      <div
        onMouseEnter={() => setHovered(true)}
        onMouseLeave={() => setHovered(false)}
      >
        Hover me
      </div>
    </div>
  );
}
```

---

### Concept 6: Lists & Keys

```jsx
function ProductList({ products }) {
  return (
    <ul>
      {products.map(product => (
        // KEY is MANDATORY on root element of mapped list!
        // Must be UNIQUE among siblings, STABLE (not index if list can change)
        <li key={product.id}>
          <h3>{product.name}</h3>
          <p>${product.price}</p>
        </li>
      ))}
    </ul>
  );
}

// ❌ WRONG — using index as key when list items can be reordered/deleted:
{items.map((item, index) => <li key={index}>{item.name}</li>)}
// React can't tell items apart when reordered — causes bugs with forms, animations

// ✅ RIGHT — use stable, unique ID:
{items.map(item => <li key={item.id}>{item.name}</li>)}

// Rendering components in a list:
{users.map(user => (
  <UserCard key={user.id} name={user.name} age={user.age} />
))}

// Conditional list (filter before map):
{products
  .filter(p => p.inStock)
  .sort((a, b) => a.price - b.price)
  .map(p => <ProductCard key={p.id} {...p} />)
}
```

---

🧪 **Mini Task 1:**
> Build a `ColorPicker` component that shows 5 color buttons. Clicking a button changes the background color of a preview box below. Use `useState` to track the selected color.
> ✅ *Expected: Clicking "Red" makes the box red, "Blue" makes it blue, etc.*

🧪 **Mini Task 2:**
> Build a `SearchableList` component that takes an array of strings as props and renders an input field. As you type, the list filters in real time — only showing items that include the typed text.

---

## ⚙️ 4. Complete Hooks System Breakdown

> 🎯 *Goal: Master every built-in hook — nothing hidden.*

---

### Hook 1: `useState` — Local Component State

```jsx
import { useState } from 'react';

// Basic usage:
const [value, setValue] = useState(initialValue);

// Lazy initialization — expensive computation runs only once:
const [expensiveState, setExpensiveState] = useState(() => {
  return computeExpensiveValue();  // Called only on first render
});

// Functional updates — always use when new state depends on old:
setCount(prev => prev + 1);       // ✅ Safe — always has latest value
setCount(count + 1);              // ❌ Risky — count may be stale in closures

// Batching — React batches state updates in event handlers:
function handleClick() {
  setCount(c => c + 1);  // These are batched into ONE render
  setName("Aryan");      // (React 18+ batches even in async code!)
  setActive(true);
}

// Reset state to initial value:
const [state, setState] = useState(initialState);
const reset = () => setState(initialState);

// Toggle boolean:
const [isOpen, setIsOpen] = useState(false);
const toggle = () => setIsOpen(prev => !prev);
```

---

### Hook 2: `useEffect` — Side Effects & Lifecycle

```jsx
import { useEffect } from 'react';

// Syntax:
useEffect(() => {
  // Effect runs after render
  return () => {
    // Cleanup runs before next effect OR when component unmounts
  };
}, [dependencies]);  // Only re-run when dependencies change

// ── Effect variations by dependency array ─────────────────────────────

// 1. No dependency array — runs after EVERY render (usually wrong):
useEffect(() => {
  console.log('Runs after every render');
});

// 2. Empty array — runs ONCE after first render (componentDidMount):
useEffect(() => {
  console.log('Runs once on mount');
  return () => console.log('Cleanup on unmount');
}, []);

// 3. With dependencies — runs when deps change:
useEffect(() => {
  document.title = `${count} notifications`;
}, [count]);

// ── Real-world examples ────────────────────────────────────────────────

// Fetching data:
function UserProfile({ userId }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    let cancelled = false;          // Prevent state update on unmounted component!

    async function fetchUser() {
      try {
        setLoading(true);
        setError(null);
        const response = await fetch(`/api/users/${userId}`);
        if (!response.ok) throw new Error('Failed to fetch');
        const data = await response.json();
        if (!cancelled) {           // Only update if still mounted
          setUser(data);
        }
      } catch (err) {
        if (!cancelled) setError(err.message);
      } finally {
        if (!cancelled) setLoading(false);
      }
    }

    fetchUser();

    return () => { cancelled = true; };  // Cleanup: cancel stale requests
  }, [userId]);  // Re-fetch when userId changes

  if (loading) return <Spinner />;
  if (error) return <ErrorMessage message={error} />;
  return <div>{user?.name}</div>;
}

// Event listener:
useEffect(() => {
  const handleKeyDown = (e) => {
    if (e.key === 'Escape') onClose();
  };
  window.addEventListener('keydown', handleKeyDown);
  return () => window.removeEventListener('keydown', handleKeyDown);
}, [onClose]);

// Interval / timer:
useEffect(() => {
  const id = setInterval(() => {
    setTime(new Date());
  }, 1000);
  return () => clearInterval(id);  // MUST cleanup!
}, []);

// WebSocket connection:
useEffect(() => {
  const ws = new WebSocket('wss://example.com/ws');
  ws.onmessage = (event) => setMessages(prev => [...prev, event.data]);
  return () => ws.close();
}, []);

// Intersection Observer (scroll animations):
useEffect(() => {
  const observer = new IntersectionObserver(
    ([entry]) => setIsVisible(entry.isIntersecting),
    { threshold: 0.1 }
  );
  if (elementRef.current) observer.observe(elementRef.current);
  return () => observer.disconnect();
}, []);
```

---

### Hook 3: `useContext` — Share State Without Prop Drilling

```jsx
import { createContext, useContext, useState } from 'react';

// 1. Create the context:
const ThemeContext = createContext(null);  // null = default value

// 2. Create a Provider component:
export function ThemeProvider({ children }) {
  const [theme, setTheme] = useState('light');

  const value = {
    theme,
    isDark: theme === 'dark',
    toggleTheme: () => setTheme(t => t === 'light' ? 'dark' : 'light'),
  };

  return (
    <ThemeContext.Provider value={value}>
      {children}
    </ThemeContext.Provider>
  );
}

// 3. Create a custom hook (best practice):
export function useTheme() {
  const context = useContext(ThemeContext);
  if (!context) {
    throw new Error('useTheme must be used within a ThemeProvider');
  }
  return context;
}

// 4. Wrap your app:
function App() {
  return (
    <ThemeProvider>
      <Router>
        <Header />
        <Main />
      </Router>
    </ThemeProvider>
  );
}

// 5. Use anywhere in the tree — NO prop passing needed:
function Header() {
  const { theme, toggleTheme } = useTheme();
  return (
    <header data-theme={theme}>
      <button onClick={toggleTheme}>
        Toggle {theme === 'light' ? '🌙' : '☀️'}
      </button>
    </header>
  );
}

// Full auth context pattern:
const AuthContext = createContext(null);

export function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    // Check for existing session on mount:
    checkSession().then(user => {
      setUser(user);
      setLoading(false);
    });
  }, []);

  const login = async (credentials) => {
    const user = await api.login(credentials);
    setUser(user);
  };

  const logout = async () => {
    await api.logout();
    setUser(null);
  };

  return (
    <AuthContext.Provider value={{ user, loading, login, logout }}>
      {!loading && children}
    </AuthContext.Provider>
  );
}

export const useAuth = () => {
  const ctx = useContext(AuthContext);
  if (!ctx) throw new Error('useAuth must be inside AuthProvider');
  return ctx;
};
```

---

### Hook 4: `useRef` — Mutable Values & DOM Access

```jsx
import { useRef, useEffect } from 'react';

// ── DOM reference ─────────────────────────────────────────────────────
function AutoFocusInput() {
  const inputRef = useRef(null);  // null = initial value before mount

  useEffect(() => {
    inputRef.current?.focus();  // Access DOM node after mount
  }, []);

  return <input ref={inputRef} type="text" />;
}

// Scroll to element:
const sectionRef = useRef(null);
const scrollToSection = () => {
  sectionRef.current?.scrollIntoView({ behavior: 'smooth' });
};

// ── Mutable value that survives re-renders but DOESN'T trigger them ───
// Perfect for: previous value, timers, abort controllers, WebSocket instances

// Track previous state value:
function usePrevious(value) {
  const prevRef = useRef(value);
  useEffect(() => {
    prevRef.current = value;
  });  // No deps — runs after EVERY render
  return prevRef.current;  // Returns value from BEFORE this render
}

function Component({ count }) {
  const prevCount = usePrevious(count);
  return <p>Now: {count}, Before: {prevCount}</p>;
}

// Timer/interval ID:
function Timer() {
  const [seconds, setSeconds] = useState(0);
  const intervalRef = useRef(null);

  const start = () => {
    intervalRef.current = setInterval(() => {
      setSeconds(s => s + 1);
    }, 1000);
  };

  const stop = () => {
    clearInterval(intervalRef.current);
  };

  useEffect(() => () => clearInterval(intervalRef.current), []); // Cleanup

  return (
    <div>
      <p>{seconds}s</p>
      <button onClick={start}>Start</button>
      <button onClick={stop}>Stop</button>
    </div>
  );
}

// AbortController for cancellable fetch:
function useFetch(url) {
  const [data, setData] = useState(null);
  const abortRef = useRef(null);

  const refetch = async () => {
    abortRef.current?.abort();  // Cancel previous request
    abortRef.current = new AbortController();
    try {
      const res = await fetch(url, { signal: abortRef.current.signal });
      const json = await res.json();
      setData(json);
    } catch (e) {
      if (e.name !== 'AbortError') throw e;
    }
  };

  return { data, refetch };
}
```

---

### Hook 5: `useReducer` — Complex State Logic

```jsx
import { useReducer } from 'react';

// useReducer is useState for complex state with multiple sub-values
// or when next state depends on action type

// Define reducer (pure function — no side effects!):
function cartReducer(state, action) {
  switch (action.type) {
    case 'ADD_ITEM': {
      const existing = state.items.find(i => i.id === action.item.id);
      if (existing) {
        return {
          ...state,
          items: state.items.map(i =>
            i.id === action.item.id
              ? { ...i, quantity: i.quantity + 1 }
              : i
          ),
        };
      }
      return {
        ...state,
        items: [...state.items, { ...action.item, quantity: 1 }],
      };
    }
    case 'REMOVE_ITEM':
      return {
        ...state,
        items: state.items.filter(i => i.id !== action.id),
      };
    case 'UPDATE_QUANTITY':
      return {
        ...state,
        items: state.items.map(i =>
          i.id === action.id ? { ...i, quantity: action.quantity } : i
        ).filter(i => i.quantity > 0),
      };
    case 'CLEAR_CART':
      return { ...state, items: [] };
    case 'APPLY_DISCOUNT':
      return { ...state, discount: action.code };
    default:
      throw new Error(`Unknown action: ${action.type}`);
  }
}

const initialState = { items: [], discount: null };

function ShoppingCart() {
  const [cart, dispatch] = useReducer(cartReducer, initialState);

  const total = cart.items.reduce(
    (sum, item) => sum + item.price * item.quantity, 0
  );

  return (
    <div>
      {cart.items.map(item => (
        <div key={item.id}>
          <span>{item.name} × {item.quantity}</span>
          <button onClick={() => dispatch({ type: 'REMOVE_ITEM', id: item.id })}>
            Remove
          </button>
          <button onClick={() => dispatch({
            type: 'UPDATE_QUANTITY', id: item.id, quantity: item.quantity + 1
          })}>
            +
          </button>
        </div>
      ))}
      <p>Total: ${total.toFixed(2)}</p>
      <button onClick={() => dispatch({ type: 'CLEAR_CART' })}>Clear</button>
    </div>
  );
}
```

---

### Hook 6: `useMemo` — Memoize Expensive Computations

```jsx
import { useMemo, useState } from 'react';

function ProductCatalog({ products, filters }) {
  const [sortBy, setSortBy] = useState('price');
  const [searchQuery, setSearchQuery] = useState('');

  // Expensive computation — only recalculates when deps change:
  const filteredProducts = useMemo(() => {
    console.log('Filtering...'); // See when it actually runs
    return products
      .filter(p => {
        if (filters.category && p.category !== filters.category) return false;
        if (filters.maxPrice && p.price > filters.maxPrice) return false;
        if (searchQuery && !p.name.toLowerCase().includes(searchQuery.toLowerCase())) return false;
        return true;
      })
      .sort((a, b) => {
        if (sortBy === 'price') return a.price - b.price;
        if (sortBy === 'name') return a.name.localeCompare(b.name);
        if (sortBy === 'rating') return b.rating - a.rating;
        return 0;
      });
  }, [products, filters, sortBy, searchQuery]);
  //  ↑ Only re-runs when these change — not on every random re-render

  // When to use useMemo:
  // ✅ Filtering/sorting large arrays (100+ items)
  // ✅ Expensive mathematical computations
  // ✅ Creating new objects/arrays passed to React.memo children
  // ❌ Don't over-memoize — simple operations are faster without it

  return (
    <div>
      <input value={searchQuery} onChange={e => setSearchQuery(e.target.value)} />
      <select value={sortBy} onChange={e => setSortBy(e.target.value)}>
        <option value="price">Price</option>
        <option value="name">Name</option>
        <option value="rating">Rating</option>
      </select>
      <p>{filteredProducts.length} products</p>
      {filteredProducts.map(p => <ProductCard key={p.id} {...p} />)}
    </div>
  );
}
```

---

### Hook 7: `useCallback` — Memoize Functions

```jsx
import { useCallback, useState, memo } from 'react';

// useCallback returns a memoized function — same reference unless deps change
// Essential when passing callbacks to React.memo children

const ExpensiveList = memo(function ExpensiveList({ items, onDelete, onToggle }) {
  console.log('ExpensiveList rendered');
  return (
    <ul>
      {items.map(item => (
        <li key={item.id}>
          <span>{item.name}</span>
          <button onClick={() => onToggle(item.id)}>Toggle</button>
          <button onClick={() => onDelete(item.id)}>Delete</button>
        </li>
      ))}
    </ul>
  );
});

function ParentComponent() {
  const [items, setItems] = useState([
    { id: 1, name: 'Item 1', active: true },
    { id: 2, name: 'Item 2', active: false },
  ]);
  const [otherState, setOtherState] = useState(0);

  // Without useCallback — new function reference on every render → ExpensiveList always re-renders!
  // const handleDelete = (id) => setItems(prev => prev.filter(i => i.id !== id));

  // With useCallback — same reference until deps change → ExpensiveList skips re-render!
  const handleDelete = useCallback((id) => {
    setItems(prev => prev.filter(i => i.id !== id));
  }, []);  // Empty deps — function never changes (uses functional update)

  const handleToggle = useCallback((id) => {
    setItems(prev => prev.map(i =>
      i.id === id ? { ...i, active: !i.active } : i
    ));
  }, []);

  return (
    <div>
      <button onClick={() => setOtherState(n => n + 1)}>
        Other: {otherState} (won't re-render list)
      </button>
      <ExpensiveList
        items={items}
        onDelete={handleDelete}
        onToggle={handleToggle}
      />
    </div>
  );
}
```

---

### Hook 8: `useId` — Unique IDs for Accessibility

```jsx
import { useId } from 'react';

// Generates a stable, unique ID that works in both SSR and client
// (replaces Math.random() or manual ID generation)

function FormField({ label, type = 'text', ...props }) {
  const id = useId();  // Generates something like ":r0:", ":r1:", etc.

  return (
    <div>
      <label htmlFor={id}>{label}</label>
      <input id={id} type={type} {...props} />
    </div>
  );
}

// Multiple IDs from one component:
function RadioGroup({ options, name }) {
  const groupId = useId();

  return (
    <fieldset>
      {options.map((option, i) => (
        <div key={option.value}>
          <input
            type="radio"
            id={`${groupId}-${i}`}  // Unique per option
            name={name}
            value={option.value}
          />
          <label htmlFor={`${groupId}-${i}`}>{option.label}</label>
        </div>
      ))}
    </fieldset>
  );
}
```

---

### Hook 9: `useTransition` — Non-Urgent State Updates

```jsx
import { useTransition, useState } from 'react';

// Mark state updates as "non-urgent" — React can interrupt them
// to handle more urgent updates (like keyboard input)

function SearchPage() {
  const [query, setQuery] = useState('');
  const [results, setResults] = useState([]);
  const [isPending, startTransition] = useTransition();

  const handleSearch = (e) => {
    const value = e.target.value;
    setQuery(value);  // Urgent — update input immediately

    startTransition(() => {
      // Non-urgent — can be interrupted if user types again
      const filtered = heavyFilter(value);  // Expensive operation
      setResults(filtered);
    });
  };

  return (
    <div>
      <input value={query} onChange={handleSearch} />
      {isPending && <Spinner />}  {/* Show while transition is pending */}
      <ResultsList results={results} />
    </div>
  );
}
```

---

### Hook 10: `useDeferredValue` — Defer Expensive Renders

```jsx
import { useDeferredValue, memo } from 'react';

// Similar to useTransition but for values you don't control

const HeavyList = memo(({ query }) => {
  // Expensive filtering on thousands of items:
  const filtered = allItems.filter(item =>
    item.name.toLowerCase().includes(query.toLowerCase())
  );
  return <ul>{filtered.map(item => <li key={item.id}>{item.name}</li>)}</ul>;
});

function App() {
  const [query, setQuery] = useState('');
  const deferredQuery = useDeferredValue(query);
  // deferredQuery lags behind query — input stays responsive!
  const isStale = query !== deferredQuery;

  return (
    <div>
      <input value={query} onChange={e => setQuery(e.target.value)} />
      <div style={{ opacity: isStale ? 0.6 : 1 }}>
        {/* Shows stale results with opacity while new ones compute */}
        <HeavyList query={deferredQuery} />
      </div>
    </div>
  );
}
```

---

### Hook 11: `useLayoutEffect` — DOM Measurements Before Paint

```jsx
import { useLayoutEffect, useRef, useState } from 'react';

// useLayoutEffect fires SYNCHRONOUSLY after DOM updates but BEFORE browser paint
// Use for: measuring DOM elements, preventing visual flicker, positioning tooltips

function Tooltip({ children, text }) {
  const tooltipRef = useRef(null);
  const [position, setPosition] = useState({ top: 0, left: 0 });

  useLayoutEffect(() => {
    // Measure tooltip size BEFORE it's shown to user — no flicker!
    const tooltip = tooltipRef.current;
    if (tooltip) {
      const rect = tooltip.getBoundingClientRect();
      // Adjust position if tooltip goes off-screen:
      if (rect.right > window.innerWidth) {
        setPosition(prev => ({ ...prev, left: window.innerWidth - rect.width }));
      }
    }
  });  // Runs after every render (for measurement)

  return (
    <div ref={tooltipRef} style={position}>
      {text}
    </div>
  );
}

// Rule: prefer useEffect, use useLayoutEffect only when you need to:
// - Measure DOM elements
// - Prevent visual flicker from position adjustments
// - Trigger scroll positioning on route change
```

---

### Hook 12: `useImperativeHandle` — Customize ref Exposure

```jsx
import { useImperativeHandle, forwardRef, useRef } from 'react';

// Lets you control what the parent can do with a ref to your component

const VideoPlayer = forwardRef(function VideoPlayer({ src }, ref) {
  const videoRef = useRef(null);

  // Expose only specific methods — not the full DOM node:
  useImperativeHandle(ref, () => ({
    play()  { videoRef.current.play(); },
    pause() { videoRef.current.pause(); },
    seek(time) { videoRef.current.currentTime = time; },
    get duration() { return videoRef.current.duration; },
  }));

  return <video ref={videoRef} src={src} />;
});

// Usage:
function App() {
  const playerRef = useRef(null);

  return (
    <>
      <VideoPlayer ref={playerRef} src="/video.mp4" />
      <button onClick={() => playerRef.current.play()}>Play</button>
      <button onClick={() => playerRef.current.pause()}>Pause</button>
      <button onClick={() => playerRef.current.seek(30)}>Jump to 0:30</button>
    </>
  );
}
```

---

### Hook 13: `useSyncExternalStore` — Subscribe to External Stores

```jsx
import { useSyncExternalStore } from 'react';

// The correct way to subscribe to external (non-React) state sources
// Used by Redux, Zustand, and other state managers internally

// Subscribe to browser online/offline status:
function useOnlineStatus() {
  return useSyncExternalStore(
    (callback) => {
      window.addEventListener('online', callback);
      window.addEventListener('offline', callback);
      return () => {
        window.removeEventListener('online', callback);
        window.removeEventListener('offline', callback);
      };
    },
    () => navigator.onLine,           // Get current value (client)
    () => true                        // Get current value (server — always online)
  );
}

// Subscribe to window size:
function useWindowSize() {
  return useSyncExternalStore(
    (callback) => {
      window.addEventListener('resize', callback);
      return () => window.removeEventListener('resize', callback);
    },
    () => ({ width: window.innerWidth, height: window.innerHeight }),
    () => ({ width: 0, height: 0 }) // SSR fallback
  );
}

function App() {
  const isOnline = useOnlineStatus();
  const { width } = useWindowSize();
  return (
    <p>
      {isOnline ? '🟢 Online' : '🔴 Offline'} | Window: {width}px
    </p>
  );
}
```

---

### 📊 Hooks Reference Table

| Hook                    | Purpose                                           | When to Use                                      |
|-------------------------|---------------------------------------------------|--------------------------------------------------|
| `useState`              | Local component state                             | Any value that should trigger re-render          |
| `useEffect`             | Side effects after render                         | Data fetching, subscriptions, DOM manipulation   |
| `useContext`            | Read context value                                | Share state without prop drilling                |
| `useRef`                | DOM access + mutable values without re-render     | Focus, scroll, timers, previous values           |
| `useReducer`            | Complex state with multiple sub-values            | Forms, carts, multi-step flows                   |
| `useMemo`               | Memoize expensive computation result              | Filtering/sorting large datasets                 |
| `useCallback`           | Memoize function reference                        | Callbacks passed to `React.memo` children        |
| `useId`                 | Generate unique, stable ID                        | Form labels, ARIA attributes                     |
| `useTransition`         | Mark update as non-urgent                         | Search, heavy filtering, tab switching           |
| `useDeferredValue`      | Defer expensive child renders                     | When you can't control the state update          |
| `useLayoutEffect`       | Sync effect before browser paint                  | DOM measurement, position calculation            |
| `useImperativeHandle`   | Customize what ref exposes                        | Video players, focus managers, canvas            |
| `useSyncExternalStore`  | Subscribe to external stores                      | Redux, Zustand, browser APIs                     |
| `useDebugValue`         | Label custom hooks in DevTools                    | Library authors, debugging                       |

---

## 🔄 5. Real-World Workflow

### 🟢 Beginner Workflow: Building a Component from Scratch

```
Think about the UI → Identify state → Build static version → Add interactivity → Extract components
```

```jsx
// Step 1: Start with static JSX (no state yet)
// Step 2: Identify what changes over time → that's state
// Step 3: Decide where state lives (lowest common ancestor)
// Step 4: Pass state down as props, pass handlers up via callbacks
// Step 5: Extract repeated patterns into components

// Example: Blog with search and filtering

// STATE ANALYSIS:
// - searchQuery: changes when user types → useState in parent
// - selectedTag: changes when tag clicked → useState in parent
// - posts: comes from server → fetched in useEffect

function BlogPage() {
  const [searchQuery, setSearchQuery] = useState('');
  const [selectedTag, setSelectedTag] = useState('all');
  const [posts, setPosts] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetchPosts().then(data => {
      setPosts(data);
      setLoading(false);
    });
  }, []);

  const filteredPosts = useMemo(() => {
    return posts
      .filter(post => selectedTag === 'all' || post.tags.includes(selectedTag))
      .filter(post => post.title.toLowerCase().includes(searchQuery.toLowerCase()));
  }, [posts, selectedTag, searchQuery]);

  const allTags = useMemo(() => {
    return ['all', ...new Set(posts.flatMap(p => p.tags))];
  }, [posts]);

  if (loading) return <PageSkeleton />;

  return (
    <main>
      <SearchBar value={searchQuery} onChange={setSearchQuery} />
      <TagFilter
        tags={allTags}
        selected={selectedTag}
        onSelect={setSelectedTag}
      />
      <PostGrid posts={filteredPosts} />
    </main>
  );
}
```

---

### 🔵 Professional Workflow: Feature Module Architecture

```jsx
// feature/auth/index.js — Self-contained feature module

// Types (TypeScript):
// interface User { id: string; name: string; email: string; role: 'admin' | 'user'; }

// Context:
const AuthContext = createContext(null);

// Reducer:
function authReducer(state, action) {
  switch (action.type) {
    case 'LOGIN_START':
      return { ...state, loading: true, error: null };
    case 'LOGIN_SUCCESS':
      return { ...state, loading: false, user: action.user, error: null };
    case 'LOGIN_FAILURE':
      return { ...state, loading: false, error: action.error };
    case 'LOGOUT':
      return { user: null, loading: false, error: null };
    default:
      return state;
  }
}

// Provider:
export function AuthProvider({ children }) {
  const [state, dispatch] = useReducer(authReducer, {
    user: null, loading: true, error: null
  });

  useEffect(() => {
    // Restore session from localStorage/cookie:
    const token = localStorage.getItem('authToken');
    if (token) {
      api.validateToken(token)
        .then(user => dispatch({ type: 'LOGIN_SUCCESS', user }))
        .catch(() => dispatch({ type: 'LOGOUT' }));
    } else {
      dispatch({ type: 'LOGOUT' });
    }
  }, []);

  const login = useCallback(async (credentials) => {
    dispatch({ type: 'LOGIN_START' });
    try {
      const { user, token } = await api.login(credentials);
      localStorage.setItem('authToken', token);
      dispatch({ type: 'LOGIN_SUCCESS', user });
    } catch (err) {
      dispatch({ type: 'LOGIN_FAILURE', error: err.message });
    }
  }, []);

  const logout = useCallback(async () => {
    await api.logout();
    localStorage.removeItem('authToken');
    dispatch({ type: 'LOGOUT' });
  }, []);

  return (
    <AuthContext.Provider value={{ ...state, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
}

export const useAuth = () => {
  const ctx = useContext(AuthContext);
  if (!ctx) throw new Error('useAuth must be inside AuthProvider');
  return ctx;
};

// Protected route component:
export function ProtectedRoute({ children, requiredRole }) {
  const { user, loading } = useAuth();

  if (loading) return <LoadingScreen />;
  if (!user) return <Navigate to="/login" replace />;
  if (requiredRole && user.role !== requiredRole) return <NotAuthorized />;

  return children;
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: GitHub Profile Finder

**Goal:** Fetch and display GitHub user data from the API.
**Estimated Time:** 1-2 hours
**Skills Used:** useState, useEffect, conditional rendering, lists, forms

```jsx
// github-finder/src/App.jsx
import { useState, useEffect } from 'react';

function App() {
  const [username, setUsername] = useState('');
  const [query, setQuery] = useState('');
  const [user, setUser] = useState(null);
  const [repos, setRepos] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  useEffect(() => {
    if (!query) return;

    const controller = new AbortController();

    async function fetchData() {
      setLoading(true);
      setError(null);
      setUser(null);
      setRepos([]);

      try {
        const [userRes, reposRes] = await Promise.all([
          fetch(`https://api.github.com/users/${query}`, { signal: controller.signal }),
          fetch(`https://api.github.com/users/${query}/repos?sort=stars&per_page=6`, { signal: controller.signal }),
        ]);

        if (!userRes.ok) throw new Error('User not found');

        const [userData, reposData] = await Promise.all([
          userRes.json(),
          reposRes.json(),
        ]);

        setUser(userData);
        setRepos(Array.isArray(reposData) ? reposData : []);
      } catch (err) {
        if (err.name !== 'AbortError') setError(err.message);
      } finally {
        setLoading(false);
      }
    }

    fetchData();
    return () => controller.abort();
  }, [query]);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (username.trim()) setQuery(username.trim());
  };

  return (
    <div className="app">
      <h1>GitHub Profile Finder</h1>

      <form onSubmit={handleSubmit}>
        <input
          type="text"
          value={username}
          onChange={e => setUsername(e.target.value)}
          placeholder="Enter GitHub username..."
        />
        <button type="submit" disabled={loading}>
          {loading ? 'Searching...' : 'Search'}
        </button>
      </form>

      {error && <p className="error">❌ {error}</p>}

      {user && (
        <div className="profile">
          <img src={user.avatar_url} alt={user.login} />
          <h2>{user.name ?? user.login}</h2>
          <p>{user.bio}</p>
          <div className="stats">
            <span>⭐ {user.public_repos} repos</span>
            <span>👥 {user.followers} followers</span>
            <span>👤 {user.following} following</span>
          </div>
          <a href={user.html_url} target="_blank" rel="noopener noreferrer">
            View Profile →
          </a>

          <h3>Top Repositories</h3>
          <ul className="repos">
            {repos.map(repo => (
              <li key={repo.id}>
                <a href={repo.html_url} target="_blank" rel="noopener noreferrer">
                  {repo.name}
                </a>
                <span>⭐ {repo.stargazers_count}</span>
                {repo.language && <span className="lang">{repo.language}</span>}
                {repo.description && <p>{repo.description}</p>}
              </li>
            ))}
          </ul>
        </div>
      )}
    </div>
  );
}

export default App;
```

✅ **You've succeeded when:** Searching "torvalds" shows Linus Torvalds' profile with his repos sorted by stars.

---

### 🔵 Intermediate Project: Real-Time Kanban Board

```jsx
// kanban/src/KanbanBoard.jsx
import { useState, useCallback } from 'react';

const COLUMNS = ['Todo', 'In Progress', 'Review', 'Done'];

const initialTasks = [
  { id: '1', title: 'Set up React project', column: 'Done', priority: 'low' },
  { id: '2', title: 'Build UI components', column: 'In Progress', priority: 'high' },
  { id: '3', title: 'Connect to API', column: 'Todo', priority: 'high' },
  { id: '4', title: 'Write tests', column: 'Todo', priority: 'medium' },
];

function KanbanBoard() {
  const [tasks, setTasks] = useState(initialTasks);
  const [dragging, setDragging] = useState(null);
  const [editingId, setEditingId] = useState(null);
  const [newTaskColumn, setNewTaskColumn] = useState(null);
  const [newTaskTitle, setNewTaskTitle] = useState('');

  const moveTask = useCallback((taskId, toColumn) => {
    setTasks(prev => prev.map(t =>
      t.id === taskId ? { ...t, column: toColumn } : t
    ));
  }, []);

  const addTask = useCallback((column) => {
    if (!newTaskTitle.trim()) return;
    setTasks(prev => [...prev, {
      id: crypto.randomUUID(),
      title: newTaskTitle.trim(),
      column,
      priority: 'medium',
    }]);
    setNewTaskTitle('');
    setNewTaskColumn(null);
  }, [newTaskTitle]);

  const deleteTask = useCallback((taskId) => {
    setTasks(prev => prev.filter(t => t.id !== taskId));
  }, []);

  const handleDragOver = (e) => {
    e.preventDefault();
    e.dataTransfer.dropEffect = 'move';
  };

  const handleDrop = (e, column) => {
    e.preventDefault();
    if (dragging) moveTask(dragging, column);
    setDragging(null);
  };

  return (
    <div className="kanban">
      <h1>Kanban Board</h1>
      <div className="kanban__columns">
        {COLUMNS.map(column => {
          const columnTasks = tasks.filter(t => t.column === column);
          return (
            <div
              key={column}
              className="kanban__column"
              onDragOver={handleDragOver}
              onDrop={e => handleDrop(e, column)}
            >
              <div className="kanban__column-header">
                <h2>{column}</h2>
                <span className="badge">{columnTasks.length}</span>
              </div>

              <ul className="kanban__tasks">
                {columnTasks.map(task => (
                  <li
                    key={task.id}
                    className={`kanban__task priority--${task.priority}`}
                    draggable
                    onDragStart={() => setDragging(task.id)}
                    onDragEnd={() => setDragging(null)}
                  >
                    {editingId === task.id ? (
                      <TaskEditForm
                        task={task}
                        onSave={(updated) => {
                          setTasks(prev => prev.map(t => t.id === task.id ? updated : t));
                          setEditingId(null);
                        }}
                        onCancel={() => setEditingId(null)}
                      />
                    ) : (
                      <>
                        <p>{task.title}</p>
                        <div className="task__actions">
                          <button onClick={() => setEditingId(task.id)}>✏️</button>
                          <button onClick={() => deleteTask(task.id)}>🗑️</button>
                        </div>
                      </>
                    )}
                  </li>
                ))}
              </ul>

              {newTaskColumn === column ? (
                <form onSubmit={e => { e.preventDefault(); addTask(column); }}>
                  <input
                    autoFocus
                    value={newTaskTitle}
                    onChange={e => setNewTaskTitle(e.target.value)}
                    placeholder="Task title..."
                  />
                  <button type="submit">Add</button>
                  <button type="button" onClick={() => setNewTaskColumn(null)}>Cancel</button>
                </form>
              ) : (
                <button
                  className="add-task-btn"
                  onClick={() => setNewTaskColumn(column)}
                >
                  + Add task
                </button>
              )}
            </div>
          );
        })}
      </div>
    </div>
  );
}
```

---

### 🔴 Advanced Project: AI Chat Interface with Streaming

```jsx
// ai-chat/src/Chat.jsx
import { useState, useRef, useEffect, useCallback } from 'react';

function useStreamingChat() {
  const [messages, setMessages] = useState([]);
  const [isStreaming, setIsStreaming] = useState(false);
  const abortRef = useRef(null);

  const sendMessage = useCallback(async (content) => {
    const userMessage = {
      id: crypto.randomUUID(),
      role: 'user',
      content,
      timestamp: Date.now(),
    };

    setMessages(prev => [...prev, userMessage]);
    setIsStreaming(true);

    // Create placeholder for assistant response:
    const assistantId = crypto.randomUUID();
    setMessages(prev => [
      ...prev,
      { id: assistantId, role: 'assistant', content: '', timestamp: Date.now() }
    ]);

    abortRef.current = new AbortController();

    try {
      const response = await fetch('/api/chat', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          messages: [...messages, userMessage].map(m => ({
            role: m.role,
            content: m.content,
          })),
        }),
        signal: abortRef.current.signal,
      });

      if (!response.ok) throw new Error('API error');

      // Stream the response:
      const reader = response.body.getReader();
      const decoder = new TextDecoder();
      let fullContent = '';

      while (true) {
        const { done, value } = await reader.read();
        if (done) break;

        const chunk = decoder.decode(value);
        const lines = chunk.split('\n').filter(line => line.startsWith('data: '));

        for (const line of lines) {
          const data = line.slice(6); // Remove 'data: '
          if (data === '[DONE]') break;

          try {
            const { delta } = JSON.parse(data);
            fullContent += delta ?? '';
            // Update the assistant message token by token:
            setMessages(prev => prev.map(m =>
              m.id === assistantId
                ? { ...m, content: fullContent }
                : m
            ));
          } catch {}
        }
      }
    } catch (err) {
      if (err.name !== 'AbortError') {
        setMessages(prev => prev.map(m =>
          m.id === assistantId
            ? { ...m, content: '❌ Error: ' + err.message }
            : m
        ));
      }
    } finally {
      setIsStreaming(false);
    }
  }, [messages]);

  const stopStreaming = () => abortRef.current?.abort();
  const clearChat = () => setMessages([]);

  return { messages, isStreaming, sendMessage, stopStreaming, clearChat };
}

function ChatInterface() {
  const { messages, isStreaming, sendMessage, stopStreaming, clearChat } = useStreamingChat();
  const [input, setInput] = useState('');
  const bottomRef = useRef(null);

  useEffect(() => {
    bottomRef.current?.scrollIntoView({ behavior: 'smooth' });
  }, [messages]);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!input.trim() || isStreaming) return;
    sendMessage(input.trim());
    setInput('');
  };

  return (
    <div className="chat">
      <div className="chat__messages">
        {messages.length === 0 && (
          <div className="chat__empty">
            <p>Ask me anything about Python, AI, or web development!</p>
          </div>
        )}
        {messages.map(msg => (
          <div key={msg.id} className={`message message--${msg.role}`}>
            <div className="message__content">
              {msg.content || (msg.role === 'assistant' && isStreaming && <Cursor />)}
            </div>
          </div>
        ))}
        <div ref={bottomRef} />
      </div>

      <form className="chat__input" onSubmit={handleSubmit}>
        <textarea
          value={input}
          onChange={e => setInput(e.target.value)}
          placeholder="Ask something..."
          onKeyDown={e => {
            if (e.key === 'Enter' && !e.shiftKey) {
              e.preventDefault();
              handleSubmit(e);
            }
          }}
          disabled={isStreaming}
        />
        {isStreaming ? (
          <button type="button" onClick={stopStreaming}>Stop</button>
        ) : (
          <button type="submit" disabled={!input.trim()}>Send</button>
        )}
      </form>
    </div>
  );
}

const Cursor = () => <span className="cursor">▋</span>;
```

🔥 **Challenge:** Add persistent message history using `localStorage` and a model selector dropdown to switch between different AI models.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Mutating State Directly

```jsx
// ❌ WRONG — direct mutation won't trigger re-render:
const [user, setUser] = useState({ name: 'Aryan', skills: [] });

// This mutates the state object in place — React doesn't see the change!
user.name = 'Bob';
user.skills.push('React');
setUser(user);   // Same object reference → React skips re-render!

// ✅ RIGHT — always create new objects/arrays:
setUser(prev => ({ ...prev, name: 'Bob' }));
setUser(prev => ({ ...prev, skills: [...prev.skills, 'React'] }));
```

---

### ❌ Mistake 2: Missing or Wrong `key` Props

```jsx
// ❌ WRONG — no key:
{items.map(item => <Card title={item.name} />)}

// ❌ WRONG — index as key when list can change:
{items.map((item, index) => <Card key={index} title={item.name} />)}
// If you delete item at index 0, React reuses the first DOM node for item 2 → form bugs!

// ✅ RIGHT — stable unique ID:
{items.map(item => <Card key={item.id} title={item.name} />)}
```

---

### ❌ Mistake 3: Creating Functions/Objects Inside JSX

```jsx
// ❌ WRONG — new object every render → forces child re-renders:
<ChildComponent style={{ color: 'red', fontSize: 16 }} onUpdate={() => save()} />
// New object + new function on every render — if Child is React.memo'd, it's pointless!

// ✅ RIGHT — defined outside render or memoized:
const style = useMemo(() => ({ color: 'red', fontSize: 16 }), []);
const handleUpdate = useCallback(() => save(), []);
<ChildComponent style={style} onUpdate={handleUpdate} />
```

---

### ❌ Mistake 4: Putting Everything in useState

```jsx
// ❌ WRONG — derived state in useState causes sync bugs:
const [firstName, setFirstName] = useState('Aryan');
const [lastName, setLastName] = useState('Dev');
const [fullName, setFullName] = useState('Aryan Dev');  // 💥 Can get out of sync!

// Must remember to update fullName whenever either name changes!

// ✅ RIGHT — derive it during render:
const [firstName, setFirstName] = useState('Aryan');
const [lastName, setLastName] = useState('Dev');
const fullName = `${firstName} ${lastName}`;  // Always in sync, no state needed
```

---

### ❌ Mistake 5: Using `useEffect` for Synchronization, Not Just Side Effects

```jsx
// ❌ WRONG — using useEffect to sync derived state:
const [items, setItems] = useState([]);
const [count, setCount] = useState(0);

useEffect(() => {
  setCount(items.length);  // Unnecessary extra render!
}, [items]);

// ✅ RIGHT — just compute it:
const count = items.length;  // Computed during render, no useEffect needed

// ❌ WRONG — useEffect for event-triggered logic:
const [submitted, setSubmitted] = useState(false);

useEffect(() => {
  if (submitted) {
    doSubmit();  // Runs asynchronously after render — unexpected behavior
    setSubmitted(false);
  }
}, [submitted]);

// ✅ RIGHT — call it directly in the event handler:
const handleSubmit = () => {
  doSubmit();  // Direct, predictable, no extra render
};
```

---

### ❌ Mistake 6: Stale Closures in `useEffect`

```jsx
// ❌ WRONG — count is stale (closes over initial value 0):
const [count, setCount] = useState(0);

useEffect(() => {
  const id = setInterval(() => {
    setCount(count + 1);  // Always sets to 1! count is frozen at 0
  }, 1000);
  return () => clearInterval(id);
}, []);  // Missing dependency!

// ✅ RIGHT — use functional update (no closure dependency):
useEffect(() => {
  const id = setInterval(() => {
    setCount(prev => prev + 1);  // Uses latest value — no closure!
  }, 1000);
  return () => clearInterval(id);
}, []);  // [] is correct — doesn't depend on count anymore
```

---

### ❌ Mistake 7: Forgetting Cleanup in `useEffect`

```jsx
// ❌ WRONG — memory leaks and state updates on unmounted components:
useEffect(() => {
  fetch('/api/data').then(res => res.json()).then(data => {
    setData(data);  // Component may have unmounted by now!
  });
}, []);

// ✅ RIGHT — cancel with AbortController or isMounted flag:
useEffect(() => {
  const controller = new AbortController();
  fetch('/api/data', { signal: controller.signal })
    .then(res => res.json())
    .then(data => setData(data))
    .catch(err => { if (err.name !== 'AbortError') setError(err.message); });
  return () => controller.abort();
}, []);
```

---

### ❌ Mistake 8: Over-Lifting State

```jsx
// ❌ WRONG — lifting ALL state to App causes entire tree to re-render:
function App() {
  const [inputValue, setInputValue] = useState(''); // Only used in SearchBar!
  return <SearchBar value={inputValue} onChange={setInputValue} />;
}

// ✅ RIGHT — keep state as close to where it's used as possible:
function SearchBar() {
  const [inputValue, setInputValue] = useState(''); // Stays local!
  return <input value={inputValue} onChange={e => setInputValue(e.target.value)} />;
}
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: Custom Hooks — The Most Underused React Pattern

Custom hooks let you extract and reuse stateful logic between components. Any function that uses other hooks is a custom hook.

```jsx
// useLocalStorage — persist state to localStorage:
function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    try {
      const stored = localStorage.getItem(key);
      return stored ? JSON.parse(stored) : initialValue;
    } catch {
      return initialValue;
    }
  });

  const setStoredValue = useCallback((newValue) => {
    try {
      const resolved = newValue instanceof Function ? newValue(value) : newValue;
      setValue(resolved);
      localStorage.setItem(key, JSON.stringify(resolved));
    } catch (err) {
      console.error(err);
    }
  }, [key, value]);

  return [value, setStoredValue];
}

// useDebounce — delay expensive operations:
function useDebounce(value, delay = 300) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => setDebouncedValue(value), delay);
    return () => clearTimeout(timer);
  }, [value, delay]);

  return debouncedValue;
}

// useAsync — data fetching with states:
function useAsync(asyncFn, deps = []) {
  const [state, setState] = useState({ data: null, loading: true, error: null });

  useEffect(() => {
    let cancelled = false;
    setState({ data: null, loading: true, error: null });

    asyncFn()
      .then(data => { if (!cancelled) setState({ data, loading: false, error: null }); })
      .catch(error => { if (!cancelled) setState({ data: null, loading: false, error }); });

    return () => { cancelled = true; };
  }, deps);

  return state;
}

// useClickOutside — close dropdown/modal on outside click:
function useClickOutside(ref, callback) {
  useEffect(() => {
    function handleClick(event) {
      if (ref.current && !ref.current.contains(event.target)) {
        callback();
      }
    }
    document.addEventListener('mousedown', handleClick);
    return () => document.removeEventListener('mousedown', handleClick);
  }, [ref, callback]);
}

// useMediaQuery — responsive logic in components:
function useMediaQuery(query) {
  const [matches, setMatches] = useState(
    () => window.matchMedia(query).matches
  );

  useEffect(() => {
    const mq = window.matchMedia(query);
    const handler = (e) => setMatches(e.matches);
    mq.addEventListener('change', handler);
    return () => mq.removeEventListener('change', handler);
  }, [query]);

  return matches;
}

// Usage:
const isMobile = useMediaQuery('(max-width: 768px)');
const prefersDark = useMediaQuery('(prefers-color-scheme: dark)');
```

---

### 💎 Tip 2: `React.memo` — Skip Unnecessary Re-Renders

```jsx
import { memo } from 'react';

// React.memo skips re-rendering if props haven't changed:
const ExpensiveChart = memo(function ExpensiveChart({ data, title }) {
  // Heavy computation inside — only runs when data or title changes
  const processedData = processData(data); // Expensive!
  return <ChartComponent data={processedData} title={title} />;
});

// Custom comparison function (when default shallow compare isn't enough):
const SmartComponent = memo(
  function SmartComponent({ user, config }) {
    return <div>{user.name}</div>;
  },
  (prevProps, nextProps) => {
    // Return true = skip re-render (props are "equal")
    // Return false = re-render
    return prevProps.user.id === nextProps.user.id &&
           prevProps.config.theme === nextProps.config.theme;
  }
);

// When to use React.memo:
// ✅ Component renders frequently but props rarely change
// ✅ Component has expensive render logic (calculations, formatting)
// ✅ Component is a pure presentational component deep in the tree
// ❌ Don't memo everything — React.memo itself has overhead
// ❌ Don't memo components that almost always receive new props
```

---

### 💎 Tip 3: Error Boundaries — Graceful Error Handling

```jsx
import { Component } from 'react';

// Error Boundaries MUST be class components (no hook equivalent yet)
class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false, error: null, errorInfo: null };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true, error };
  }

  componentDidCatch(error, errorInfo) {
    // Log to error monitoring service:
    console.error('Error caught:', error, errorInfo);
    this.setState({ errorInfo });
    // logToSentry(error, errorInfo); // e.g., Sentry.captureException(error)
  }

  render() {
    if (this.state.hasError) {
      return this.props.fallback || (
        <div className="error-boundary">
          <h2>Something went wrong.</h2>
          <p>{this.state.error?.message}</p>
          <button onClick={() => this.setState({ hasError: false })}>
            Try again
          </button>
        </div>
      );
    }
    return this.props.children;
  }
}

// Usage:
<ErrorBoundary fallback={<ErrorPage />}>
  <Dashboard />
</ErrorBoundary>

// Granular: each feature wrapped separately:
<main>
  <ErrorBoundary fallback={<p>Chart failed to load.</p>}>
    <RevenueChart />
  </ErrorBoundary>
  <ErrorBoundary fallback={<p>Table failed to load.</p>}>
    <DataTable />
  </ErrorBoundary>
</main>
```

---

### 💎 Tip 4: Compound Components Pattern

```jsx
// Compound components — related components that share implicit state
// Example: Tabs component

const TabsContext = createContext(null);

function Tabs({ defaultTab, children }) {
  const [activeTab, setActiveTab] = useState(defaultTab);

  return (
    <TabsContext.Provider value={{ activeTab, setActiveTab }}>
      <div className="tabs">{children}</div>
    </TabsContext.Provider>
  );
}

function TabList({ children }) {
  return <div className="tab-list" role="tablist">{children}</div>;
}

function Tab({ id, children }) {
  const { activeTab, setActiveTab } = useContext(TabsContext);
  const isActive = activeTab === id;

  return (
    <button
      role="tab"
      aria-selected={isActive}
      className={`tab ${isActive ? 'tab--active' : ''}`}
      onClick={() => setActiveTab(id)}
    >
      {children}
    </button>
  );
}

function TabPanel({ id, children }) {
  const { activeTab } = useContext(TabsContext);
  if (activeTab !== id) return null;
  return <div role="tabpanel">{children}</div>;
}

// Attach as sub-components:
Tabs.List = TabList;
Tabs.Tab = Tab;
Tabs.Panel = TabPanel;

// Beautiful, intuitive usage:
<Tabs defaultTab="profile">
  <Tabs.List>
    <Tabs.Tab id="profile">Profile</Tabs.Tab>
    <Tabs.Tab id="settings">Settings</Tabs.Tab>
    <Tabs.Tab id="notifications">Notifications</Tabs.Tab>
  </Tabs.List>
  <Tabs.Panel id="profile"><ProfileForm /></Tabs.Panel>
  <Tabs.Panel id="settings"><SettingsForm /></Tabs.Panel>
  <Tabs.Panel id="notifications"><NotificationPrefs /></Tabs.Panel>
</Tabs>
```

---

### 💎 Tip 5: Render Props Pattern

```jsx
// A component that shares logic by calling a function prop with data
// Useful when you need flexible rendering of shared behavior

function MouseTracker({ children, render }) {
  const [position, setPosition] = useState({ x: 0, y: 0 });

  useEffect(() => {
    const handleMove = (e) => setPosition({ x: e.clientX, y: e.clientY });
    window.addEventListener('mousemove', handleMove);
    return () => window.removeEventListener('mousemove', handleMove);
  }, []);

  // Call the render prop with the data:
  return render ? render(position) : children(position);
}

// Usage:
<MouseTracker render={({ x, y }) => (
  <div style={{ position: 'fixed', left: x, top: y, pointerEvents: 'none' }}>
    🎯
  </div>
)} />

// As children function:
<MouseTracker>
  {({ x, y }) => <p>Mouse at: {x}, {y}</p>}
</MouseTracker>
```

---

### 💎 Tip 6: `Suspense` & `lazy` — Code Splitting

```jsx
import { Suspense, lazy, useState } from 'react';

// lazy() — load component only when first rendered:
const Dashboard = lazy(() => import('./pages/Dashboard'));
const Settings = lazy(() => import('./pages/Settings'));
const Reports = lazy(() => import('./pages/Reports'));

// Suspense — show fallback while lazy component loads:
function App() {
  const [page, setPage] = useState('dashboard');

  const pages = {
    dashboard: Dashboard,
    settings: Settings,
    reports: Reports,
  };

  const Page = pages[page];

  return (
    <div>
      <nav>
        <button onClick={() => setPage('dashboard')}>Dashboard</button>
        <button onClick={() => setPage('settings')}>Settings</button>
        <button onClick={() => setPage('reports')}>Reports</button>
      </nav>

      <Suspense fallback={<LoadingSpinner />}>
        <Page />
      </Suspense>
    </div>
  );
}

// Nested Suspense for granular loading:
<Suspense fallback={<PageSkeleton />}>
  <Dashboard>
    <Suspense fallback={<ChartSkeleton />}>
      <HeavyChart />
    </Suspense>
    <Suspense fallback={<TableSkeleton />}>
      <DataTable />
    </Suspense>
  </Dashboard>
</Suspense>
```

---

### 🛠️ Recommended Tools & Resources

| Tool / Resource             | What It's For                                                  | Notes                                       |
|-----------------------------|----------------------------------------------------------------|---------------------------------------------|
| React DevTools              | Inspect component tree, props, state, performance              | Browser extension — essential               |
| Vite                        | Fastest React development server + build tool                  | Preferred over CRA in 2024+                 |
| React Query (TanStack Query)| Server state management — fetching, caching, synchronization   | Replaces most useEffect data fetching       |
| Zustand                     | Tiny, powerful client state management                         | Simpler than Redux                          |
| React Router v6             | Client-side routing with data loading                          | Standard routing solution                   |
| React Hook Form             | Performant forms with validation                               | Avoids re-renders on every keystroke        |
| Zod                         | TypeScript-first schema validation                             | Works perfectly with React Hook Form        |
| Tailwind CSS                | Utility-first CSS for React components                         | Most popular React styling approach         |
| Storybook                   | Develop and document components in isolation                   | Essential for design systems                |
| Vitest + React Testing Lib  | Unit and integration testing for React                         | Standard testing stack                      |

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: React Server Components (RSC)

```jsx
// React Server Components run on the server — they can:
// - Directly access databases, file systems, secret environment variables
// - Never ship their JavaScript to the client (zero bundle size impact!)
// - Can't use useState, useEffect, or browser-only APIs

// server-component.jsx (runs on server only)
async function ProductPage({ id }) {
  // Direct database query — no API needed!
  const product = await db.product.findUnique({ where: { id } });
  const reviews = await db.review.findMany({ where: { productId: id } });

  return (
    <div>
      <h1>{product.name}</h1>
      <p>${product.price}</p>
      {/* Client component for interactivity: */}
      <AddToCartButton productId={id} price={product.price} />
      <ReviewList reviews={reviews} />
    </div>
  );
}

// ── "use client" boundary — everything below runs in the browser ──────
'use client';

import { useState } from 'react';

function AddToCartButton({ productId, price }) {
  const [added, setAdded] = useState(false);
  const [loading, setLoading] = useState(false);

  const addToCart = async () => {
    setLoading(true);
    await fetch('/api/cart', {
      method: 'POST',
      body: JSON.stringify({ productId, price }),
    });
    setAdded(true);
    setLoading(false);
  };

  return (
    <button onClick={addToCart} disabled={loading || added}>
      {added ? '✅ Added!' : loading ? 'Adding...' : 'Add to Cart'}
    </button>
  );
}

// The mental model:
// Server Components → fetch data, render HTML → send to browser
// Client Components → received as HTML → hydrated → interactive
```

---

### Advanced Concept 2: Server Actions — Forms Without API Routes

```jsx
// Next.js 14+ Server Actions — run server-side code from client components
'use server';

import { revalidatePath } from 'next/cache';
import { redirect } from 'next/navigation';

// Server Action — an async function marked with 'use server':
async function createPost(formData) {
  'use server';
  const title = formData.get('title');
  const content = formData.get('content');

  // Validate:
  if (!title || !content) throw new Error('Title and content required');

  // Direct DB call — no API route needed!
  const post = await db.post.create({ data: { title, content } });

  // Revalidate the cache and redirect:
  revalidatePath('/blog');
  redirect(`/blog/${post.id}`);
}

// Client usage — works even without JavaScript!
function NewPostForm() {
  return (
    <form action={createPost}>
      <input name="title" required placeholder="Post title" />
      <textarea name="content" required placeholder="Post content" />
      <button type="submit">Publish Post</button>
    </form>
  );
}

// With useActionState (React 19):
'use client';
import { useActionState } from 'react';

function PostForm() {
  const [state, action, isPending] = useActionState(createPost, null);

  return (
    <form action={action}>
      {state?.error && <p className="error">{state.error}</p>}
      <input name="title" />
      <button disabled={isPending}>
        {isPending ? 'Publishing...' : 'Publish'}
      </button>
    </form>
  );
}
```

---

### Advanced Concept 3: `useOptimistic` — Instant UI Updates

```jsx
'use client';
import { useOptimistic, useTransition } from 'react';

// Immediately show the expected result while async operation runs
// If it fails, reverts to the actual state automatically

function LikeButton({ post }) {
  const [optimisticLikes, addOptimisticLike] = useOptimistic(
    post.likes,
    (currentLikes, delta) => currentLikes + delta
  );

  const [isPending, startTransition] = useTransition();

  const handleLike = () => {
    startTransition(async () => {
      addOptimisticLike(1);  // Show +1 immediately!
      await likePost(post.id); // Actual server call
      // If this fails, React reverts to post.likes automatically
    });
  };

  return (
    <button onClick={handleLike} disabled={isPending}>
      ❤️ {optimisticLikes}
    </button>
  );
}

// Optimistic list update:
function TodoList({ todos, addTodo }) {
  const [optimisticTodos, addOptimisticTodo] = useOptimistic(
    todos,
    (state, newTodo) => [...state, { ...newTodo, pending: true }]
  );

  async function handleAdd(text) {
    const newTodo = { id: crypto.randomUUID(), text, done: false };
    addOptimisticTodo(newTodo);         // Instant UI update
    await addTodo(newTodo);             // Server sync
    // On success: React replaces optimistic with real
    // On failure: React reverts to original todos
  }
}
```

---

### Advanced Concept 4: React 19 `use()` Hook

```jsx
// React 19: use() can read promises and context anywhere
import { use, Suspense } from 'react';

// Read a promise — must be inside Suspense!
function UserProfile({ userPromise }) {
  const user = use(userPromise);  // Suspends until promise resolves
  return <h1>{user.name}</h1>;
}

function Page() {
  const userPromise = fetchUser(1);  // Created outside component!

  return (
    <Suspense fallback={<Skeleton />}>
      <UserProfile userPromise={userPromise} />
    </Suspense>
  );
}

// use() with Context — can be called conditionally (unlike useContext!):
function ConditionalTheme({ showTheme }) {
  if (!showTheme) return <p>No theme</p>;

  const theme = use(ThemeContext);  // Called conditionally — impossible with useContext!
  return <p>Theme: {theme}</p>;
}
```

---

### ⚡ Performance Optimization Table

| Technique                    | Impact    | When to Use                                          |
|------------------------------|-----------|------------------------------------------------------|
| `React.memo`                 | High      | Pure components receiving stable props               |
| `useMemo` for computations   | High      | Filtering/sorting 100+ items                         |
| `useCallback` for handlers   | Medium    | Callbacks passed to `React.memo` children            |
| `useTransition` / deferred   | High      | Search, filtering, tab switching                     |
| Code splitting (`lazy`)      | Very High | Large components loaded conditionally                |
| `Suspense` boundaries        | High      | Prevent full-page spinners, enable parallel loading  |
| Virtual scrolling            | Very High | Lists with 1,000+ items (use `react-virtual`)        |
| `content-visibility`         | Medium    | Long pages with off-screen sections                  |
| React Server Components      | Very High | Replace client data-fetching with server rendering   |
| Bundle analysis              | High      | Find and eliminate large dependencies                |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: React Fiber — The Internal Engine

```jsx
/*
React Fiber is the reconciliation engine introduced in React 16.
It completely replaced the old recursive reconciler.

Key concepts:
- FIBER: A JavaScript object representing a unit of work
  Each React element has a corresponding fiber node with:
  - type: the component function or string
  - key: for reconciliation
  - child, sibling, return: tree links
  - pendingProps, memoizedProps: props before/after render
  - memoizedState: the hook state linked list
  - effectTag: what DOM mutation is needed
  - lanes: priority bitmask

- WORK LOOP: React processes fibers one by one
  - beginWork(): render phase — create/update fibers
  - completeWork(): commit phase — create DOM nodes
  - Can be interrupted between fibers (concurrent mode!)

- LANES: Priority system for scheduling
  const SyncLane = 0b0000000000000000000000000000001;
  const InputContinuousLane = 0b0000000000000000000000000000100;
  const DefaultLane = 0b0000000000000000000000000010000;
  const TransitionLane1 = 0b0000000000000000000000001000000;
  const IdleLane = 0b0100000000000000000000000000000;
*/

// You can inspect the fiber tree in DevTools console:
// $r → The selected React component's fiber
// $r._debugFiber → Raw fiber node
// $r._debugFiber.memoizedState → Hook state linked list

// See fiber of any DOM node:
const fiber = domElement._reactFiber;  // Internal, not stable API
```

---

### 🔮 Secret 2: Batching in React 18+

```jsx
// React 18 introduced automatic batching EVERYWHERE
// (previously, only batching inside React event handlers)

// React 17 — NO batching in setTimeout, fetch callbacks:
setTimeout(() => {
  setCount(c => c + 1);  // Re-render 1
  setName('Aryan');       // Re-render 2
  // 2 separate renders!
}, 1000);

// React 18 — automatic batching EVERYWHERE:
setTimeout(() => {
  setCount(c => c + 1);  // Batched!
  setName('Aryan');       // Batched!
  // Only 1 render!
}, 1000);

// Opt out of batching (rare — e.g., you need intermediate renders):
import { flushSync } from 'react-dom';

flushSync(() => {
  setCount(c => c + 1);  // Triggers render immediately
});
// DOM is updated here
flushSync(() => {
  setName('Aryan');      // Another immediate render
});
```

---

### 🔮 Secret 3: Hook State is a Linked List

```jsx
/*
Hooks are stored as a linked list on the fiber node.
This is WHY hooks can't be called conditionally!

When React renders a component with hooks:

useState(0)      → fiber.memoizedState → { queue: StateQueue, next: → }
useState('')     →                                                     { queue: StateQueue, next: → }
useEffect(fn)    →                                                                                  { effect, next: → }
useRef(null)     →                                                                                                     { current: null, next: null }

React matches hooks by POSITION in the linked list.
If you conditionally call a hook, the list indices shift
and React reads the WRONG hook's state → catastrophic bugs!

This is enforced by the "Rules of Hooks" ESLint plugin.
*/

// This is why you MUST NOT do this:
function Component({ showFeature }) {
  if (showFeature) {
    const [x, setX] = useState(0);  // ❌ Conditional hook!
  }
  const [y, setY] = useState('');   // React thinks this is x's hook!
}
```

---

### 🔮 Secret 4: The Reconciliation Algorithm (Diffing)

```jsx
/*
When React re-renders, it diffs the previous and new Virtual DOM trees.
The algorithm has key assumptions for O(n) complexity:

1. ELEMENT TYPE CHANGE → destroy old tree, create new one from scratch
   <div> → <span>  = destroy entire div tree, create span tree
   This means: never swap between element types unnecessarily!

2. SAME TYPE → update attributes, recurse into children

3. KEYS → allow React to match elements across renders
   Without keys: React matches by position (causes bugs when items reorder)
   With keys: React matches by identity (stable, correct)
*/

// Performance insight — wrapping in different element types causes expensive work:
function Tab({ isActive, children }) {
  // ❌ WRONG — React destroys and recreates the entire form every switch:
  if (isActive) {
    return <div className="active">{children}</div>;
  }
  return <section>{children}</section>;

  // ✅ RIGHT — same element type, just className changes:
  return <div className={isActive ? 'active' : 'inactive'}>{children}</div>;
}

// Preserve component state across condition changes with CSS:
// ✅ Show/hide without unmounting (preserves state):
<div style={{ display: isVisible ? 'block' : 'none' }}>
  <ExpensiveComponent />
</div>

// vs unmounting (resets state):
{isVisible && <ExpensiveComponent />}
```

---

### 🔮 Secret 5: `startTransition` Can Un-suspend

```jsx
// A transition can cause a suspended tree to "un-suspend" without showing fallback
// This enables smooth tab switching between content that may need to load

import { useTransition, Suspense, useState } from 'react';

function Tabs() {
  const [tab, setTab] = useState('about');
  const [isPending, startTransition] = useTransition();

  function selectTab(nextTab) {
    startTransition(() => {
      setTab(nextTab);  // Wrapped in transition — if new tab suspends,
                        // React KEEPS showing the current tab (not the fallback!)
                        // until the new tab is ready. Much smoother UX!
    });
  }

  return (
    <>
      <button onClick={() => selectTab('about')}>About</button>
      <button onClick={() => selectTab('posts')}>Posts</button>
      <Suspense fallback={<Spinner />}>
        {tab === 'about' && <About />}
        {tab === 'posts' && <Posts />}  {/* May suspend on first load */}
      </Suspense>
      {isPending && <div className="loading-overlay" />}
    </>
  );
}
```

---

### 🔮 Secret 6: `createPortal` — Render Anywhere in the DOM

```jsx
import { createPortal } from 'react-dom';

// Render JSX into a different DOM node — outside the component's DOM position
// Event bubbling STILL follows React tree (not DOM tree)

function Modal({ isOpen, onClose, children }) {
  if (!isOpen) return null;

  // Renders into document.body, not inside the parent div
  return createPortal(
    <div className="modal-overlay" onClick={onClose}>
      <div className="modal" onClick={e => e.stopPropagation()}>
        <button className="modal__close" onClick={onClose}>×</button>
        {children}
      </div>
    </div>,
    document.body  // Target DOM node — can be any existing element
  );
}

// Tooltip portal (avoids overflow: hidden parent clipping):
function Tooltip({ target, text }) {
  const rect = target.getBoundingClientRect();
  return createPortal(
    <div
      className="tooltip"
      style={{ position: 'fixed', top: rect.bottom, left: rect.left }}
    >
      {text}
    </div>,
    document.body
  );
}
```

---

### 🔮 Secret 7: `React.cloneElement` & `Children` API

```jsx
import { Children, cloneElement, isValidElement } from 'react';

// cloneElement — clone a React element and modify its props:
function RadioGroup({ children, name, value, onChange }) {
  // Inject name, checked, onChange into each Radio child:
  return (
    <div role="radiogroup">
      {Children.map(children, (child) => {
        if (!isValidElement(child)) return child;
        return cloneElement(child, {
          name,
          checked: child.props.value === value,
          onChange,
        });
      })}
    </div>
  );
}

// Usage:
<RadioGroup name="plan" value={plan} onChange={setPlan}>
  <Radio value="free">Free</Radio>
  <Radio value="pro">Pro</Radio>
  <Radio value="enterprise">Enterprise</Radio>
</RadioGroup>
// Each Radio automatically gets: name="plan", checked=..., onChange=...

// Children utilities:
Children.count(children)          // Count children (handles null/undefined)
Children.toArray(children)        // Convert to flat array with stable keys
Children.forEach(children, fn)    // Iterate
Children.only(children)           // Assert + return single child
```

---

### 🔮 Secret 8: `useDebugValue` — Custom Hook Labels in DevTools

```jsx
import { useDebugValue, useState, useEffect } from 'react';

// Label your custom hooks in React DevTools for easier debugging:

function useFetch(url) {
  const [data, setData] = useState(null);
  const [status, setStatus] = useState('idle');

  // Shows "useFetch: loading" or "useFetch: success" in DevTools!
  useDebugValue(status, (s) => `Status: ${s}`);

  useEffect(() => {
    setStatus('loading');
    fetch(url)
      .then(r => r.json())
      .then(d => { setData(d); setStatus('success'); })
      .catch(() => setStatus('error'));
  }, [url]);

  return { data, status };
}

// With format function (second arg — only called in DevTools, not in prod):
useDebugValue(new Date(timestamp), date => date.toISOString());
```

---

### 🔮 Secret 9: View Transitions API in React

```jsx
// React 18+ + View Transitions API = page transitions like native apps

import { startTransition } from 'react';
import { useNavigate } from 'react-router-dom';

function AnimatedLink({ to, children }) {
  const navigate = useNavigate();

  const handleClick = (e) => {
    e.preventDefault();

    if (document.startViewTransition) {
      document.startViewTransition(() => {
        startTransition(() => navigate(to));
      });
    } else {
      navigate(to);  // Fallback without animation
    }
  };

  return <a href={to} onClick={handleClick}>{children}</a>;
}

// CSS for the transition:
/*
::view-transition-old(root) {
  animation: slide-out 0.3s ease-in;
}
::view-transition-new(root) {
  animation: slide-in 0.3s ease-out;
}
*/
```

---

### 🔮 Secret 10: Concurrent Rendering Mental Model

```jsx
/*
REACT 18 CONCURRENT RENDERING — how it actually works:

Traditional (sync) rendering:
  Start render → ... can't be interrupted ... → Commit to DOM

Concurrent rendering:
  Start render → ... work unit ... → Check: is there urgent work? →
    No: continue → Commit
    Yes: PAUSE, handle urgent work, RESUME render

This is like a chef pausing mid-dish to answer a fire alarm,
then going back to exactly where they left off.

The render phase CAN be interrupted and restarted.
This means your render function WILL be called multiple times in StrictMode!
This is why: effects should be idempotent, mutations must not happen in render.

Features that enable concurrent rendering:
  - startTransition: mark update as "can be interrupted"
  - useDeferredValue: defer the rendering of a value
  - Suspense: pause rendering until data is ready
  - useTransition: gives isPending feedback during transition

Developer impact:
  - React.StrictMode invokes render functions TWICE (development only)
    to detect side effects in render — don't mutate outside in render!
  - Never produce side effects in render function (create DOM, call APIs)
  - Use useEffect for side effects — always
*/

// React.StrictMode double invocation:
function Component() {
  console.log('render'); // Logged TWICE in development!
  // This helps catch:
  // - setState during render
  // - Side effects in render
  // - Multiple renders for the same state
  return <div>Hello</div>;
}
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: JSX syntax, function components, props, children, conditional rendering
├── Week 2: useState (primitives, objects, arrays), events, controlled inputs, lists + keys
└── Week 3: useEffect (data fetching, subscriptions, cleanup), useRef (DOM + mutable values)
    └── Project: GitHub profile finder, weather app with API

PHASE 2 — INTERMEDIATE (Week 4-6)
├── Week 4: useContext + custom hooks, component patterns (compound, render props)
├── Week 5: useReducer for complex state, useMemo + useCallback + React.memo optimization
└── Week 6: React Router v6 (routes, params, nested, protected), Error Boundaries, Suspense + lazy
    └── Project: Multi-page SPA with auth, routing, and data fetching

PHASE 3 — ADVANCED (Week 7-10)
├── Week 7:  Advanced hooks (useTransition, useDeferredValue, useId, useImperativeHandle)
├── Week 8:  Testing (React Testing Library, Vitest, mocking, accessibility queries)
├── Week 9:  State management (Zustand or Redux Toolkit), React Query for server state
└── Week 10: TypeScript with React — types, interfaces, generic components
    └── Project: Full-featured dashboard with auth, CRUD, real-time updates

PHASE 4 — EXPERT / 0.01% (Month 3-6)
├── Month 3: Next.js — App Router, Server Components, Server Actions, streaming
├── Month 4: Performance profiling, bundle analysis, virtual scrolling, RSC optimization
├── Month 5: React internals — Fiber, reconciliation, concurrent features, scheduling
└── Month 6: Build and publish a React component library to npm with Storybook + tests
    └── Project: Full-stack Next.js app with Prisma, auth, payments, deployed to Vercel
```

---

### 🏁 Milestone Checklist

- [ ] I can build any UI with components, props, and state without googling
- [ ] I understand the rules of hooks and WHY they exist (linked list)
- [ ] I can explain the difference between controlled and uncontrolled components
- [ ] I've built a multi-page app with React Router
- [ ] I understand when to use useState vs useReducer vs useContext
- [ ] I can optimize renders with React.memo, useMemo, and useCallback correctly
- [ ] I've built and used at least 5 custom hooks
- [ ] I understand Error Boundaries and where to place them
- [ ] I can explain the Virtual DOM and reconciliation algorithm
- [ ] I understand stale closures in useEffect and how to fix them
- [ ] I've set up React Query or SWR for server state management
- [ ] I understand React Server Components and the server/client boundary
- [ ] I've profiled a React app with DevTools and found a real performance issue
- [ ] I understand React Fiber and concurrent rendering at a conceptual level

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "React is a Function from State to UI"

The core mental model of React is:

```
UI = f(state)
```

Given the same state, a pure React component always produces the same UI. This is the whole idea. React's job is to keep the UI in sync with state — and do it efficiently.

When you understand this deeply:
- You stop thinking in terms of "when do I update the DOM" → React handles that
- You start thinking in terms of "what is the state?" → derive everything from it
- You realize derived state (computed values) should never be in useState
- You understand why mutations break React — they change state without triggering the f(state) recalculation

---

### 🤫 Deep Insight 1: React is NOT a Framework — And That's a Problem

React describes itself as a "library for building user interfaces." This means React intentionally leaves out:
- Routing
- Data fetching
- State management
- Build tools
- Server rendering
- Form handling

This freedom is both a strength and a source of "decision fatigue." Every React project requires assembling an ecosystem. The 2024 answer to this is **Next.js** — which adds all of these on top of React, creating a true full-stack framework.

---

### 🤫 Deep Insight 2: Render ≠ Paint

Many developers think "re-render" means the browser repaints the screen. It doesn't.

- **Render**: React calls your component function and produces a new Virtual DOM tree (a JavaScript object tree — no DOM interaction)
- **Diff**: React compares old and new Virtual DOM trees
- **Commit**: Only if there's a real difference, React updates the real DOM
- **Paint**: The browser paints what the DOM tells it to (only if the DOM changed)

A component can re-render many times without the browser repainting anything. `React.memo` prevents unnecessary renders. But even without it, React's diffing often skips actual DOM updates.

---

### 🤫 Deep Insight 3: React's `key` is More Powerful Than You Think

The `key` prop isn't just for lists. It's a **reset mechanism** for any component.

```jsx
// Reset a component's state completely by changing its key:
function ProfileEditor({ userId }) {
  return (
    <Form key={userId} />  // Different userId = different Form instance = fresh state!
  );
}

// Without key — the form keeps the previous user's data:
// React sees <Form /> → <Form /> (same type) → updates props only, keeps state

// With key — React sees: <Form key="1" /> → <Form key="2" /> → destroys and recreates!
// This is the cleanest way to reset a component to initial state.
```

---

### 🧠 The Big Picture — React in the Modern Ecosystem

```
The React Universe in 2025:

Core:             React 19 — use(), useActionState, useOptimistic, ViewTransitions
Framework:        Next.js 15 — RSC, Server Actions, App Router, Turbopack
                  Remix — Data loading, nested routing, progressive enhancement
State:            Zustand (client), TanStack Query (server), Jotai (atomic)
Styling:          Tailwind CSS, CSS Modules, Styled Components, vanilla-extract
Testing:          Vitest, React Testing Library, Playwright (e2e)
Forms:            React Hook Form + Zod
Animation:        Framer Motion, React Spring, CSS animations
Native:           React Native + Expo (iOS/Android from React knowledge!)
3D:               React Three Fiber (Three.js in React)
AI:               Vercel AI SDK (streaming AI UIs in React)

The Trend:
2013-2018: Single Page Apps (SPA) — React renders everything in browser
2019-2021: SSR enters mainstream — Next.js pages router
2022-2024: Server-first revolution — React Server Components
2025+:     AI-driven UIs — streaming, progressive, server-orchestrated

React's position: The most widely used UI library, but increasingly
just the "view layer" of larger frameworks (Next.js, Remix).
Knowing React deeply means understanding both the library AND its ecosystem.
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                              |
|----------------------|----------------------------------------------------------------------------|
| Component            | A function that returns JSX — the atom of all React UIs                    |
| Props                | Read-only data passed from parent to child — never mutate them             |
| State                | Mutable data owned by a component — changing it triggers a re-render       |
| Hook                 | A function starting with `use` that lets you use React features            |
| Virtual DOM          | JavaScript representation of the UI — React diffs it to minimize real DOM updates |
| Reconciliation       | React's algorithm for comparing old and new component trees                |
| Fiber                | React's internal work unit — enables async, interruptible rendering        |
| `key` prop           | Stable identity for list items AND component reset mechanism               |
| Lifting State Up     | Moving state to the closest common ancestor to share between components    |
| Server Components    | Components that render on the server — no client JS, can access backend directly |

---

### The 10 Things to Remember

1. ✅ **Never mutate state** — always create new objects/arrays with spread
2. ✅ **Always use stable unique IDs as `key`** — never use array index for reorderable lists
3. ✅ **Use functional updates** (`setState(prev => ...)`) when new state depends on old
4. ✅ **Effects run AFTER render** — don't fetch in render, use `useEffect` or Server Components
5. ✅ **Always return a cleanup function from `useEffect`** — cancel fetches, clear timers
6. ✅ **Derive values during render** — don't sync derived state with `useEffect`
7. ✅ **Keep state as local as possible** — lift only when sharing is required
8. ✅ **Extract custom hooks** for any stateful logic you reuse across components
9. ✅ **`React.memo` + `useCallback` + `useMemo` together** — they only help as a set
10. ✅ **React.StrictMode double-invokes renders** — never produce side effects in render

---

### Quick Reference Cheat Sheet

```jsx
// ── PROJECT SETUP ───────────────────────────────────────────────────────
// npm create vite@latest my-app -- --template react
// npm create next-app@latest my-app

// ── JSX RULES ──────────────────────────────────────────────────────────
// className (not class), htmlFor (not for), camelCase attributes
// Self-close void elements: <img />, <input />, <br />
// Fragments: <> </> or <React.Fragment key={id}> </React.Fragment>
// Expressions: {value}, {fn()}, {condition && <JSX />}, {a ? b : c}
// Events: onClick, onChange, onSubmit, onKeyDown, onFocus, onBlur

// ── HOOKS AT A GLANCE ───────────────────────────────────────────────────
const [state, setState] = useState(init);
const [state, setState] = useState(() => expensiveInit());  // Lazy init
setState(prev => newValue);                                  // Functional update

useEffect(() => { /* side effect */ return () => { /* cleanup */ }; }, [deps]);

const ctx = useContext(MyContext);

const ref = useRef(initialValue);  // ref.current — mutable, no re-render

const [state, dispatch] = useReducer(reducer, initialState);

const memoized = useMemo(() => expensive(a, b), [a, b]);

const stableFn = useCallback(() => fn(a), [a]);

const id = useId();  // Stable unique ID for accessibility

const [isPending, startTransition] = useTransition();
startTransition(() => setExpensiveState(value));

const deferred = useDeferredValue(value);  // Lags behind value

// ── COMPONENT PATTERNS ──────────────────────────────────────────────────
// React.memo — skip re-render if props unchanged:
const Memoized = memo(Component);
const Memoized = memo(Component, (prev, next) => prev.id === next.id);

// forwardRef — forward ref to child DOM element:
const Input = forwardRef((props, ref) => <input ref={ref} {...props} />);

// lazy + Suspense — code splitting:
const Page = lazy(() => import('./Page'));
<Suspense fallback={<Spinner />}><Page /></Suspense>

// Error Boundary:
<ErrorBoundary fallback={<Error />}><RiskyComponent /></ErrorBoundary>

// Portal:
createPortal(<Modal />, document.body)

// ── STATE MANAGEMENT DECISION TREE ─────────────────────────────────────
// 1 component → useState
// 2-3 components → lift state up + props
// Complex state → useReducer
// Many components → useContext (or Zustand for large apps)
// Server state → React Query / SWR

// ── COMMON PATTERNS ─────────────────────────────────────────────────────
// Controlled input:
<input value={value} onChange={e => setValue(e.target.value)} />

// Uncontrolled input (rare — use React Hook Form for complex forms):
const ref = useRef(); ref.current.value;

// Derived state — compute during render:
const fullName = `${firstName} ${lastName}`;  // NOT useState!

// Toggle:
const toggle = () => setState(prev => !prev);

// List operations (always immutable!):
// Add:    [...prev, newItem]
// Remove: prev.filter(i => i.id !== id)
// Update: prev.map(i => i.id === id ? {...i, ...update} : i)
// Move:   (use immer or spread carefully)

// Reset component state:
<Component key={resetKey} />  // Change key to force fresh mount

// Stale closure fix in intervals:
useEffect(() => {
  const id = setInterval(() => setState(prev => prev + 1), 1000); // Functional update
  return () => clearInterval(id);
}, []);  // [] is correct when using functional update

// ── PERFORMANCE CHECKLIST ──────────────────────────────────────────────
// □ memo() expensive pure components
// □ useCallback() for callbacks passed to memo'd children
// □ useMemo() for expensive filter/sort on large datasets
// □ startTransition() for non-urgent state updates
// □ lazy() + Suspense for routes and large components
// □ Keys are stable unique IDs (never index for reorderable lists)
// □ State is as local as possible
// □ No new objects/functions created in JSX (outside render or memoized)
```

---

### What's Next?

After mastering React, your natural path:

- 📘 **Next.js** — The React framework for full-stack apps: SSR, RSC, Server Actions, file routing, API routes
- 📘 **TypeScript + React** — Type-safe React; interfaces, generic components, typed hooks
- 📘 **TanStack Query** — Server state management; replaces most useEffect data-fetching
- 📘 **React Native** — Build iOS + Android apps with your React knowledge
- 📘 **Testing** — React Testing Library + Vitest + Playwright for confidence at scale
- 📘 **Zustand / Redux Toolkit** — Client state management for large applications
- 📘 **React Three Fiber** — 3D experiences in React using Three.js

---

> 💬 *"The best React code is the React code you don't have to write. Start with the server."*
> — The React Team, on React Server Components

> 💬 *"Don't think about how to update the UI. Think about what state describes the UI at any given moment, and let React figure out the rest."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: React — Complete Library Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
