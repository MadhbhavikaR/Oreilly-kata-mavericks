## ADR 9: Choice of Container Orchestration Platform
### Context
We need to decide on the container orchestration platform for hosting our services: Kubernetes (K8S) or AWS Elastic Container Service (ECS).

### Decision
We will use Amazon Elastic Kubernetes Service (EKS) as our container orchestration platform for hosting services.

### Decision Rationale

- EKS provides better compatibility with our AWS-based architecture and services.
- Kubernetes offers a broader ecosystem and community support.
- This choice aligns with our services and scalability goals.

### Implications

- Setting up and managing an EKS cluster is required.
- Kubernetes expertise within the team or training may be needed.

### Dependencies

- Create and configure an EKS cluster.
- Define Kubernetes manifests for microservices.

### Implementation Details

- Deploy services to the EKS cluster using Kubernetes manifests.
- Implement CI/CD pipelines for automated deployments to EKS.

### Monitoring and Testing

- Monitor EKS cluster health, scaling, and resource utilization.
- Test deployments, scaling, and failover in the Kubernetes environment.

### Open Issues
Detailed configuration and resource allocation for the EKS cluster.
