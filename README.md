# Last Crate

A phone-powered closing-time handoff for surplus bread. Built from scratch for CALL-E: Your Code Is Calling.

Implementation lives in [apps/typescript/last-crate](apps/typescript/last-crate). Fixture mode never calls a phone. Live mode uses the official CALL-E server SDK.

Node 24+, then `npm install` and **`npm run demo`**. The harness starts the server, completes a no-call handoff, saves its ticket and prints the direct application link. `npm start` runs the collection desk without starting a demo. Run `npm test` for offline verification.

Copy `.env.example` to `.env` for live configuration. Never commit credentials or private call evidence.

`npm run harness -- demo --live --yes-live` runs at most two authorized role-play calls with automatic matching, recovery, recording and ticket generation. `npm run harness -- replay <run-id>` replays captured provider responses with no calls. Successful seed fixtures remain explicitly synthetic until successful live calls are recorded.

See [submission status](submission/STATUS.md), [demo script](submission/demo-script.md), and the [app README](apps/typescript/last-crate/README.md) for the remaining submission work.
