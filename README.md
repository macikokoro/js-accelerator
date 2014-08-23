Initialize git repo

```
git init
touch .gitignore
echo "node_modules/" >> .gitignore
git add .
git commit -m "add package.json and .gitignore"
```
npm init// package.json

for express add dependencies to package.json

```
{
  "name" : "hello-express",
  "description" : "a hello world web application written in express",
  "version" : "0.0.1",
  "dependencies" : {
    "express" : "^4.0"
  }
}
```

npm install

create express server

```
var express = require('express');
var http    = require('http');

var app = express();

app.get('/', function(req, res){
  res.send('hello world!');
});

var server = http.createServer(app);
server.listen(3000, function(){
  console.log('the server is running on port 3000');
});
```
