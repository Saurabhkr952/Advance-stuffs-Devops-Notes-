### Gateway API Kubernetes 

#### Gateway Class
it's just like storage class.

#### Gateway 
you will get a external loadbalancer when you create gateway.

### Route
you will write rule how to route traffic. 

```yaml
apiVersion: gateway.networking.k8s.io/v1beta1
kind: Gateway
metadata:
  name: my-gateway
spec:
  gatewayClassName: gke-l7-gxlb    # 	Global external Application Load Balancer built on the classic Application Load Balancer
  listeners: 
  - name: http
    protocol: HTTP
    port: 80
    allowedRoutes:
      kinds:
      - kind: HTTPRoute

---

apiVersion: gateway.networking.k8s.io/v1beta1
kind: HTTPRoute
metadata:
  name: dev-portfolio-route
spec:
  parentRefs:
  - name: my-gateway
  hostnames:
  - dev-portfolio.34.111.173.32.nip.io
  rules:
    -  backendRefs:
         - name: dev-portfolio
           port: 31000
```
