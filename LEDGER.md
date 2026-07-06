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
