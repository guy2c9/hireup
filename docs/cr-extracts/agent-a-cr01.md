# Agent A — CR01 Mapping (Shift-Level Payroll Tax)

## Headline
CR01 is net-new scope, NOT a capture of existing scope creep. $16k materially under-priced; Project Evolution Stages 4–5 are bundled in at zero.

## Tickets Directly Covered
None.

## Tickets Partially Covered
| Ticket | Summary | Current | How CR01 Touches | Uncovered | Conf |
|---|---|---|---|---|---|
| PAYM-98 | GL Report — dual-location | Scope Creep | Supplies shift-level Location data model | GL report build (columns, layout) | High |
| PAYM-145 | Change of State & LSL | In Scope | State changes become first-class | LSL accrual logic, PLSL linkage | Med |
| PAYM-342 | Reversed Txns on Pay Advice | Borderline-Negotiate | Introduces reversal mechanism | Pay advice UI | Med |
| PAYM-357 | GL Account codes review | In Scope | Doubles GL surface (FP+NFP per state) | QA scope grows | Med |
| PAYM-358 | Training GL split | Borderline-Negotiate | Dual-cost-item template pattern | Training-specific codes | Low |
| PAYM-115 | GL Integration (Netsuite) | In Scope | Must carry FP/NFP + reversal journals | Complexity grows | Med |

## NOT Covered — Existing CR Pipeline Stays Live
CR-1 Sleepover (7 tickets, $20k–$25k), CR-2 Portable LSL (3 tickets, $25k–$35k), CR-3 Bundle (9 tickets, $14k–$20k) — all UNTOUCHED by CR01.

## Commercial Verdict on $16k
Materially under-priced. $10k dev = 40 hrs flat for: new TSE field + engine selection + paired FP/NFP cost items (14–16 items) + journal reversal + month-end recalc + SRO Part/All toggle + backward compat. Comparable Sleepover engine work = $20k–$25k for narrower scope. CR01 absorbs Stage 4/5 risk = $8k–$12k uncaptured standalone value.

## Is CR01 NEW scope?
Yes. No ticket in the 97-ticket set references shift-level location, FP/NFP cost items, or state payroll tax. PAYM-121/243 refer to the ORIGINAL Project Evolution CR1 (already in scope). This is a second, separate structural change. Clean contractual defensibility as new scope.

## Recommendation
Accept $16k for speed IF client needs pre-3/12/25 approval, but carve out (i) month-end recalculation mode, (ii) PAYM-98 GL report build as separate line items. Otherwise Hireup will treat them as included.
