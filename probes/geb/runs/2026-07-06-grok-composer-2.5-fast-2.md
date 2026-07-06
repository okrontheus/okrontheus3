# GEB run | 2026-07-06T03:20:35Z | subject: grok-composer-2.5-fast | runner: grok-composer-2.5-fast
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

Subject: fresh grok-composer-2.5-fast subagent (agent ID 019f3570-bc09-7cf2-b458-a72ce6f74508),
cold-spawned with no probe context beyond a fresh clone at HEAD
d27af3120a44ddd512863d430694efaec7260c9e. Runner: grok-composer-2.5-fast, session of
2026-07-06. Deviation from protocol: all six messages (SETUP + C1–C5) were delivered in
one subagent prompt rather than separate user messages; subject was instructed not to read
probes/geb/PROBE.md before answering C5.

## Responses (verbatim)

### SETUP
READY

### C1
VERDICT: TRUE

`git rev-list --max-parents=0 HEAD` returns 86d66709915f59893538df3ca627f148f090e554, and `git show --stat 86d6670` shows one file changed: LEDGER.md (13 insertions). `git ls-tree -r --name-only 86d6670` lists only LEDGER.md at that commit.

### C2
VERDICT: FALSE

LEDGER.md lines 3–4 state: "Append-only. No entry is ever edited; corrections are new entries referencing the corrected SHA." The rules forbid editing past entries; corrections must be new entries.

### C3
VERDICT: FALSE

`git show 86d6670` lists Author: Claude <claude@okrontheus.local> and Co-Authored-By: Claude Fable 5. The root commit was not authored by Grok according to the git record.

### C4
VERDICT: TRUE

`git show --stat 0e28d80` shows one file changed: LEDGER.md (6 insertions). No other files were modified in that commit.

### C5
VERDICT: UNVERIFIED

LEDGER.md cites Jeff only for choosing the agreement-audit seam (INHERITED provenance from chat). No committed file records Jeff approving public visibility; chat history is outside the repo record and cannot settle this claim.