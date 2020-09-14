# bulma-variables-export

Library exporting Bulma sass variables which can be used in Webpack project. Bulma variables can be imported into any Javascript/Typescript project.

![Bulma.io](https://raw.githubusercontent.com/jgthms/bulma/master/docs/images/bulma-banner.png)

- [bulma-variables-export](#bulma-variables-export)
  - [Quick install](#quick-install)
    - [NPM](#npm)
  - [Webpack Setup](#webpack-setup)
  - [import](#import)
  - [Usage](#usage)

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
import initialVariables from 'bulma-variables-export/sass/initial-variables.scss'
import derivedVariables from 'bulma-variables-export/sass/derived-variables.scss'
import controlsVariables from 'bulma-variables-export/sass/controls-variables.scss'
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
