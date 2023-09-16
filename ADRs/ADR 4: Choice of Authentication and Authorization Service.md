## ADR 4: Choice of Authentication and Authorization Service
### Context
We need to decide on the authentication and authorization service for securing our application.

### Decision
We will use Amazon Cognito as our authentication and authorization service.

### Decision Rationale

+ Amazon Cognito offers managed user identity and access control services.
+ It provides user authentication, multi-factor authentication (MFA), and OAuth support.
+ Integration with AWS services simplifies security and user management.

### Implications

+ Configuration of user pools and identity providers within Amazon Cognito is required.
+ User authentication and authorization logic need to be integrated with the application.

### Dependencies

Set up Amazon Cognito user pools and identity providers.

### Implementation Details

+ Configure user authentication settings and security policies.
+ Implement user authentication and authorization flows in the application.

### Monitoring and Testing

+ Monitor user authentication and authorization events.
+ Test user registration, login, and access control in the application.

### Open Issues

Implementation of MFA and user access policies.
