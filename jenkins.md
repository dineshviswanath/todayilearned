# Pipeline
+ Never create Parameter name with Dash in it. Jenkins throws error when variable is referenced like this `"${SHARED-FLOW-BRANCH}"`
```
hudson.remoting.ProxyException: groovy.lang.MissingPropertyException: No such property: SHARED for class: WorkflowScript
```
+ BAD:
  `SHARED-FLOW-BRANCH`
+ GOOD:
  `SHARED_FLOW_BRANCH` or `SHAREDFLOWBRANCH`
  
