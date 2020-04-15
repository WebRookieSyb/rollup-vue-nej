# rollup-to-nej

***Transform _.js to _.js with nej define***

If you want to use Vue or Vue Jsx, you still need a \*.js to be entry file.

You can see how to use it in the examples file

## Usage

```sh
npm install

* build
roll build vue -i *** -o *** -s ***=***,***=***

* watch
roll dev vue -i *** -o *** -s ***=***,***=***
```

## Support config

generate config file by:

```
roll init 
```


.rolltonejrc.json
use include to set real pack file

```json
{
  "input": "raw",
  "output": "src",
  "alias": {
    "@nej": "./src",
    "vueSrc": "../../",
    "***": "***"
  },
  "include": [
    "raw/button",
    "raw/tab/index.js"
  ]
}
```

## Support api

```js
const doRollup = require("rollup-to-nej");
doRollup.build("vue", {
  input: "raw",
  output: "src",
  alias: {
    "@nej": "./src",
    "vueSrc": "../../",
    "***": "***"
  }
});
```

---


## Config 

### alias

You can use alias to avoid public modules being packaged. 
use like `-s @nej=./src,vueSrc=../../` . Please note that if you use `@` , you can not use like `@**` or `*@*`

### removeComments

Remove comments after package. Use it in cli by `--removeComments`, or in params as `removeComments:true`

### externalHelpers

If you do not wish the babel helpers to be included in your bundle at all (but instead reference the global babelHelpers object), you may set the externalHelpers option to true and import babel-runtime in you code. Use it in cli by `--externalHelpers`, or in params as `externalHelpers:true`