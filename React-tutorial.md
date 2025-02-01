# React Tutorial with Vite

## 1. Setting Up a Vite Application

### Prerequisites
Before setting up a React application using Vite, ensure you have the following installed:
- **Node.js** (LTS version recommended) – [Download Node.js](https://nodejs.org/)
- **npm** or **yarn** (comes with Node.js installation)

### Creating the Project
To create your project inside `D:/React-learning`, follow these steps:

1. Open your terminal (Command Prompt, PowerShell, or Git Bash) and navigate to your directory:
   ```sh
   cd D:/React-learning
   ```

2. Run the following command to create a Vite project:
   ```sh
   npm create vite@latest my-first-app --template react
   ```
   - `my-first-app` is the project name (you can change it).
   - `--template react` ensures it sets up a React environment.

3. Move into the project folder:
   ```sh
   cd my-first-app
   ```

4. Install dependencies:
   ```sh
   npm install
   ```

5. Start the development server:
   ```sh
   npm run dev
   ```
   This will start a local server, usually accessible at `http://localhost:5173/`.

---

## 2. Understanding the Vite Project Structure

After creating the Vite React app, you will see the following structure:
```
my-first-app/
├── node_modules/     # Dependencies installed via npm
├── public/           # Static assets like images
├── src/              # Source code (React components, styles, etc.)
│   ├── App.jsx       # Main component
│   ├── main.jsx      # Entry point for React app
│   ├── assets/       # Images, icons, etc.
│   ├── components/   # React components
│   ├── styles/       # CSS files
├── .gitignore        # Files to ignore in Git
├── index.html        # Main HTML file
├── package.json      # Project configuration & dependencies
├── vite.config.js    # Vite configuration
```

### Key Files & Their Purpose
- **`index.html`** - The entry point for the app.
- **`src/main.jsx`** - Renders the `App` component inside `index.html`.
- **`src/App.jsx`** - The main component containing the app UI.

---

## 3. React Topics with Code and Explanation

### JSX (JavaScript XML)
JSX allows us to write HTML-like syntax inside JavaScript.
Example:
```jsx
function Greeting() {
    return <h1>Hello, Welcome to React!</h1>;
}
```

### Components
Components allow code reuse. React components can be **Functional** or **Class-based**.
Example of a Functional Component:
```jsx
function Welcome(props) {
    return <h1>Hello, {props.name}!</h1>;
}
```

### Props (Properties)
Props pass data between components.
Example:
```jsx
function User({ name }) {
    return <h2>User: {name}</h2>;
}

export default function App() {
    return <User name="Alice" />;
}
```

### State and useState Hook
State allows components to manage data.
```jsx
import { useState } from "react";

function Counter() {
    const [count, setCount] = useState(0);
    return (
        <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increase</button>
        </div>
    );
}
```

### Handling Events
```jsx
function ButtonClick() {
    function handleClick() {
        alert("Button clicked!");
    }
    return <button onClick={handleClick}>Click Me</button>;
}
```

### Conditional Rendering
```jsx
function Message({ isLoggedIn }) {
    return isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Sign In</h1>;
}
```

### Lists and Keys
Rendering lists dynamically:
```jsx
const users = ["Alice", "Bob", "Charlie"];
function UserList() {
    return (
        <ul>
            {users.map((user, index) => (
                <li key={index}>{user}</li>
            ))}
        </ul>
    );
}
```

### Forms and Controlled Components
```jsx
import { useState } from "react";

function Form() {
    const [name, setName] = useState("");
    function handleSubmit(e) {
        e.preventDefault();
        alert(`Hello, ${name}`);
    }
    return (
        <form onSubmit={handleSubmit}>
            <input type="text" value={name} onChange={(e) => setName(e.target.value)} />
            <button type="submit">Submit</button>
        </form>
    );
}
```

---

## 4. Important React Concepts & Learning Steps

| Concept            | Description & Learning Step |
|-------------------|--------------------------------|
| JSX              | Learn JSX syntax and expressions |
| Components       | Create functional & class components |
| Props           | Pass data between components |
| State           | Use `useState` to manage state |
| Hooks           | Explore `useEffect`, `useContext`, etc. |
| Events          | Learn event handling in React |
| Conditional Rendering | Use ternary operators, `&&` for rendering |
| Lists & Keys    | Render lists dynamically with keys |
| Forms          | Manage form inputs and submissions |
| Routing        | Use React Router for navigation |
| Context API    | Manage global state with `useContext` |
| Redux Toolkit  | Learn state management for large apps |
| API Fetching   | Fetch data using `fetch()` or Axios |
| Deployment     | Deploy the app on Netlify/Vercel |

---

## 5.  Basic React Project - Counter App

## File: `src/App.jsx`
```jsx
import { useState } from "react";
import Counter from "./components/Counter";

export default function App() {
    return (
        <div>
            <h1>Simple Counter App</h1>
            <Counter />
        </div>
    );
}
```

### Explanation:
- The `App` component acts as the main component and imports `Counter`.
- It renders a title and the `Counter` component.

---

## File: `src/components/Counter.jsx`
```jsx
import { useState } from "react";

function Counter() {
    const [count, setCount] = useState(0);
    
    const increase = () => setCount(count + 1);
    const decrease = () => setCount(count - 1);
    const reset = () => setCount(0);

    return (
        <div>
            <h2>Count: {count}</h2>
            <button onClick={increase}>Increase</button>
            <button onClick={decrease}>Decrease</button>
            <button onClick={reset}>Reset</button>
        </div>
    );
}

export default Counter;
```

### Explanation:
- `useState` is used to manage the counter state.
- Three buttons allow increasing, decreasing, and resetting the count.

---

## File: `src/main.jsx`
```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

ReactDOM.createRoot(document.getElementById("root")).render(
    <React.StrictMode>
        <App />
    </React.StrictMode>
);
```

### Explanation:
- This is the entry point of the React application.
- It renders the `App` component inside the `root` div in `index.html`.

---

## File: `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>React Counter</title>
</head>
<body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
</body>
</html>
```

### Explanation:
- The `index.html` file contains a `div` with `id="root"`, where React will mount the app.
- The script tag loads `main.jsx`, which starts the React app.
