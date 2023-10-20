Node js Commands
  To Install 
  npm init -y
  npm i express mysql2 body-parser express-validator bcryptjs jsonwebtoken
  npm i -D nodemon
  replace  in Package.json  test block
  "start": "nodemon index.js"

  Create index.js file 

  ********** index.js file************
  
const express = require('express');
const bodyParser = require('body-parser');
const app = express();
const ports  = process.env.port || 3000;
app.use(bodyParser.json());

app.use((req,res,next)=>{

    res.setHader('Acess-Control-Allow-Origin','*');
    res.setHader('Acess-Control-Allow-Methods', 'GET,POST,PUT,DELETE');
    res.setHader('Acess-Control-Allow-Header','Content-Type,Authorization');
    next();


} );
app.listen(ports,()=> console.log(`Listening on port ${ports}`))


Add Folder config ==>> Add File config.json

**************************config.json******************************************

{
    "host":"localhost",
    "user":"root",
    "database":"posts",
    "password":"password"

    
}


