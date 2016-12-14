# rollup-error-example

Illustrate a (possible) problem with rollup.

Am I missing something? Here is a project with a minimal configuration to
reproduce the "problem" I running into. The problem seems only to be extraneous
command-line logging without affecting the bundle itself; i.e. the bundle is
created correctly and accurately.

This project displays the output:

```
node_modules/nan
resolve failed:  { Error: Cannot find module 'babel-runtime'
    at Function.Module._resolveFilename (module.js:472:15)
    at Function.requireRelative.resolve (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/require-relative/index.js:30:17)
    at resolve (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/modify-babel-preset/lib/serialize.js:25:26)
    at findAndRemove (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/modify-babel-preset/lib/serialize.js:67:11)
    at /Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/modify-babel-preset/lib/serialize.js:111:13
    at Array.map (native)
    at loadPreset (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/modify-babel-preset/lib/serialize.js:103:29)
    at module.exports (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/modify-babel-preset/index.js:97:19)
    at Object.<anonymous> (/Users/jkalis/Pro/QL/WebCore/luxui/rollup-testing/node_modules/babel-preset-es2015-rollup/index.js:3:18)
    at Module._compile (module.js:573:32) code: 'MODULE_NOT_FOUND' } babel-runtime
```

The command(s) to reproduce this are:

  - `npm run bundle`, or
  - `./node_modules/.bin/rollup -c rollup.js`

In other projects I have similar issues with additional resolve "failures" that
seem not to affect the bundle itself. Is this something that is easily fixable?
