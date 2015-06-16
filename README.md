# dead-code

It looks like uglify won't magically remove the bloat of lodash.y

```js
var _ = require('lodash');
lodash.isEqual('a', 'b');
```

### Setup

`npm install`

### Test

Here is how you can test yourself
```
webpack --config /dev/null out.js # no uglify
webpack test.js out.min.js # uglify
```

### Results

- Unminified: 450kb
- Minified 40kb
