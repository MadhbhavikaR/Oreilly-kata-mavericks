# ADR 16: Pull-Based vs. Push-Based Data Consumption Approaches

## Context
We need to decide how data will be consumed by microservices: using a pull-based approach or a push-based approach.

## Decision
We will adopt a push-based data consumption approach mainly for our microservices architecture. However, to support the service providers who do not have a webhook registration capability we would have a pull-based approach at the connector level

## Decision Rationale
- Push-based data consumption allows real-time updates and event-driven processing.
- It aligns with the principles of microservices, where services respond to events.
- This approach reduces latency and enhances scalability.

## Implications
- Implementation of event-driven architecture and message brokers is required.
- Services must subscribe to relevant events and handle them appropriately.

## Dependencies
- Set up a message broker or event bus (e.g., AWS SNS, AWS EventBridge).

## Implementation Details
- Define events and topics for various microservices to publish and subscribe to.
- Implement event producers and consumers in microservices.

## Monitoring and Testing
- Monitor event delivery and processing times.
- Test the resilience and scalability of event-driven communication.

## Open Issues
- Event schema management and versioning.
