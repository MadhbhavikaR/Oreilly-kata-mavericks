# ADR 17: Schedule-Based vs. Event/Webhook-Based Triggers

## Context
We need to determine how various actions and processes in our application will be triggered: using schedule-based triggers or event/webhook-based triggers.

## Decision
We will prioritize event/webhook-based triggers for our application.

## Decision Rationale
- Event/webhook-based triggers enable real-time and responsive processing.
- They align with an event-driven microservices architecture.
- This approach allows us to respond to changes as they occur.

## Implications
- Implementation of event publishers, subscribers, and webhook endpoints is necessary.
- Event schemas and contracts need to be defined and maintained.

## Dependencies
- Set up event publishers and webhook endpoints.
- Define event schemas and contracts.

## Implementation Details
- Implement event publishers for critical actions in microservices.
- Configure webhook endpoints for external integrations and notifications.

## Monitoring and Testing
- Monitor event delivery, processing, and webhook responses.
- Test event-driven processes for responsiveness and reliability.

## Open Issues
- Event versioning and backward compatibility.
