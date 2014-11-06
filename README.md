# HumbleJS - MongoDB ODM for Javascript

HumbleJS is the sister project of [HumbleDB](http://humbledb.readthedocs.org/),
a MongoDB ORM for Python. HumbleJS tries to maintain API parity with HumbleDB
where at all possible, and when it makes sense, extends the API for convenience
and clarity in JavaScript and CoffeeScript.

HumbleJS is written in CoffeeScript, but compiled and distributed as
JavaScript.

[![Build Status](https://travis-ci.org/aboutdotme/humblejs.svg?branch=master)](https://travis-ci.org/aboutdotme/humblejs)

Currently HumbleJS is stable in core features, but under development as
nice-to-have features are added regularly. Documentation is a work in progress.

## [Documentation](http://humblejs.readthedocs.org)

[Documentation](http://humblejs.readthedocs.org) is available on Read The Docs.

## Examples

**Example**:

```javascript
var mongojs = require('mongojs')
var Document = require('humblejs').Document
var MyDoc = new Document(mongojs('testdb').collection('my_doc'), {
    prop: 'a',
    other_prop: 'o',
    default_value: ['d', some_default],
    with_a_stored_default: ['s', function(){ Math.random() }],
    });
doc = new MyDoc();
doc.prop = "foobar"

// Property assignment is mapped
doc === {a: "foobar"}

// Accessing a missing default will return the specified value
doc.default_value === "some default"
```

## License

MIT - See LICENSE

