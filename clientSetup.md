# ⚛️ Client Side Project Setup (React + TailwindCSS + DaisyUI + React Router)

### 1️⃣ Initialize React Project
```bash
cd <your-new-project-directory>
npm install react-router-dom
npm install localforage match-sorter sort-by
```

### 2️⃣ TailwindCSS Setup

```bash
npm install -D tailwindcss@3
npx tailwindcss init
```
### 3️⃣ DaisyUI Installation
```bash
npm i -D daisyui@latest
```
### ✏️ Configure tailwind.config.js
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [require("daisyui")],
}

```
### 4️⃣ Setup Tailwind in index.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
### 5️⃣ ESLint Configuration 
##### If using eslint.config.js, ensure this line exists:
```js
node: true
```
### 6️⃣ Basic React Router Setup
```js
import {createBrowserRouter,RouterProvider,} from "react-router-dom";

const router = createBrowserRouter([
  {
    path: "/",
    element: <div>Hello world!</div>,
  },
]);

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
### 📤 Client Side Deployment

Follow the official deployment guide here:

🔗 [Client Deploy Guide](https://github.com/ProgrammingHero1/Job-Portal-Resources/blob/main/client-deploy.md)
