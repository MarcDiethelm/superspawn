superspawn
=======

###### A Node.js spawn command that works on Windows too.

Original source from Apache Cordova's superspawn.js by Andrew Grieve.

## Install
```js
npm i --save superspawn
```

## Usage
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
  .catch(rejectedHandler)
  .then(resolvedHandler)
```

## Todo
- [ ] Write tests
