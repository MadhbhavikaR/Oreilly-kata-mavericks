## ADR 8: Web Server vs. S3 and CDN for Site Hosting

### Context
We need to decide how to host the static website resources: using a traditional web server or Amazon S3 with a Content Delivery Network (CDN).

### Decision
We will host the static website resources using Amazon S3 and a Content Delivery Network (CDN).

### Decision Rationale
- S3 and CDN combination offers high availability and low-latency content delivery.
- It scales easily to handle traffic spikes and global distribution.
- This approach aligns with cost-effectiveness and simplicity.

### Implications
- Configuration and management of S3 buckets and CDN distribution are required.
- Ensure proper cache control and versioning for website assets.

### Dependencies
- Set up S3 buckets for storing website assets.
- Configure CDN distribution.

### Implementation Details
- Upload static website resources to S3 buckets.
- Set up cache control and versioning for assets.
- Configure CDN for fast content delivery.

### Monitoring and Testing
Monitor CDN performance and cache utilization.
Test website loading times and availability from various global locations.

### Open Issues
Implementation of cache purging strategies for CDN.
