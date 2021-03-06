# LightScript

### JavaScript, with cleaned-up syntax and a few conveniences.

A superset of ES7 with JSX and Flow,
implemented as a fork of Babel’s parser wrapped in a Babel plugin. Built to make programmers a little more productive.

See [lightscript.org](http://lightscript.org) for example code
and language reference documentation. A quick taste:

```coffee
fizzBuzz(n = 100) ->
  [for i from 1 thru n:
    if i % 3 == 0 and i % 5 == 0:
      "fizzbuzz"
    elif i % 3 == 0:
      "fizz"
    elif i % 5 == 0:
      "buzz"
    else:
      i
  ]
```


### Language Features

In addition to all all ES7, JSX, and Flow features:

- (Optional) Significant Indentation
- Implicit Returns
- If Expressions
- Auto const
- Async/Await shorthand
- Safe-Await
- Readable Operators (or, and, ==, etc)
- Bound Methods
- Commaless Objects and Arrays
- Automatic Semicolon Insertion that always works
- Array Comprehensions
- Array-based for-loops
- Range-based for-loops
- a few others

Reference documentation is available at [lightscript.org](http://lightscript.org),
or in Markdown format [here](https://github.com/lightscript/lightscript.org/blob/master/pages/docs/docs.md). Tests for all features can be seen
[here](https://github.com/lightscript/babylon-lightscript/tree/lightscript/test/fixtures/lightscript)
and [here](https://github.com/lightscript/babel-plugin-lightscript/tree/master/test/fixtures).


### Project Structure

"LightScript" is split across multiple repos:

- **The Parser**: [babylon-lightscript](https://github.com/lightscript/babylon-lightscript)
  - The core of most of the language.
  - Because it is a fork, the repo would not be easily pulled into a monorepo.
- **The Babel Plugin**: [babel-plugin-lightscript](https://github.com/lightscript/babel-plugin-lightscript)
  - Rewrites a "LightScript AST" into a "JavaScript AST".
  - The core of what you need to use LightScript.
- **The Babel Preset**: [babel-plugin-lightscript](https://github.com/lightscript/babel-plugin-lightscript)
  - Provides the rest of ES7 for ES6 environments, as well as runtime typechecking.
- **The Sublime Text Package**: [lightscript-sublime](https://github.com/lightscript/lightscript-sublime)
  - Provides syntax highlighting, albeit somewhat hackily.
  - Not yet installable from Package Control; blocking on https://github.com/wbond/package_control_channel/pull/6163.
- **The Atom Package**: [lightscript-atom](https://github.com/lightscript/lightscript-atom)
  - Based on the Sublime Package.
  - Live on `apm`, you can install it today.
- **The Website**: [lightscript.org](https://github.com/lightscript/lightscript.org)
  - In addition to powering lightscript.org, it's also the best example of LightScript code in use.
    Hopefully that changes soon.

For now, the issue tracker on this repo should be used for bug reports and feature requests.
