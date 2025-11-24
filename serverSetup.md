## 🖥️ Server Side Project Setup(Express + MongoDB + Vercel Deployment)

### 1️⃣ Initialize Node.js Project

  ```bash
cd <your-project-directory>
mkdir <your-server-folder-name>
cd <your-server-folder-name>
npm init -y
npm install express cors mongodb dotenv
```
### 2️⃣ Basic Server Setup with MongoDB

  ```js
const express = require("express");
const cors = require("cors");
const { MongoClient, ServerApiVersion } = require("mongodb");
require("dotenv").config();

const app = express();
const port = process.env.PORT || 5000;

// Middleware
app.use(cors());
app.use(express.json());

const uri = `mongodb + srv://${process.env.DB_USER}:${process.env.DB_PASS}@cluster0.wi4y4.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0`;


const client = new MongoClient(uri, {
  serverApi: {
    version: ServerApiVersion.v1,
    strict: true,
    deprecationErrors: true,
  },
});

async function run() {
  try {
    await client.connect();
    console.log("✅ Connected to MongoDB!");

    // Get a reference to the desired collection in the database
    const collection = client.db("yourDatabaseName").collection("yourCollectionName");
    
    // You can add your API routes here
    app.get("/data", async (req, res) => {
      const result = await collection.find().toArray();
      res.send(result);
    });

  }
  catch (error) {
    console.error("❌ MongoDB connection error:", error);
  }
}

//run
run().catch(console.dir);

app.get("/", (req, res) => {
  res.send("Server is up and running!");
});

app.listen(port, () => {
  console.log(`Server is listening on port ${port}`);
});

```
### 📤 Server Side Deployment

Follow the deployment guide here:

🔗 [Server Deploy Guide](https://github.com/ProgrammingHero1/Zap-shift-Resources/blob/main/server-deploy.md)
