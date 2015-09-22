# Ruby Style Guide

This is a brand new work in progress.  Do not rely on this yet.

Based on [Chris Neukirchen's Ruby Style
Guide](http://github.com/chneukirchen/styleguide/).

## Formatting:

* Use 2 space indent, no tabs.

* Use spaces around operators, after commas, colons and semicolons,
  around `{` and before `}`.

* Avoid spaces after `(`, `[` and before `]`, `)`.

* Use one space before statement modifiers (postfix
  `if`, `unless`, `while` and `until`).

* Indent `when` as deep as `case`.

* Use an empty line between `def`s.

* Use empty lines to break up a long method into logical paragraphs.

* Try to keep lines fewer than 80 characters when possible.

* Avoid trailing whitespace.


## Syntax:

* Use `def` with parentheses when there are arguments.

* Use `&&` and `||` for boolean expressions.

* Prefer ! over not.

* Use `{...}` for single-line blocks and `do...end` for multi-line blocks.

* Avoid `return` where not required.

* Avoid line continuation (`\`) where not required.

* Avoid using self explicitly anywhere except class methods `def self.method`
  and assignments `self.attribute = "value"`

* Using the return value of = is okay: if v = array.grep(/foo/) ...

* Prefer `"` for all strings, even non-interpolated ones.

* Use `%Q{}` for strings that would require lots of `\"` escaping

* Prefer string interpolation `#{}` or array joining `%w[foo bar].join(", ")
  over inline `<<` or `concat`

* Use of `||=` is ok.

* Break up a chain of enumerable calls like `map` `select` `reject` into
  separate lines when it is clearer.

* Prefer &:method_name to { |item| item.method_name } for simple method calls.

* Prefer `name: value` style hash symbols over `:name => value`, especially for
  one liners.

* Use `:name => value` for large hashes when symbol keys are preferred and
  you wish to align on the hashrocket `=>` for readability.


## Naming:

* Use `snake_case` for methods.

* Use `CamelCase` for classes and modules.

* Use `SCREAMING_SNAKE_CASE` for other constants.

* Use `_` or names prefixed with `_` for unused or private variables.

* Prefer map over collect, detect over find, and select over find_all.

* Avoid bang (!) method names when a non-bang method doesn't already exist.

* Use ? suffix for predicate methods.

## Comments:

* Comments longer than a word are capitalized and use punctuation.

* Avoid superfluous comments.

* Use yardoc formatting if you are making API comments.

## Misc:

* Prefer writing methods that are less than 10 lines.

* Avoid writing methods that receive more than 3 parameters.

* Use `def self.method` to define singleton methods.

* Avoid needless metaprogramming.

* Avoid a catch-all `rescue` when possible.

* Don't use `case` without an `else` branch.

* Avoid `unless` `else` conditional pairings.

## General:

* Do not mutate arguments unless that is the purpose of the method.

* Avoid monkeypatching. Especially avoid monkeypatching core classes like `String`,
  `Fixnum`, `Array`, `Hash`, etc.

* Keep the code simple.

* Don't overdesign.

* Be consistent.

* Use common sense.
