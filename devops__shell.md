
## Reference
https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html#tag_18_22

## Links
+ https://explainshell.com/ 
+ 


## Here-document
Source:
https://superuser.com/questions/1434549/whats-the-different-between-cat-some-file-eof-some-stuff-eof-and-echo
```bash
cat <<'EOF' >> index.js
'use strict';
var debug = require('debug')

module.exports.init = function(config, logger, stats) {

  return {
   
    ondata_response: function(req, res, data, next) {
      debug('***** plugin ondata_response');
      next(null, null);
    },
    
    onend_response: function(req, res, data, next) {
      debug('***** plugin onend_response');
      next(null, "Hello, World!\n\n");
    }
  };
}
EOF
```
