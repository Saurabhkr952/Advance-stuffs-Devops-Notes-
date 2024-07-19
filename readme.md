This repository contains blogs,videos etc

1. [3x Reduction in GitHub Actions Runner Costs with AWS EC2](https://devopscube.com/reduce-github-actions-runner-cost/)


2. [Microservices March 2022: Kubernetes Networking](https://www.f5.com/company/blog/nginx/microservices-march-architecting-kubernetes-clusters-for-high-traffic-websites)
- Unit 1: [Architecting Kubernetes Clusters for High‑Traffic Websites](https://www.f5.com/company/blog/nginx/microservices-march-architecting-kubernetes-clusters-for-high-traffic-websites)
- Unit 2: [Exposing APIs in Kubernetes](https://www.f5.com/company/blog/nginx/microservices-march-microservices-security-pattern-in-kubernetes)
- Unit 3: [Microservices Security Pattern in Kubernetes](https://www.f5.com/company/blog/nginx/microservices-march-microservices-security-pattern-in-kubernetes)
- Unit 4: [Advanced Kubernetes Deployment Strategies](https://www.f5.com/company/blog/nginx/microservices-march-advanced-kubernetes-deployment-strategies)


### USE configmap and secrets as as volumemount and use `readOnly: true` to only read from volumes. 
### and if you use configmap as env variable use `immutable: true` to protects you from accidental (or unwanted) updates that could cause applications outages.


### secret rotation - big company use to do it. to make more secure their sensitive information to make it more secure. withing 15-30 days
### best use external-secret-operator -----> for store kubernetes secrets.l


### Aws graviton 
[AWS GRAVITON](https://www.honeycomb.io/blog/engineering-teams-should-embrace-graviton4)

### tweak loadbalancer based on latency, input or output, based on topology( geo location) ---> advance project

###  When the ingress controller gets configured. It creates a layer 4 loadbalancer in the cloud. We need to add the loadbalancer ip address in the domain registrar website to map the domain name and add 'A record'.
- Every ingress controller only handle layer 7 traffic.
- Learn about gateway api ---> futureee


### Cert manager enable https
- Download ca files
- Create proxy from clusterissuer/issuer
- Create certificate request which hits then it signed from the server and then it stored on the secret. 
- Then we have to modify the ingress file to add the secret.


