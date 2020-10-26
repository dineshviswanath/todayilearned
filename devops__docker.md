
### Error:
Problem: 'AAA' is used in service "XXX" but no declaration was found in the volumes section.

Solution: Try to add "./" infront of volume mapping to get relative link
```bash
    volumes:
      - "./file.yml:/config/file.yml"
```


### Debug:
*How-to Debug a Running Docker Container from a Separate Container*
https://medium.com/@rothgar/how-to-debug-a-running-docker-container-from-a-separate-container-983f11740dc6
```bash
docker run -t --pid=container:caddy \
  --net=container:caddy \
  --cap-add sys_admin \
  --cap-add sys_ptrace \
  ubuntu
```
