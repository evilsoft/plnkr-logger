## Plunker HTML Logger

When showing off code inside of an embedded context, sometime the browser's console just
is not enough. It can get confusing depending on what else on the page is also using
the console. This library extends the `console.log` calls to also write formatted HTML
to a specified target.

When included in an embedded project, `console.log` will be replaced with the logger
function and all output will appear both in the target element as well as in the
console. The log that appears in the console will of course, not contain any formatting
and will behave just like a normal `console.log`.

A `logger` function will also be added to the provided root, for :corn:sistancy with
any videos you may be creating.

## Usage
The `logger.js` file holds all the code inside of an Immediately Invoked Function
Expression (IIFE). The configuration for the logger is passed to the IIFE using the
following format:

```javascript
{
  root: window,     // where the `logger` function is added
  selector: 'body', // selector for the element to append the entries
  fontSize: '28px', // base font-size for entries
  colors: {
    background: 'transparent',  // background
    foreground: 'gray',         // base for non-formatted text
    label: 'blue',              // logger label
    nil: 'green',               // undefined and null
    number: 'violet',           // all numbers
    string: 'red',              // all string values
    key: 'blue',                // object keys
    boolean: 'green'            // booleans
  }
}
```

Once configured, you can create a minimized version of the lib for inclusion in
your embedded context. To do this you must make sure that all dependencies are
brought down. This can be done by running the following from the project folder:

```
$ npm install
```

Now that all dependencies are brought in, you have everything you need to create
a `logger.min.js` file that will be placed in your project root folder. To kick off
the build run the following in your project folder:

```
$ npm run build
```
