GET: Used to request data. Matching and handling a specific route.
POST: Used to insert data in your database.
PUT: Used to update de data in your database.
DELETE: Deleta data.


# Start a node.js app

---> npm init
---> npm install express


---> ignore node_modules


---> create app.js:

    const express = require("express");

    const app = express();

    const port = process.env.PORT || 3000;
  
  
---> In app.js create a simple route with GET

    app.get("/", (req, res) => {
      res.send("Welcome to my API!");
    });

    app.listen(port, () => {
      console.log(`Running on port ${port}`);
    });

---> npm install nodemon 
---> add in package.json:

    "start": "nodemon app.js"
    
---> add in package.json the nodemon configuration:

    "nodemonConfig": {
        "restartable": "rs",
        "ignore": [
          "node_modules/**/node_modules"
        ],
        "delay": "2500",
        "env": {
          "NODE_ENV": "development",
          "PORT": 4000
        }
        
       
---> create a router in app.js:

    const bookRouter = express.Router();
    ...
    bookRouter.route("/books")
