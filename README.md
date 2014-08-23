## Serving a static HTML page with express
------------------------------------------

Modify server.js

```
var express = require('express');
var http    = require('http');

var app = express();

app.use(express.static(__dirname + '/public'));

var server = http.createServer(app);
server.listen(3000, function() {
  console.log('the server is listening on port 3000');
});
```
The server now serves any files located in the public directory.

mkdir public

touch public/index.html

```
<!doctype html>
<html lang="en">
    <head>
        <meta charset="UTF-8"/>
        <title>Hello World Express</title>
    </head>
    <body>
      Hello World from an html document!
    </body>
</html>
```
Run the server with node server.js

open localhost:3000

the page reads Hello World from an html document!

ctrl + c to stop server again
