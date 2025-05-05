Server deploy : https://github.com/ProgrammingHero1/Job-Portal-Resources/blob/main/server-deploy.md
Client Side deploy : https://github.com/ProgrammingHero1/Job-Portal-Resources/blob/main/client-deploy.md

React Router:
-------------------------------------------------------------------
cd <your new project directory>
npm install react-router-dom 
npm install localforage match-sorter sort-by 
-------------------------------------------------------------------
Tailwind: 
-------------------------------------------------------------------
npm install -D tailwindcss@3
npx tailwindcss init
-------------------------------------------------------------------
DaisyUI: 
-------------------------------------------------------------------
npm i -D daisyui@latest
-------------------------------------------------------------------
tailwind.config.js :
-------------------------------------------------------------------
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [require('daisyui'),],
}
-------------------------------------------------------------------
index.css :
-------------------------------------------------------------------
@tailwind base;
@tailwind components;
@tailwind utilities;
-------------------------------------------------------------------
eslint.config.js :
-------------------------------------------------------------------
node: true,



-------------------------------------------------------------------
import {
  createBrowserRouter,
  RouterProvider,
} from "react-router-dom";


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









--------------BACKEND SERVER----------------------------

1. cd \Projects
2. mkdir project name
3. cd project name
4. npm init -y
5. npm install express cors mongodb dotenv



----------------MONGODB+SERVER---------------------------
const express = require('express');
const app = express();
const cors = require('cors');
const port = process.env.PORT || 5000;
const { MongoClient, ServerApiVersion } = require('mongodb');
require('dotenv').config();

//middleware
app.use(cors());
app.use(express.json());

const uri = `mongodb+srv://${process.env.DB_USER}:${process.env.DB_PASS}@cluster0.wi4y4.mongodb.net/?appName=Cluster0`;

// Create a MongoClient with a MongoClientOptions object to set the Stable API version
const client = new MongoClient(uri, {
    serverApi: {
        version: ServerApiVersion.v1,
        strict: true,
        deprecationErrors: true,
    }
});

async function run() {
    try {
        await client.connect();
        console.log("Connected to MongoDB!");

        const database = client.db("yourDatabaseName");
        const collection = database.collection("yourCollectionName");

    } catch (error) {
        console.error("MongoDB connection error:", error);
    }
}

run();
app.get('/', (req, res) => {
    res.send('Server is up and running!');
});

// Common log message for server start
app.listen(port, () => {
    console.log(`Server is listening on port ${port}`);
});


