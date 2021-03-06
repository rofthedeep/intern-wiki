*New in Intern 1.3*

Intern allows `client.html`/`client.js` to load and use alternative AMD loaders. This is useful in the case that you are using a specific feature that only exists in a particular loader (most commonly, RequireJS’s `shim` functionality, which is normally implemented via [loader plugin](https://github.com/tbranyen/use.js) in other loaders).

To use an alternative loader, simply add the `useLoader` configuration option to your Intern configuration file. Two keys are currently supported, `host-node` and `host-browser`, which correspond to the loader that will be used in Node.js and in the browser, respectively.

`host-node` should be a standard Node.js module ID, like `dojo/dojo`, or `requirejs`. The module will be resolved using the standard Node.js module resolution system. **Note that you will need to add the `intern/node_modules` directory to your `NODE_PATH` environment variable. This restriction will be lifted in Intern 1.5.**

`host-browser` should be a path to a script file, relative to `client.html`, like `node_modules/dojo/dojo.js`, or `../../bower_components/requirejs/require.js`. The module will be loaded using script injection.

You may omit either key, in which case the default (Dojo 2) loader will be used instead.

Additional information about `useLoader`, including an example, is available in the [[Configuring Intern]] documentation.