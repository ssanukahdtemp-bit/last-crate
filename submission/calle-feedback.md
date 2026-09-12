# CALL-E feedback draft — not yet submitted

## Reproducible region/language mismatch

Date: September 12, 2026. SDK: `@call-e/calle@0.7.0`. Calls API endpoint: `POST https://api.heycall-e.com/v1/calls`.

The official region table at https://docs.heycall-e.com/regions listed Sri Lanka (`LK`, +94) with English, Tamil and Sinhala. A request to an authorized Sri Lankan test number, with recipient `region: "LK"` and `locale: "en-US"`, was rejected before returning a Call ID.

Stable error code: `call_not_ready`.

The error explained that English calls to Sri Lanka were not currently supported and requested a supported region/language combination. No phone number or API key is included in this report. No accepted or completed call is claimed.

### Why this mattered

We selected the route from the published table and prepared a two-call English role-play within a small testing quota. The failure blocked live validation despite a working app and authenticated API access.

### Suggested improvement

Provide an authoritative, machine-readable supported destination/locale list, or a no-dial validation endpoint, and align the documentation with that list. Distinguish invalid locale syntax from unavailable English support. A rejection should clearly indicate whether a call was created and whether quota was consumed.

### Positive developer experience

The SDK's explicit idempotency key, structured result schema and transcript turns make it possible to separate call execution from business success. The documentation on recovering an unknown creation outcome was directly useful in avoiding blind redials.

### Additional observations

- A local count of call reservations cannot establish account spend. Exposing estimated duration/cost limits per request would improve small-budget testing.
- The documented absence of client-side call cancellation influenced the app's “Stop future calls” label and its reconciliation behavior. A supported cancellation endpoint would simplify the operator experience.

Only the region mismatch above was directly observed against the live API. The additional observations are design feedback, not claims of defects.
