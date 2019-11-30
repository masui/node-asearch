# Node Asearch
ambiguity text search for JavaScript

[![Build Status](https://travis-ci.org/shokai/node-asearch.png?branch=master)](https://travis-ci.org/shokai/node-asearch)

- https://github.com/shokai/node-asearch
- https://npmjs.org/package/asearch


## Install

    $ npm install asearch

## Usage

```coffee
Asearch = require 'asearch'

a = new Asearch 'abcde'

console.log a.match 'abcde'    # => true
console.log a.match 'AbCdE'    # => true
console.log a.match 'abcd'     # => false
console.log a.match 'abcd', 1  # => true
console.log a.match 'ab de', 1 # => true
console.log a.match 'abe', 1   # => false
console.log a.match 'abe', 2   # => true
```

### Typo

```coffee
a = new Asearch 'cheese burger'

console.log a.match 'cheese burger'   # => true
console.log a.match 'chess burger'    # => false
console.log a.match 'chess burger', 2 # => true
console.log a.match 'chess', 2        # => false
```

<img src="http://gyazo.com/cbbabaf5f48f99a236b129b3df804081.png">


### 2 byte chars

```coffee
a = new Asearch '漢字文字列'

console.log a.match '漢字文字列' # => true
console.log a.match '漢字文字烈' # => false
console.log a.match '漢字文字烈', 1 # => true
```

### for browser

- https://github.com/shokai/node-asearch/tree/master/samples/web

```html
<script src="asearch.min.js"></script>
```
```javascript
a = new Asearch('abcde');
a.match('abcd');
```


## Test

    $ git clone https://github.com/shokai/node-asearch.git
    $ cd node-asearch
    $ npm i
    $ npm i -g grunt-cli
    $ grunt test
    $ grunt watch
