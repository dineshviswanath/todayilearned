# Installation
## Installed Custom Resource Definition in Kubernetes
```bash
customresourcedefinition.apiextensions.k8s.io/virtualservices.networking.istio.io created
customresourcedefinition.apiextensions.k8s.io/destinationrules.networking.istio.io created
customresourcedefinition.apiextensions.k8s.io/serviceentries.networking.istio.io created
customresourcedefinition.apiextensions.k8s.io/gateways.networking.istio.io created
customresourcedefinition.apiextensions.k8s.io/envoyfilters.networking.istio.io created
customresourcedefinition.apiextensions.k8s.io/policies.authentication.istio.io created
customresourcedefinition.apiextensions.k8s.io/meshpolicies.authentication.istio.io created
customresourcedefinition.apiextensions.k8s.io/httpapispecbindings.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/httpapispecs.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/quotaspecbindings.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/quotaspecs.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/rules.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/attributemanifests.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/bypasses.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/circonuses.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/deniers.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/fluentds.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/kubernetesenvs.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/listcheckers.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/memquotas.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/noops.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/opas.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/prometheuses.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/rbacs.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/redisquotas.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/servicecontrols.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/signalfxs.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/solarwindses.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/stackdrivers.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/statsds.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/stdios.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/apikeys.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/authorizations.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/checknothings.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/kuberneteses.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/listentries.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/logentries.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/edges.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/metrics.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/quotas.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/reportnothings.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/servicecontrolreports.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/tracespans.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/rbacconfigs.rbac.istio.io created
customresourcedefinition.apiextensions.k8s.io/serviceroles.rbac.istio.io created
customresourcedefinition.apiextensions.k8s.io/servicerolebindings.rbac.istio.io created
customresourcedefinition.apiextensions.k8s.io/adapters.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/instances.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/templates.config.istio.io created
customresourcedefinition.apiextensions.k8s.io/handlers.config.istio.io created
```

istio

- monolithic applications to distributed microservice architecture
- Used
  - A/B testing 
  - canary rollouts, 
  - rate limiting, 
  - access control, 
  - end-to-end authentication.
- Architecture/Components
  - data plane/envoy
    - envoy proxy
      - Problems MicroServices
        - networking
        - observability
      - runs alongside every application 
      - abstracts the network by providing common features in a platform-agnostic manner. 
      - Benefits
        - visualize problem areas via consistent observability,
        - tune overall performance,
        - add substrate features in a single place.
  - Control plane/Istiod
    - Pilot
      - Responsible for configuring the Envoy and Mixer at runtime.
    - Citadel / Istio CA
      -  Secures service to service communication over TLS. Providing a key management system to automate key and certificate generation, distribution, rotation, and revocation.
    - Gallery
    - Mixer 
      - Create a portability layer on top of infrastructure backends. Enforce policies such as ACLs, rate limits, quotas, authentication, request tracing and telemetry collection at an infrastructure level.
    - Ingress/Egress
      - Configure path based routing for inbound and outbound external traffic.
  - Tools
    - Jaeger
      - Jaeger, inspired by Dapper and OpenZipkin, is a distributed tracing system released as open source by Uber Technologies.
      - tracing information for each HTTP request
      - view the details on an individual request and the HTTP calls made
      - identify issues and potential performance bottlenecks.
      - monitoring and troubleshooting microservices-based distributed systems
        - Distributed context propagation
        - Distributed transaction monitoring
        - Root cause analysis
        - Service dependency analysis
        - Performance / latency optimization
      - https://eng.uber.com/distributed-tracing/
- Traffic Management
  - control the flow of traffic and API calls between services.
  - percentage-based traffic splits
  - Services
    - Gateways
    - Virtual Services
      - configure how requests are routed to a service within an Istio service mesh
      - set of routing rules that are evaluated in order
      - manifests
        - hosts
          - IP Address
          - DNS name
          - Wildcard
        - http
          - match
            - uri
            - headers
          - route
            - destination
              - host
            - destination
              - host
    - Destination Rules
    - Service Entries
    - Sidecars
- Security
- Observability
- Extensibility
- Sample
  - https://istio.io/latest/docs/examples/bookinfo/
