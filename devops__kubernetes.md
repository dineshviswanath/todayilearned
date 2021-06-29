## Do I Need Kubernetes?

https://mbird.biz/writing/do-i-need-kubernetes.html
Explains when we need to use K8s and when not. Finally it says "It depends" but thoughtful consideration on different aspects of Infrastructure

## Overriding the Entrypoint and commands
https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#notes


## Scaling down the Daemenset
```
kubectl patch daemonset name -p '{"spec": {"template": {"spec": {"nodeSelector": {"non-existing": "true"}}}}}'
```

## debug curl container
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: testcurl
spec:
  containers:
  - name: curl
    image: curlimages/curl 
    command: [ "sleep", "600" ]
```
https://nikgrozev.com/2020/07/29/debug-container-in-kubernetes/

## Start up checks
![image](https://user-images.githubusercontent.com/2858081/123808924-136fb680-d8e9-11eb-8cfd-151aa3e6cd5b.png)
