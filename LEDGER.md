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
