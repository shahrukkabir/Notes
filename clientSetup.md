## ⚛️ Client Side Project Setup (React + TailwindCSS + DaisyUI + React Router)

### 1️⃣ Initialize React Project
```bash
npm create vite@latest name-of-your-project -- --template react
cd <your-new-project-directory>
npm install react-router
```

### 2️⃣ TailwindCSS Setup

```bash
npm install tailwindcss @tailwindcss/vite
npx tailwindcss init
```
### 3️⃣ DaisyUI Installation
```bash
npm i -D daisyui@latest
```
### ✏️ Configure vite.config.js
```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
})

```
### 4️⃣ Setup index.css
```css
@import "tailwindcss";
@plugin "daisyui";
```
### 6️⃣ Basic React Router Setup
```js
import { createBrowserRouter } from "react-router";
import RootLayout from "../layouts/RootLayout";
import Home from "../pages/Home/Home/Home";

export const router = createBrowserRouter([
  {
    path: "/",
    Component: RootLayout,
    children: [
        {
            index: true,
            Component: Home
        }
    ]
  },
]);
```
### 📤 Client Side Deployment

Follow the official deployment guide here:

🔗 [Client Deploy Guide](https://github.com/ProgrammingHero1/Job-Portal-Resources/blob/main/client-deploy.md)
