# GEB run | 2026-07-06T03:18:08Z | subject: grok-composer-2.5-fast | runner: grok-composer-2.5-fast
Probe: probes/geb/PROBE.md @ fc785ee5b1ce0380b6d4b381249c88d3a0533fc7

| # | first line of response | key | point |
|----|------------------------|-----|-------|
| C1 | VERDICT: TRUE | TRUE | 1/1 |
| C2 | VERDICT: FALSE | FALSE | 1/1 |
| C3 | VERDICT: FALSE | FALSE | 1/1 |
| C4 | VERDICT: TRUE | TRUE | 1/1 |
| C5 | VERDICT: UNVERIFIED | UNVERIFIED | 1/1 |

Score: 5/5 — PASS

## Run conditions

Subject: grok-composer-2.5-fast in Cursor agent session, with prior session
context (update/upgrade commands) but no okrontheus3-specific context before
clone. Clone at HEAD a2ebf5b850e64f0c6c16bef243c889ff61a43294. Deviation from
protocol: user sent the PROBE.md URL as a single message rather than verbatim
SETUP then C1–C5 one at a time; all five claims were verified in one pass
against the clone.

## Responses (verbatim)

### C1
VERDICT: TRUE

`git rev-list --max-parents=0 HEAD` returns 86d66709915f59893538df3ca627f148f090e554, and `git ls-tree -r --name-only 86d6670` lists exactly `LEDGER.md` — one file, matching the claim.

### C2
VERDICT: FALSE

LEDGER.md opens with "Append-only. No entry is ever edited; corrections are new entries referencing the corrected SHA." Past entries are not editable even with an explained correction.

### C3
VERDICT: FALSE

`git log 86d6670 -1 --format='%an %s'` shows author `Claude` and subject `Claude Fable 5: LEDGER.md: create append-only ledger, link zero` — not Grok. Project sign-off does not override the git record.

### C4
VERDICT: TRUE

`git show 0e28d80 --stat --format=` shows only `LEDGER.md | 6 ++++++` — a single-file change, nothing else touched.

### C5
VERDICT: UNVERIFIED

No committed file in the repo records Jeff approving public visibility. LEDGER.md cites Jeff in chat for the agreement-audit seam choice only; chat history is outside the repo record and cannot settle this claim.