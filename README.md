# Standard JavaScript

This is a TL;DR of the [standard] and [semistandard] JavaScript rules. For more detailed explanations, see standard's [rules documentation](https://github.com/feross/standard/blob/master/RULES.md).

[standard]: https://github.com/feross/standard
[semistandard]: https://github.com/Flet/semistandard

> [![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)
> [![js-semistandard-style](https://cdn.rawgit.com/flet/semistandard/master/badge.svg)](https://github.com/Flet/semistandard)

## Rules

* **Use 2 spaces** for indentation.

  ```js
  function hello (name) {
    console.log('hi', name)
  }
  ```
  
* **Use single quotes for strings** except to avoid escaping.

  ```js
  console.log('hello there')
  $("<div class='box'>")
  ```

* **No unused variables.**

  ```js
  function myFunction () {
    var result = something()   // ✗ avoid
  }
  ```
  
* **Add a space after keywords.**

  ```js
  if (condition) { ... }   // ✓ ok
  if(condition) { ... }    // ✗ avoid
  ```
  
* **Add a space after function names.**

  ```js
  function name (arg) { ... }   // ✓ ok
  function name(arg) { ... }    // ✗ avoid
  
  run(function () { ... })      // ✓ ok
  run(function() { ... })       // ✗ avoid
  ```
  
* **Always use** `===` instead of `==`.<br>
  Exception: `obj == null` is allowed to check for `null || undefined`.

  ```js
  if (name === 'John')   // ✓ ok
  if (name == 'John')    // ✗ avoid
  ```
  
  ```js
  if (name !== 'John')   // ✓ ok
  if (name != 'John')    // ✗ avoid
  ```

* **Infix operators** must be spaced.

  ```js
  // ✓ ok
  var x = 2;
  var message = 'hello, ' + name + '!';
  ```

  ```js
  // ✗ avoid
  var x=2;
  var message = 'hello, '+name+'!';
  ```

* **Commas should have a space** after it.

  ```js
  // ✓ ok
  var list = [1, 2, 3, 4];
  function greet (name, options) { ... }
  ```

  ```js
  // ✗ avoid
  var list = [1,2,3,4];
  function greet (name,options) { ... }
  ```

* **Keep else statements** in the same line as its curly braces.

  ```js
  // ✓ ok
  if (condition) {
    // ...
  } else {
    // ...
  }
  ```

  ```js
  // ✗ avoid
  if (condition) {
    // ...
  }
  else {
    // ...
  }
  ```

* **For multi-line if statements,** use curly braces.

  ```js
  // ✓ ok
  if (options.quiet !== true) console.log('done')
  ```

  ```js
  // ✓ ok
  if (options.quiet !== true) {
    console.log('done')
  }
  ```

  ```js
  // ✗ avoid
  if (options.quiet !== true)
    console.log('done')
  ```

* **Always handle the** `err` function parameter.

  ```js
  // ✓ ok
  run(function (err) {
    if (err) throw err
    window.alert('done')
  })
  
  // ✗ avoid
  run(function (err) {
    window.alert('done')
  })
  ```
   
* **Always prefix browser globals** with `window.`.<br>
  Exceptions are: `document`, `console` and `navigator`.

  ```js
  window.alert('hi')   // ✓ ok
  ```

## Semicolons

These rules are enforced for [standard], but are not imposed in [semistandard].
  
* No semicolons. (see: [1](http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding), [2](http://inimino.org/%7Einimino/blog/javascript_semicolons), [3](https://www.youtube.com/watch?v=gsfbh17Ax9I))

  ```js
  window.alert('hi')   // ✓ ok
  window.alert('hi');  // ✗ avoid
  ```

* Never start a line with `(` or `[`. This is the only gotcha with omitting semicolons. (see: [1](https://github.com/feross/standard/blob/master/RULES.md#automatic-semicolon-insertion-asi))

  ```js
  ;(function () {
    window.alert('ok')
  }())
  ```
  
