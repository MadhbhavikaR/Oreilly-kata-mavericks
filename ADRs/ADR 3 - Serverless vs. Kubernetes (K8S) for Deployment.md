## ADR 3: Serverless vs. Kubernetes (K8S) for Deployment

### Context
We need to determine the deployment strategy for our microservices: Serverless (AWS Lambda) or Kubernetes (K8S) orchestration.

### Decision
We will adopt a Kubernetes (K8S) deployment strategy for our microservices.

### Decision Rationale
+ Kubernetes offers container orchestration, providing flexibility and scalability.
+ It allows better resource management and fine-grained control over deployments.
+ Kubernetes aligns well with our heterogeneous microservices architecture.
+ Kubernetes facilitates setting up different parallel environments in a streamlined manner.
+ Kubernetes’s on-demand provisioning with proper min-max tuning can lead to cost savings.
+ Using container based deployment and Kubernetes orchestration we can benefit with infra-as-code along with clear rule based deployment like defining when application is healthy, when to add or remove pods, etc.

### Implications
+ Kubernetes management may introduce additional complexity compared to serverless.
+ Kubernetes requires skilled DevOps and infrastructure management.

### Dependencies
Set up and configure a Kubernetes cluster.

### Implementation Details
+ Define Kubernetes manifests for each microservice.
+ Implement CI/CD pipelines for automated deployments.

### Monitoring and Testing
+ Monitor Kubernetes cluster health, scaling, and resource utilization.
+ Test deployments and scaling in Kubernetes.

### Open Issues
Implementing an efficient CI/CD pipeline for Kubernetes.
