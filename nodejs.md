# node.js

node.js can be downloaded from the [_node.js_ website](https://nodejs.org/) for Windows, macOS, Linux and other platforms. If you wish to use this resource, you will need to download it.

Having a understanding of [javascript programming](https://www.w3schools.com/js/default.asp) concepts will be beneficial.

## What is it?
As found on the [_node.js_](https://nodejs.org/en/about) About page:
>As an asynchronous event driven JavaScript runtime, Node is designed to build scalable network applications. Upon each connection the callback is fired, but if there is no work to be done, Node will sleep.

_node.js_ is designed to be a server run package which takes advantage of the javascript syntax. _node.js_ makes use of [modules](https://nodejs.org/api/modules.html) to help, build, and create web development, server-side components and compilers to name a few.

Depending on the depth you wish to use _node.js_, their [API Documentation](https://nodejs.org/api/) will be a great asset.

## Who is using _node.js_?
* Netflix
* Uber
* Paypal
* eBay

### Activity

_node.js_ can run through a packaged `node.exe` file which is a command line shell that can run javascript.

What appears when you run the following blocks of code through `node.exe`?

`5`

`var x = 5` then call `x`

`x*3`

`for (var i = 0; i<10; i++) {
  console.log(i);
}`

`var d = new Date()` then call `d`

Now try and run code just looks for elements such as:

`document.getElementbyId('h1')`

What happened and why did it happen? `node.exe` is essentially javascript without the browser operations. There is no document (HTML) for `node.js` to target to retrieve this information.

## Running in Terminal
When running `node.js` through a Command Line or Terminal, you can access applications you have written and saved as javascript.

This can be done by locating the folder which contains for `.js` file and using a `node` prefix when typing into Command line.

>Example
>
>`node app.js` or simply `node app`.

### Activity

Copy the below code and save it as to your computer to run through Command Line.

app1.js
```javascript
console.log('Hello World');
```
This should return the string in Command Line.

---
You can also run javascript functions through this method.  

app2.js
```javascript
function greeting(greet) {
  console.log(greet);
}

greeting('Hello again World');
```
The whole function should be run then returned.

---

_NPM_ - _node.js_ Package Manager is used to install `node.js` modules.

`package.json` - This is *important*. This is created by running `npm init` in Command Line. It will should be placed in the root of your application so _NPM_ knows how the application is structured. When running `npm init`, you are going to be prompted to enter some information. As an example the first one to show up is `name` with a name in brackets beside it. This name in brackets is a default name and all the titles will have a default or no input. To select the default or leave blank, just press `enter`.

These areas fields are: `name`, `version`, `description`, `entry point`, `test command`, `git repository`, `keywords`, `author`, `license`

`entry point` would be most important one to get correct. This is the main file that `package.json` connects with. This is generally a `.js` file.

Once completed, this information will published into a `package.json` file.

**_If `npm init` does not run you may need to try `sudo npm init` instead._**

Using [ES2015 (or ES6) Syntax](http://es6-features.org/), we can create a local server. Using a few modules from within the _node.js_ package, we can set this up very simply.

More information about ES2015/ES6 can be found [here](https://css-tricks.com/lets-learn-es2015/) and [here](https://www.w3schools.com/js/js_es6.asp) explaining ES2015 Syntax.

app3.js
```javascript
// node module 'require' (core)
const http = require('http');

// loop address
const hostname = '127.0.0.1';

const port = 3000;

// request and response
const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-type', 'text/plain');
  res.end('Hello World yet again');
});

server.listen(port, hostname, () => {
  console.log('Server started on port '+port);
});
```

Once this has been run on Command Line, go to http://127.0.0.1:3000 and see what happens.

If done correctly, this is the result of setting up a simple local server on your computer.

---
In this example `fs` ([file system](https://nodejs.org/api/fs.html#fs_fs_readfile_path_options_callback)) has been added. This is used your accessing files.

Copy both `app4.js` and `index.html` for this exercise make sure they are in the same folder.

app4.js
```javascript
// node module 'require' (core)
const http = require('http');

// file system module
const fs = require('fs');

// loop address
const hostname = '127.0.0.1';

const port = 3000;

fs.readFile('index.html', (err, html) => {
  if (err) {
    throw err;
  }

  // request and response
  const server = http.createServer((req, res) => {
    res.statusCode = 200;

    res.setHeader('Content-type', 'text/plain');
    res.write(html);
    res.end();
  });

  server.listen(port, hostname, () => {
    console.log('Server started on port '+port);
  });

});
```

index.html
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Test HTML</title>
  </head>
  <body>
    <h1>Guess What?</h1>
    <h2>It's me, 'Hello World'</h2>
  </body>
</html>
```

Once loaded, have a look at how the webpage looks. Why is that?

What if you changed `res.setHeader('Content-type', 'text/plain')` to `res.setHeader('Content-type', 'text/html')`?

Restart your server through Command Line (`Ctrl + C` and run the app again), and reload your webpage ( http://127.0.0.1:3000 ). Has it changed?
