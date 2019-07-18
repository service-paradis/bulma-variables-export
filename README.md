# bulma-variables-export
Library exporting Bulma sass variables which can be used in Webpack project. Bulma variables can be imported into any Javascript/Typescript project.

<img src="https://raw.githubusercontent.com/jgthms/bulma/master/docs/images/bulma-banner.png" width="600" height="315" class="center">

- [bulma-variables-export](#bulma-variables-export)
  - [Quick install](#Quick-install)
    - [NPM](#NPM)
  - [Webpack Setup](#Webpack-Setup)
  - [import](#import)
  - [Usage](#Usage)

## Quick install

### NPM
```sh
npm install bulma-variables-export
```

## Webpack Setup
When working with Javascript/Typescript and Sass, sometimes you want to be able to share variables defined in stylesheets with your code. This is actually pretty simple with Webpack.

First make sure webpack is set up to import scss:
```javascript
// webpack.config.js
module.exports = {
  ...
  module: {
    rules: [{
      test: /\.scss$/,
      use: [{
        loader: "style-loader" // creates style nodes from JS strings
      }, {
        loader: "css-loader" // translates CSS into CommonJS
      }, {
        loader: "sass-loader" // compiles Sass to CSS
      }]
    }]
  }
};
```

## import
Now you can import any Bulma variables in your project.

You can import every variables using:
```javascript
import variables from 'bulma-variables-export'
```

You can also import specific set of variables using:
```javascript
import initialVariables from 'bulma-variables-export/sass/initial-variables'
import derivedVariables from 'bulma-variables-export/sass/derived-variables'
import controlsVariables from 'bulma-variables-export/sass/controls-variables'
```

## Usage
Usage in your code is very simple. The variables name are exactly defined as Bulma but in camelCase.
```javascript
import variables from 'bulma-variables-export'
// *OR*
// variables = require('bulma-variables-export');

console.log(variables.black)
console.log(variables.familyMonospace)
console.log(variables.weightMedium)
```
