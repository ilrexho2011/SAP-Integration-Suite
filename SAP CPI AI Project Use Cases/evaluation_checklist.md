# Evaluation Checklist (Per Project)

## Design & Reusability
- [ ] Externalized configuration (API base URL, credentials, timeouts)
- [ ] Reusable subflows (logging, error handling) via Process Direct
- [ ] Clear separation of mapping vs orchestration

## Reliability & Observability
- [ ] Exception Subprocess with meaningful error categories
- [ ] Data Store logs for start/success/error with correlation IDs
- [ ] Idempotency and safe retries where applicable

## Security
- [ ] Secure credential handling via CPI Security Material
- [ ] TLS certificates validated
- [ ] PII handling documented (masking in logs)

## Performance
- [ ] Batching or pagination where needed
- [ ] Guardrails (max payload size, timeouts, circuit-breaker pattern)

## Documentation & Handover
- [ ] Readme with endpoint contracts and assumptions
- [ ] Test cases with input/output samples
- [ ] Operational runbook (how to reprocess failures)

Scoring Guidance:
- 0 = Missing, 1 = Partial, 2 = Meets, 3 = Exceeds
Target score ≥ 24/36.
