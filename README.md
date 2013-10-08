
# subfs

Create subfilesystems that are rooted at a specific directory.

## Example

```js
var fs = require('fs');
var subfs = require('subfs');

var sub = subfs(fs, __dirname + '/dir');

// write file.txt into the filesystem mounted at ./dir
sub.writeFile('file.txt', 'foobar', function(err) {
  if (err) throw err;

  fs.readFile(__dirname + '/dir/file.txt', function(err, value) {
    if (err) throw err;
    console.log('value: %s', value);
    // value: foobar
  });
});
```

## API

```js
var subfs = require('subfs');
```

### var sub = subfs(fs, dir)

Create a [fs](http://nodejs.org/api/fs.html) clone that prefixes each operation
with the given `dir`.

## Installation

With [npm](https://npmjs.org) do:

```bash
npm install subfs
```

## License

(MIT)

Copyright (c) 2013 Julian Gruber &lt;julian@juliangruber.com&gt;

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
