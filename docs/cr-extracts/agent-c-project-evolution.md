# Agent C — Project Evolution Scope Impact

## Headline
Stages 1–3 covered by CR01. Stages 4–5 are UNPRICED scope creep worth **$31k–$50k**. Raise as CR-4 Addendum.

## Existing vs Net-New
Mixed. RW-PE sheet in discovery; PAYM-121 "Build Integration — Project Evolution CR1" already In Scope. BUT December 2025 process doc goes materially beyond CR01 (Nov 2025).

## 5 Stages Classification
| Stage | Class | Reason |
|---|---|---|
| 1 Shift-level Location | In Scope (via CR01) | CR01 bullet 1 |
| 2 FP/NFP classification | In Scope (via CR01) | CR01 bullet 2 |
| 3 State-based cost items | In Scope (via CR01) | CR01 bullet 2 |
| 4 Month-end reclassification / FP-only vs Part/All / SRO | **Scope Creep** | Not in CR01, SOW 3.3, or 3.5. No JIRA ticket covers. |
| 5 GL journal reversal + correction + audit linkage | **Borderline-lean-creep** | CR01 mentions "reversal capability" in passing; 3-way linkage (original→reversal→correction) is new |

## CR01 Gap
CR01 covers Stages 1–3 explicitly, Stage 5 partially (reversal only, no correction/linkage), Stage 4 NOT AT ALL. Classic scope drift after sign-off.

## Relevant Tickets
PAYM-121, PAYM-243 (In Scope — original CR1), PAYM-98 (Scope Creep — dual-location GL), PAYM-115 (GL Netsuite), PAYM-357 (GL codes), PAYM-342 (reversal display — Borderline), PAYM-358 (Training GL), PAYM-145 (cross-border LSL).

## 4 NEW Scope Items Not in 97-Ticket Set
1. Month-end FP-only vs Part/All toggle (SRO-driven)
2. SRO ruling response workflow
3. Retrospective pay-period recalculation across month
4. Linked audit trail original→reversal→correction

## Indicative $ Exposure
| Item | Low | High |
|---|---|---|
| Month-end recalc engine (Stage 4) | $15,000 | $25,000 |
| SRO mode toggle + config | $3,000 | $5,000 |
| Reversal/correction/linkage uplift (Stage 5 beyond CR01) | $8,000 | $12,000 |
| UAT + regression for retrospective engine | $5,000 | $8,000 |
| **Total additional exposure** | **$31,000** | **$50,000** |

## Contractual Risks
- CR01 "journal reversal capability" could be read broadly — clarify in writing NOW that CR01's 24-hr T&M did not contemplate correction/linkage or month-end recalc
- Timing preserves position: Dec 2025 design doc post-dates Nov 2025 CR01 — document as emergent post-CR
- SOW §5 Assumption 8 parallel: same logic that excludes Hibiscus supports excluding Stages 4–5

## Combined Recoverable (Post-PE Addendum)
Existing 3 CRs: $46k–$67k + New CR-4 (Project Evolution Addendum): $31k–$50k = **$77k–$117k total recoverable (45–69% of $170k SOW)**

## Recommendation
Raise CR-4 "Project Evolution — Month-End & Audit Trail" before any Stage 4/5 development starts. Sequence after CR-1/CR-2 but before PPT2 completes.
