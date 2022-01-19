## Docker Sketch
![image](https://user-images.githubusercontent.com/2858081/119145525-a2172b00-ba41-11eb-8401-30aa9cc33a35.png)

## Tutorials
https://training.play-with-docker.com/ops-s1-hello/

### Dockerfile
#### COPY and ADD diff
+ ADD: A valid use case for ADD is when you want to extract a local tar file into a specific directory in your Docker image. 
+ If you’re copying in local files to your Docker image, always use COPY because it’s more explicit.


### Error:
Problem: 'AAA' is used in service "XXX" but no declaration was found in the volumes section.

Solution: Try to add "./" infront of volume mapping to get relative link
```bash
    volumes:
      - "./file.yml:/config/file.yml"
```


### Debug:
+ *How-to Debug a Running Docker Container from a Separate Container*
https://medium.com/@rothgar/how-to-debug-a-running-docker-container-from-a-separate-container-983f11740dc6
```bash
docker run -t --pid=container:caddy \
  --net=container:caddy \
  --cap-add sys_admin \
  --cap-add sys_ptrace \
  ubuntu
```

+ Edit file content inside container without VI editor
```bash
cat <<'EOF' > index.js
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
References: https://superuser.com/questions/1434549/whats-the-different-between-cat-some-file-eof-some-stuff-eof-and-echo



## Networking
+ https://pythonspeed.com/articles/docker-connection-refused/  listening on 0.0.0.0, which means “listen on all interfaces” explanation
