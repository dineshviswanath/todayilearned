
### Error:
Problem: 'AAA' is used in service "XXX" but no declaration was found in the volumes section.

Solution: Try to add "./" infront of volume mapping to get relative link
```bash
    volumes:
      - "./file.yml:/config/file.yml"
```
