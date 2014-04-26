superspawn
=======

###### A Node.js spawn command that works on Windows too.

Original source from Apache Cordova's superspawn.js by Andrew Grieve.

##### Windows extras
- Sets '/c' flag so files other than `.exe` can be run. Supported: `.exe, .cmd, .bat, .js, .vbs`
- Sets '/s /c' flags so commands (and paths) containing spaces or quotes are parsed correctly.

See [this Node bug](https://github.com/joyent/node/issues/2318).


## Install
```js
npm i --save superspawn
```

## Usage

Superspawn uses the same signature as the native child_process.spawn. But instead of a reference to the child process it returns a [Q.promise](https://github.com/kriskowal/q#readme).

```js
var spawn = require('superspawn').spawn

/**
 * @param {string} cmd
 * @param {string[]} [args]
 * @param {opts} [opts]
 * @returns {Q.promise} - Returns a promise that succeeds only for return code = 0.
 *
 * @typedef {Object} opts
 * @property {boolean} [printCommand=false] - Whether to log the command
 * @property {string} stdio -
 *     'default' is to capture output and returning it as a string to success (same as exec).
 *     'ignore' means don't bother capturing it.
 *     'inherit' means pipe the input & output. This is required for anything that prompts.
 * @property {object} env - Map of extra environment variables.
 * @property {string} cwd - Working directory for the command.
 */
spawn(cmd, args, opts)
  .catch(function(err) {}) // rejectedHandler
  .then(function(stdout) {}) // resolvedHandler
;
```

## Todo
- [ ] Write tests
