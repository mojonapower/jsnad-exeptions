The nativeURLconstructor can be used to parse URLs,it's been wrapped into a function calledparseURL:


```javascript
function parseURL (str) {
    const parsed = new URL(str);
    return parsed
    }
```
IfURLis passed a unparsable URL string it will throw,so callingparseURL('foo')will resultin an exception:LFW211         

The labs-1 folder contains anindex.jsfile with thefollowing content:


```javascript
'use strict'
const assert = require('assert');
function parseUrl (str){
    const parsed = new URL(str);
    return parsed
    }
    assert.doesNotThrow(() => { parseUrl('invalid-url') });
    assert.equal(parseUrl('invalid-url'), null);
    assert.deepEqual(
        parseUrl('http://example.com'),
        new URL('http://example.com')
        )
    console.log('passed!');

```
Modify theparseURLfunction body such that instead of throwing an error, it returnsnullwhenthe URL is invalid. Use the fact thatURLwill throwwhen given invalid input to determinewhether or not to return nullor a parsed object.

Once implemented, execute theindex.jsfile with node,if the output sayspassed!then theexercise was completed successfully:LFW211          


```bash 
$ node index.js
$ passed!
$ _
```

 © Copyright the Linux Foundation 2020-2022. All rights reserved.