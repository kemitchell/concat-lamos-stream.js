```javascript
var assert = require('assert')
var concat = require('concat-lamos-stream')

require('pump')(
  require('string-to-stream')(
    [
      'a: x',
      'b: y'
    ].join('\n')
  ),
  concat(function (parsed) {
    assert.deepEqual(
      parsed,
      {
        a: 'x',
        b: 'y'
      }
    )
  })
)
```
