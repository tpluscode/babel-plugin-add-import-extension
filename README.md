# babel-plugin-add-import-extension
A plugin to add extensions to import declarations, is very useful when you use Typescript with Babel and don't want to explicity import `.js` modules.

A normal import using Typescript:
```js
import { add, double } from './lib/numbers'
```
will be converted to:
```js
import { add, double } from './lib/numbers.js'
```

Is possible to set the extension when you set the plugin on your babel config file:
```js
plugins: ['babel-plugin-add-import-extension'] // defaults to .js extension

plugins: [
    ['babel-plugin-add-import-extension', 'jsx'] // will add jsx extension
  ]
```

Remember that this plugin will not override extensions and will only add the choosed extension, so if your imports already has extensions it will add another one because this plugin is really dummy :)

What this plugin does is to compare all imported modules with your `package.json` and if your module is not on your `package.json` it will consider that is a project/local module and add the choosed extension, so for node modules it don't add any extension.

I made this plugin for personal use on my [typescript boilerplate](https://github.com/karlprieb/typescript-web-starter), but if a lot of people start to use I can add tests and some documentation ;)