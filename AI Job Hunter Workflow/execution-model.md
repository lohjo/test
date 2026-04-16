# Execution Model

Doc defines phase run order, spawn contract, artifact flow, Gmail delivery.

## Runtime Assumptions

- Search via web tools or approved APIs.
- Code exec in local Python runtime.
- Storage in workspace files only (temp JSON + XLSX).
- User confirm each phase gate before continue.

## Phase Order

1. Intake and preference lock.
2. Search and raw data capture.
3. XLSX generation.
4. Filter and score.
5. Outreach generation.
6. Package and close.

No phase skip unless user explicitly approves skip.

## Agent Spawn Contract

- Spawn must include payload, timeout, expected output.
- Spawn fail -> retry max 2.
- Still fail -> abort phase + cleanup.

## Gmail Delivery Modes

Primary mode:
- Gmail API creds present -> create draft via API.

Fallback mode:
- Gmail API unavailable -> output copy-paste markdown with To/Subject/Body.

Both modes preserve exact email text from scorer/outreach agent.

## Partial Failure Policy

- Some jobs fail email gen -> keep successes.
- Retry failed jobs once.
- Return success_count, fail_count, fail reasons.

## Cleanup Rules

On abort:
- Delete temp search JSON.
- Delete partial XLSX from failed run.
- Keep logs/messages for audit.
