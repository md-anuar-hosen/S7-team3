## Context
NFR-PERF-01 requires p95 latency <200ms at 200 RPS for list endpoints. Our dataset is moderately sized and served to occasional burst traffic.

## Choice
We chose a read-through cache in front of the API + cursor-based pagination. The cache reduces read load on the DAL and keeps p95 latency predictable. Cursor pagination avoids expensive count/offset queries and keeps response sizes stable.

## Alternatives Rejected
- Full microservice split (rejected): introduced operational complexity and cross-service latency that would harm the p95 target.
- Offset-based pagination (rejected): offset grows linearly with page number causing slow DB scans at high offsets.

## Risks & Mitigations
- Cache staleness -> Mitigation: short TTL (30s) for list endpoints + cache invalidation on write; Verification: T-PERF-01 shows cache hit scenario, evidence/EV-perf-rsvp.pdf.
- Thundering herd on cache expiry -> Mitigation: jittered TTL + background refresh for hot keys; Verification hook: T-PERF-01 variant with staggered expiry.
- Retry storms for POST /v1/rsvp -> Mitigation: require clientKey idempotency + proper 4xx/5xx semantics; Verification hook: T-AV-01 (uptime/availability check).

## Verification Hook
T-PERF-01: target p95<200ms at 200RPS. Evidence located at `evidence/EV-perf-rsvp.pdf`.
