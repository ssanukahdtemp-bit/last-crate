# One desk, one harness

## Offline demo now

From the repository root, with Node 24 and dependencies installed:

```sh
npm run demo
```

The harness starts the app, runs the synthetic two-call workflow, saves a ticket, and prints a direct link to the finished handoff. No account or manual phone interaction is required.

In this Codex workspace, `node --env-file-if-exists=.env apps/typescript/last-crate/harness.ts demo` also works directly with the installed dependency.

## Final live demo later

The only setup is a CALL-E key and one authorized, supported test number in `.env`. One person can answer both roles. Use actual country/language routing; English to the supplied Sri Lankan number was rejected. English TTS can supply replies on a route that accepts the intended English conversation; a Sinhala label does not establish English route support.

```sh
npm run doctor
npm run harness -- demo --live --yes-live
```

Answer the bakery call using the brief printed by the harness, then the collector call. The harness handles every other operational step. It generates same-day time windows, chooses the eligible partner, creates the second request, validates both replies, records provider evidence, issues the ticket and saves the result report. The maximum is two created call tasks per workflow; the provider owns any internal dial attempts.

If interrupted, repeat the command. It reuses the saved session. Do not add `--new-session` unless intentionally authorizing a fresh pair of calls.

## Replay without phone dependencies

```sh
npm run harness -- recordings
npm run harness -- replay <recorded-run-id>
```

The currently shipped genuine recording is a route rejection. The successful path is synthetic until live success is recorded. The video must preserve this distinction. After the live test, the new recordings appear automatically; no manual fixture editing is needed.

## Submission steps outside the application

GitHub publication was deferred. A prepared contribution branch and local patch are the handoff for that step. Public hosting, YouTube/Vimeo upload and the entrant's Devpost account fields remain separate publishing/account operations; the calling workflow does not depend on them to run. The final screen recording should contain real CALL-E call excerpts when claiming live success, with no secrets or private phone numbers visible.
