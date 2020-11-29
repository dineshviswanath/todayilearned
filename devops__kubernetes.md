## Do I Need Kubernetes?

https://mbird.biz/writing/do-i-need-kubernetes.html
Explains when we need to use K8s and when not. Finally it says "It depends" but thoughtful consideration on different aspects of Infrastructure

## Overriding the Entrypoint and commands
https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#notes


##Scaling down the Daemenset
```
kubectl patch daemonset splunk-forwarder-splunk-kubernetes-logging -p '{"spec": {"template": {"spec": {"nodeSelector": {"non-existing": "true"}}}}}'
```
