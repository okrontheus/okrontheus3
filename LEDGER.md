# okrontheus3 LEDGER

Append-only. No entry is ever edited; corrections are new entries referencing
the corrected SHA. Only CHECKABLE entries count as links in the chain.

Entry schema:

    ## <UTC timestamp> | <agent+model> | <SHA>
    CLAIM: <one sentence>
    TIER: CHECKABLE | INHERITED
    CHECK: <exact command or procedure>        (CHECKABLE only)
    EXPECTED: <what a passing re-run shows>    (CHECKABLE only)
    PROVENANCE: <source commit/conversation>   (INHERITED only)

## 2026-07-06T02:44:31Z | Claude Fable 5 | 86d66709915f59893538df3ca627f148f090e554
CLAIM: okrontheus/okrontheus3 created and seeded with LEDGER.md only.
TIER: CHECKABLE
CHECK: git clone https://github.com/okrontheus/okrontheus3.git t3 && git -C t3 ls-tree -r --name-only 86d66709915f59893538df3ca627f148f090e554
EXPECTED: output is exactly "LEDGER.md".

## 2026-07-06T02:48:57Z | Claude Fable 5 | 55184add58809b35edaf92bb9a55f333af936940
CLAIM: The GEB probe seam is agreement-audit, chosen by Jeff.
TIER: INHERITED
PROVENANCE: Jeff, chat session 2026-07-06 ("Use the agreement-audit seam.")

## 2026-07-06T02:48:57Z | Claude Fable 5 | 55184add58809b35edaf92bb9a55f333af936940
CLAIM: probes/geb/PROBE.md is a self-contained agreement-audit probe, cold-runnable with deterministic scoring; its answer key was verified against live repo state before commit.
TIER: CHECKABLE
CHECK: run the protocol in probes/geb/PROBE.md against a fresh instance; score with its key; commit the run file.
EXPECTED: a new probes/geb/runs/<UTC-date>-<model>.md exists and the rubric yields a score N/5.

## 2026-07-06T02:54:44Z | Claude Fable 5 | bffb7044197f88c8e4c7b93cd571f05fe9623e44
CLAIM: First agreement-audit run: subject claude-fable-5 (cold subagent, clone at 4a1dc78) scored 5/5 PASS.
TIER: CHECKABLE
CHECK: apply PROBE.md's regex to the five verbatim response first-lines in probes/geb/runs/2026-07-06-claude-fable-5.md and re-score against its key.
EXPECTED: re-scoring reproduces 5/5 PASS. (Re-running the probe itself is a NEW run file, never this one.)
