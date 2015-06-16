# dead-code

It looks like uglify won't magically remove the bloat of lodash.

Here is the first version of things (test.js)

```js
var _ = require('lodash');
lodash.isEqual('a', 'b');
```

Here is the obviously more optimized version (test2.js)
```js
var isEqual = require('lodash.isequal');
isEqual('a', 'b');
```

### Setup

`npm install`

### Test

Here is how you can test yourself
```
webpack --config /dev/null test.js out.js # no uglify
webpack test.js out.min.js # uglify
webpack --config /dev/null test2.js out2.js # no uglify
webpack test2.js out2.min.js # uglify
```

### Results

```
824 -rw-r--r--  1 jamuferguson  110163442   412K Jun 16 15:20 out.js
104 -rw-r--r--  1 jamuferguson  110163442    50K Jun 16 15:20 out.min.js
 88 -rw-r--r--  1 jamuferguson  110163442    40K Jun 16 15:20 out2.js
 16 -rw-r--r--  1 jamuferguson  110163442   6.4K Jun 16 15:20 out2.min.js
```

