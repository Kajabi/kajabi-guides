# Javascript Style Guide

Currently a WIP.

Loosely based on [Thoughtbot](https://github.com/thoughtbot/guides/tree/master/style/javascript) and
[Airbnb's Javascript Style Guide](https://github.com/airbnb/javascript/tree/master/es5).


## Formatting:

* Use soft tabs set to 2 spaces.

* In control statements (`if`, `while`), place 1 space before leading braces and opening parenthesis.

* Leave a blank line after blocks before the next statement.

* Use semicolons at the end of each statement.

* Avoid trailing whitespace.

* Use one `var` declartion per variable.

* Use braces with all multi-line blocks.

* Put `else` on the same line as your `if` block's closing brace.

* Use dot notation when accessing properties e.g. `var isJedi = luke.jedi`.


## Syntax:

* Use literal syntax for instantiation e.g. `var items = {};

* Use function declarations instead of function expressions.

* Use `===` and `!==` over `==` and `!=`.

* Prefer single quotes.


## Naming:

* Use `camelCase` for objects, functions and instances

* Use `PascalCase` when naming constructors or classes.


## Comments:

* Avoid superfluous comments.


## Misc:

* Assign variables at the top of their scope. Avoids assignment hoisting issues.

* Pass a hash instead of a raw value when attaching data payloads to events.

* Prefix jQuery object variables with a `$`.

* Write code in hopes your mom could read it -Andy Huynh

