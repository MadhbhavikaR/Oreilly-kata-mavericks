## ADR 15: Choice of Load Balancer and Web Application Firewall (WAF)

### Context
We need to decide on the load balancing and web application firewall (WAF) services for distributing traffic and enhancing security.

### Decision
We will use Amazon Elastic Load Balancing (ELB) with AWS Web Application Firewall (WAF) for traffic distribution and security.

### Decision Rationale
- Amazon ELB provides load balancing with high availability and scalability.
- AWS WAF offers protection against web application attacks and threats.
- This choice aligns with our AWS-based architecture and enhances security.

### Implications
- Configuration of ELB listeners, target groups, and routing policies is required.
- Definition of WAF rules, conditions, and security policies.

### Dependencies
- Set up Amazon ELB load balancers and define target groups.
- Configure AWS WAF rules and conditions.

### Implementation Details
- Set up ELB listeners and routing for distributing traffic to services.
- Implement AWS WAF rules to protect against common web application attacks.

### Monitoring and Testing
- Monitor ELB health, traffic distribution, and SSL termination.
- Test WAF rules for effectiveness in blocking malicious traffic.
