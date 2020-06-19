## Understanding the Nginx Conf file
https://www.digitalocean.com/community/tutorials/understanding-the-nginx-configuration-file-structure-and-configuration-contexts

```bash
- context
  - events
  - http
    - access_log, error_log
    - error_page
    - gzip
    - keepalive settings
    - server
      - server_name products.tescomobile.com
      - listen 80 
      - location /
        - proxy_pass 
    - map
    - geo
      - only based on IPAdress
    - split_clients
```

