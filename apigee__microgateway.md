# MicroGateway 
## Installation issues
### problems
#### Due to permission issue, configs are not loaded
```bash
2020-10-26T12:44:04.727Z [33] [microgateway edgemicro] current nodejs version is v12.16.1
2020-10-26T12:44:04.728Z [33] [microgateway edgemicro] current edgemicro version is 3.1.7
SIGTERM delay : [  ]
tee: /opt/apigee/logs/edgemicro.log: Permission denied
/opt/apigee/entrypoint.sh: line 34: /opt/apigee/.edgemicro/tescomobile-nonprod-dev-config.yaml: Permission denied
chown: cannot access '/opt/apigee/.edgemicro/*': No such file or directory
```
Solution:
3.1.7v has wrong UID for runasuser. 
Instead of 
```
    securityContext:
        runAsNonRoot: true
        runAsUser: 100
```
Update to 
```
    securityContext:
        runAsNonRoot: true
        runAsUser: 101
```
