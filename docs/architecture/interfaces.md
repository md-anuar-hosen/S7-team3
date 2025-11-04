# Critical Interfaces (3)

## 1) GET /v1/rsvp
- Purpose: List RSVPs (cursor pagination)
- Query params: `cursor` (string), `limit` (int, max 100, default 50)
- Responses:
  - 200: `{ items: [Rsvp], nextCursor: string }`
  - 429: Rate limited (retryable)
  - 500: Server error (retryable)
- Error body: `{ code, message, details }`
- Pagination: Cursor-based (nextCursor)
- SLO: p95 < 200ms
- Timeouts/Retry: client timeout 3s, retry on 429/5xx with exponential backoff, idempotent reads

## 2) POST /v1/rsvp
- Purpose: Create RSVP
- Body: `{ name: string, notes?: string, clientKey: string }`
- Responses:
  - 201: created
  - 400: validation error
  - 409: duplicate (idempotency)
- Idempotency: clientKey required to dedupe retries
- SLO: p99 < 500ms
- Retries: retry on network errors/5xx, do not retry 4xx except 429

## 3) POST /v1/auth/login
- Purpose: Issue short lived token
- Body: `{ username, password }`
- Responses:
  - 200: `{ token }`
  - 401: invalid credentials
- SLO: p95 < 250ms
- Security: TLS only, brute-force throttling on auth endpoint
