# Outgoing review notes to TEAM_X

## Strong
- Clear NFR mapping and at least one executed verification (k6). Evidence path: /evidence/EV-perf-rsvp.pdf
- Interfaces include idempotency and SLO guidance.

## Risk
- Single DB for reads and writes could be a single point of contention under sustained high load. Consider read-replica or caching strategy.

## Question
- Do you have constraints on data residency or retention that would affect cache TTL or replication strategies?

## What we received (short inbound summary)
- Received: suggestion to add schema for RSVP items and confirm retention of nextCursor for 60s.
- Action: We'll add nextCursor expiry note to the interfaces and schedule k6 run with warm-cache and cold-cache scenarios.
