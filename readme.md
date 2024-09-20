This repository contains blogs,videos etc

1. [3x Reduction in GitHub Actions Runner Costs with AWS EC2](https://devopscube.com/reduce-github-actions-runner-cost/)


2. [Microservices March 2022: Kubernetes Networking](https://www.f5.com/company/blog/nginx/microservices-march-architecting-kubernetes-clusters-for-high-traffic-websites)
- Unit 1: [Architecting Kubernetes Clusters for High‑Traffic Websites](https://www.f5.com/company/blog/nginx/microservices-march-architecting-kubernetes-clusters-for-high-traffic-websites)
- Unit 2: [Exposing APIs in Kubernetes](https://www.f5.com/company/blog/nginx/microservices-march-microservices-security-pattern-in-kubernetes)
- Unit 3: [Microservices Security Pattern in Kubernetes](https://www.f5.com/company/blog/nginx/microservices-march-microservices-security-pattern-in-kubernetes)
- Unit 4: [Advanced Kubernetes Deployment Strategies](https://www.f5.com/company/blog/nginx/microservices-march-advanced-kubernetes-deployment-strategies)


#### USE configmap and secrets as as volumemount and use `readOnly: true` to only read from volumes. 
#### and if you use configmap as env variable use `immutable: true` to protects you from accidental (or unwanted) updates that could cause applications outages.


#### secret rotation - big company use to do it. to make more secure their sensitive information to make it more secure. withing 15-30 days
#### best use external-secret-operator -----> for store kubernetes secrets.

### Types of Deployment strategies
- [CANARY_BLUE-GREEN_A/B](https://spacelift.io/blog/kubernetes-deployment-strategies)

#### Aws graviton 
[AWS GRAVITON](https://www.honeycomb.io/blog/engineering-teams-should-embrace-graviton4)

#### tweak loadbalancer based on latency, input or output, based on topology( geo location) ---> advance project

####  When the ingress controller gets configured. It creates a layer 4 loadbalancer in the cloud. We need to add the loadbalancer ip address in the domain registrar website to map the domain name and add 'A record'.
- Every ingress controller only handle layer 7 traffic.
- Learn about gateway api ---> futureee


#### Cert manager enable https
- Download ca files
- Create proxy from clusterissuer/issuer
- Create certificate request which hits then it signed from the server and then it stored on the secret. 
- Then we have to modify the ingress file to add the secret.


### DNS RECORDS- A,AAAA,CNAME
[DNS RECORDS- A,AAAA,CNAME](https://www.whizlabs.com/blog/dns-records/?hl=en-IN)


### 3 pillars of observaiblity 
- **Metrics, Logs, Traces & Profiling**
  
- Let's talk about Traces ---------> specifically opentelemetry(Distributed tracing, vendor agnostic)
- Instrument in source code with opentelemetry & send traces to collectors.(eg. Jaeger).

**Benefits:**
- **performance & Latency optimization & identify bottleneck**: Visualize and monitor the time taken to communicate with services in a distributed system.
- **Error Tracking**: It captures errors and exceptions within spans, allowing you to see where failures or issues arise.
    eg.  For example, if a request goes through services A → B → C → D, and an error occurs between B and C, you can easily see and pinpoint this in the trace by visualization.
    
- **jaeger** uses otel collector by default. It migrates from its own collector.

### Gateway API Kubernetes 
#### Gateway Class
it's just like storage class.
#### Gateway 
you will get a external loadbalancer when you create gateway
### Route
you will write rule how to route traffic. 


##### what is tls & How does it link to HTTPS?
- It's an improved version of the SSL.
- Hypertext Transfer Protocol Secure (HTTPS) which uses SSL/TLS to encrypt the data exchanged between the browser and server. When a website uses HTTPS:
- The browser and server establish a secure connection using SSL/TLS.    
##### what is tls certificate ?
- It is a digital certificate that verifies the identity of a website or server and ensures a secure connection. It's issued by a trusted Certificate Authority (CA).


#### Database Schema Management for Kubernetes -----> SchemaHero
