# ADR 18: Individual Logging vs. Centralized Logging with Event Streaming

## Context
We need to decide how to manage application logs: individual logging for each service or centralized logging with event streaming.

## Decision
We will implement centralized logging with event streaming for our application.

## Decision Rationale
- Centralized logging simplifies log aggregation and analysis.
- Event streaming allows real-time log processing and alerts.
- It provides a unified view of logs for better observability.

## Implications
- Setup and configuration of a centralized logging and event streaming infrastructure are required.
- Integration with microservices and log format standardization.

## Dependencies
- Select and configure a centralized logging and event streaming solution (e.g., AWS CloudWatch Logs, AWS Kinesis).

## Implementation Details
- Implement log forwarding from microservices to the centralized logging system.
- Set up real-time log processing and alerting.
- Configure log retention and archiving policies.

## Monitoring and Testing
- Continuously monitor log streams and events.
- Test log processing and alerting for different log scenarios.

## Open Issues
- Implementing proper log access controls and data retention policies.
