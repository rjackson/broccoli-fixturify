# Broccoli Fixturify

[![Build Status](https://travis-ci.org/rwjblue/broccoli-fixturify.svg?branch=master)](https://travis-ci.org/rwjblue/broccoli-fixturify)

## Usage

Create a Broccoli source node whose contents are created by
[fixturify](https://github.com/joliss/node-fixturify) rather than coming from
the file system:

```javascript
var Fixturify = require('broccoli-fixturify');

var desiredDirectory = {
  'foo.txt': 'foo.txt contents',
  'subdir': {
    'bar.txt': 'bar.txt contents'
  }
}

var node = new Fixturify(desiredDirectory);

node.write({
  'other.file': 'its contents',
  'other.directory': {
  'a.file': 'hello, i was added to the fixture'
  }
}); // appends the following files on the next build

node.remove({
  'foo.txt': null,
}); // removes 'foo.txt' on the next build

node.reset(); // on next build, the fixture directory is restored to "desiredDirectory"
```

## Full Usage

## Documentation

### `new Fixturify(fixturifyObjectTree)`

`fixturifyObjectTree` *{Object}*

This will be used by `fixturify` to generate a directory tree based on the file input.

## ZOMG!!! TESTS?!?!!?

I know, right?

Running the tests:

```javascript
npm install
npm test
```

## License

This project is distributed under the MIT license.
