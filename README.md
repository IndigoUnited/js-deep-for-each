# deep-for-each [![Build Status](https://travis-ci.org/IndigoUnited/js-deep-for-each.svg?branch=master)](https://travis-ci.org/IndigoUnited/js-deep-for-each)

Recursively iterates over collections (arrays and objects).


## Installation

`$ npm install deep-for-each` - `NPM`   
`$ bower install deep-for-each` - `bower`

The browser file is named `index.umd.js` which supports CommonJS, AMD and globals (`deepForEach`).
If you want to run this module on old browsers, you must include [es5-shim](https://github.com/es-shims/es5-shim).


## Usage

The example bellow is based on `nodejs`.

```js
var deepForEach = require('deep-filter');

deepForEach({
    prop1: 'foo',
    prop2: ['foo', 'bar'],
    prop3: ['foo', 'foo'],
    prop4: {
        prop5: 'foo',
        prop6: 'bar'
    }
}, function (value, prop, subject, path) {
    // prop is an array index or an object key
    // subject is either an array or an object
    // path is the iteration path, e.g.: 'prop2[0]' and 'prop4.prop5'

    console.log(path + ':', value);
});
```

Running the example above will print:

```
prop1: foo
prop2: [ 'foo', 'bar' ]
prop2[0]: foo
prop2[1]: bar
prop3: [ 'foo', 'foo' ]
prop3[0]: foo
prop3[1]: foo
prop4: { prop5: 'foo', prop6: 'bar' }
prop4.prop5: foo
prop4.prop6: bar
```


## Tests

`$ npm test`


## License

Released under the [MIT License](http://www.opensource.org/licenses/mit-license.php).
