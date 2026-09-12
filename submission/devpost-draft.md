# Last Crate

## Tagline

Surplus bread is not a pickup. Last Crate makes the handoff.

## Inspiration

At a bakery's closing time, stock changes faster than a listing can be updated. Knowing that bread exists does not tell a community coordinator whether it is still available, whether someone will set it aside, or whether a collector can arrive in time. Those facts and commitments live with the people at the other end of the phone.

## What it does

Last Crate coordinates one same-day collection of surplus plain bread. CALL-E confirms the bakery's real quantity and time window. A deterministic matcher excludes partners without enough capacity or time to travel. A second CALL-E call offers the confirmed quantity to the closest eligible partner and asks for an explicit pickup commitment. Software checks the result and creates an expiring pickup ticket with both calls' evidence.

The demo is deliberately narrow: known bakery, approved collection roster, full-quantity pickup, own transport. No open marketplace, driver network or generic chat interface.

## How we built it

TypeScript running directly on Node 24, SQLite for durable workflow state, and a small HTML/CSS/JavaScript interface. The official `@call-e/calle` SDK is invoked on the server at runtime. CALL-E owns natural conversation and structured extraction; the application owns feasibility, state transitions, call reservations and the final ticket.

The same workflow runs with explicit no-call fixtures. A saved idempotency key and request precede every live creation. Restart recovery retrieves the saved Call ID or replays the unchanged operation if the original response was lost.

## What makes it different

The mechanism is the two-sided handoff. The bakery agrees to release a specific quantity during a specific window. The collector accepts that exact offer with transport and a feasible arrival. A favorable-sounding phone call alone cannot issue a ticket.

## Challenges

Testing exposed a mismatch between documented and actual English calling support to Sri Lanka. The API returned `call_not_ready`; the app preserved the rejection as unresolved and did not fabricate a successful call or pickup. We also fixed a stop-request race in which a worker could overwrite the coordinator's stop while a provider request was awaiting its response.

## What we learned

Call completion, task completion, pickup agreement and actual collection are four different facts. Treating them separately makes the workflow understandable and recoverable.

## What's next

A supervised pilot with a bakery and its existing collection partners, measured by agreed pickups that actually happen. Follow-up work would connect the ticket to their dispatch system and replace manual travel estimates where useful.

## Required fields still to complete

- Public CALL-E contribution PR URL: https://github.com/CALLE-AI/awesome-phone-call-agents/pull/492.
- Public YouTube/Vimeo demo URL: not yet recorded/uploaded; use an explicitly labeled fixture walkthrough if live verification remains unavailable.
- CALL-E account email: entrant to supply privately in Devpost.
- Functional deployed application URL: not yet deployed; local app runs at localhost:3210.
- Live integration evidence: authenticated runtime request verified; successful live conversations still pending accepted English destination.

Remove this checklist from the final public story after filling the actual fields. Do not replace pending facts with claims of completion.
