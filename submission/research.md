# Research and submission decisions

Checked September 12, 2026, before application implementation.

- [Official overview](https://call-e.devpost.com/): SDK/API/MCP/CLI/skill contributions; specific real-world problem, clear demo and actual runtime integration.
- [Official rules](https://call-e.devpost.com/rules): deadline September 14, 2026, 11:45 p.m. SGT (9:15 p.m. Asia/Colombo). Eligibility and entrant representations must be confirmed by the entrant. Submission materials must be in English or translated; demonstration video should show the project running.
- [Resources](https://call-e.devpost.com/resources): official integrations, documentation and example repository.
- [Integrations](https://github.com/CALLE-AI/call-e-integrations): SDKs for server apps; direct Calls API; MCP plan/run/read flow with OAuth; CLI/skill installation paths. The README described long-running goal optimization as under development.
- [Quickstart](https://docs.heycall-e.com/quickstart), [SDKs](https://docs.heycall-e.com/sdks), [Calls](https://docs.heycall-e.com/calls), [Goal Runs](https://docs.heycall-e.com/goal-runs), [Errors](https://docs.heycall-e.com/errors), [Regions](https://docs.heycall-e.com/regions): checked runtime shapes, supported schema subset, lifecycle, call identifiers, idempotency, transcript evidence, published Goal requirements and destination restrictions.
- [Contribution repository](https://github.com/CALLE-AI/awesome-phone-call-agents), its README, CONTRIBUTING and AGENTS: runnable apps belong under `apps/<runtime>/<app>/`; include dry-run behavior, setup, credentials, side effects, cancellation and validation. Existing examples include batch calling, service dispatch, phone approvals, scheduling and surplus-food confirmation; Last Crate focuses its contribution on the bounded two-party bread handoff and completed collection desk.

Choice: request-scoped Calls API through the official TypeScript SDK. Each partner request depends on the actual donor result, so static published Goal configuration adds setup without helping the first vertical slice. SQLite, native Node and a no-build frontend keep setup small. No second LLM service is needed: CALL-E handles conversational reasoning, and the application explains deterministic matching decisions.

Required submission assets: contribution PR URL, public roughly three-minute YouTube/Vimeo demo, CALL-E account email. The overview requests a built/deployed functional project and lists the demo URL as optional; prepare a deployment rather than assume localhost alone satisfies every requirement. Public publishing and the entrant's Devpost submission are still pending.
