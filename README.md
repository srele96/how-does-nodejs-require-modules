# How does NodeJS require modules

Step-by-step solution. Runnable example with explanation of how NodeJS requires modules.

## 1. Create an entry point and require a module

To learn, we need to start as if we were to create an app. To start, I want to require a module that I'm going to use.

To do this, we need a starting point. I will create an entry point JavaScript file called app.

I want to use an imaginary module called app-maker. Let's require it.

```js
// app.js
const appMaker = require('app-maker');
```

Now I will run the file with the following command:

`node app.js`

Oops! An error.

`Error: Cannot find module 'app-maker'`

## 2. Solve the error

Have you ever run the npm install command? Perhaps you made a web server application using express?

If the answer is yes, you are familiar with the node modules directory.

How did you require one of those modules? Did it look something like this?

```js
const express = require('express');
```

Maybe this?

```js
const lodash = require('lodash');
```

We required an app maker module the same way. Where should it be? In node modules.

1. Create node modules directory.
2. Create a folder inside and call it app-maker.
3. Create a file inside the app-maker and call it index.js.
4. Add content to index.js.

```js
module.exports = function appMaker() {
  return 'This is an app maker'
}
```

Run the app.

`node app.js`

There isn't any error now.

## 3. Use the app maker

Let's use the module to verify that everything works.

Add the following code to the app.js and run it.

```js
// app.js
const appMaker = require('app-maker');

console.log(appMaker());
```

You should see printed text. That should give you entry-level insight into how NodeJS resolves required modules.

With all that info, we can conclude the following:

1. Running npm install downloads some code from the web.
2. That code may use the same format we did.
3. The node modules folder contains modules like ours that someone else created.
