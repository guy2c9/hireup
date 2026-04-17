# Hireup Project — Session History

## 2026-04-16 — JIRA Scope Analysis

**Objective:** Analyse 97 JIRA tickets from the Hireup payroll implementation project against the original scope documents to identify scope creep and feature requests.

**Documents reviewed:**
- Hireup SOW — Final — August 25.docx (SOW No. 20250717H, $170,000)
- HireUp — Requirements workbook (User Stories).xlsx
- HireUp — Payroll Discovery Workbook FINAL 20260115.xlsx
- Hireup — RAID.xlsx
- INTERNAL Hireup Program — Copy of Timeline (version 3) High Level.xlsx
- JIRA.xml (97 tickets from PAYM project)

**Results:**
- 69 tickets (71%) classified as **in scope**
- 16 tickets (16%) classified as **scope creep / feature requests**
- 3 tickets (3%) classified as **borderline**

**Key scope creep themes identified:**
1. Portable LSL — 3 tickets (PAYM-159, PAYM-173, PAYM-241) — entirely new compliance stream not in SOW
2. Custom UI widget for adhoc timesheets (PAYM-334)
3. Slack integration (PAYM-166) — tagged "Nice to have"
4. PPT minimum contracted hours custom solution (PAYM-271)
5. FDVL pay advice suppression (PAYM-279)
6. Additional reports and GL enhancements (PAYM-98, PAYM-151)
7. Training pay code GL splits (PAYM-358)
8. Custom payslip email body (PAYM-337)

**Output:** `docs/jira-scope-analysis.md` — initial analysis with ticket classifications.

### Update — Detailed Source References for In-Scope Items

Expanded the in-scope section of `docs/jira-scope-analysis.md` to include:
- Specific source document references for every in-scope ticket (exact SOW section, Requirements Workbook user story row, Discovery Workbook sheet, Timeline row, and/or RAID entry)
- Explanation of why each ticket qualifies as in scope
- Consolidated master table of all 88 tickets with classification tag, source references, and explanation in a single view

**Document abbreviations used throughout:**
- **SOW** — Hireup SOW — Final — August 25.docx (SOW No. 20250717H)
- **RW** — Requirements workbook, "Hireup Requirements" sheet
- **RW-PE** — Requirements workbook, "Project Evolution" sheet
- **DW** — Payroll Discovery Workbook FINAL 20260115.xlsx
- **RAID** — Hireup — RAID.xlsx
- **TL** — Timeline (version 3) High Level.xlsx

**Final output:** `docs/jira-scope-analysis.md` — complete analysis with full source traceability for all 88 tickets.

### Update — Multi-Agent Independent Review

Conducted a second-pass review using 3 independent review agents to challenge the initial classifications:

**Agent 1 — SOW Gap 2 (Sleepover) strict contractual review:**
Examined all 8 tickets classified under SOW Gap 2 against the exact gap wording: *"Need to configure sleepover bookings so compliance hours are at the lower rate. Also we need to understand how to send through sleepovers without any time worked."* Found the gap is far narrower than initially assumed — 6 of 8 tickets reclassified as scope creep, 1 as borderline.

**Agent 2 — Non-gap in-scope ticket review:**
Critically reviewed 15 tickets including the 4 Simplification tickets, daily OT, short shifts, Hibiscus release, and others. Found the Simplification cluster (PAYM-327–330) represents rework of failed designs rather than refinement. Found PAYM-262 (Hibiscus) explicitly excluded by SOW Section 5.

**Agent 3 — Scope creep/borderline counter-check:**
Verified all 16 scope creep and 3 borderline tickets. Found 5 tickets softened from scope creep to borderline (RW user stories partially cover them). Found PAYM-174 should be in scope (tracking only, no build).

**Reclassifications applied:**

| Direction | Count | Tickets |
|---|---|---|
| In Scope → Scope Creep | 8 | PAYM-45, PAYM-262, PAYM-312, PAYM-313, PAYM-319, PAYM-324, PAYM-325, PAYM-326 |
| In Scope → Borderline | 9 | PAYM-232, PAYM-273, PAYM-293, PAYM-327, PAYM-328, PAYM-329, PAYM-330, PAYM-342, PAYM-347 |
| Scope Creep → Borderline | 5 | PAYM-151, PAYM-311, PAYM-335, PAYM-337, PAYM-358 |
| Borderline → In Scope | 1 | PAYM-174 |

**Revised results:**

| Category | Original | Revised | Change |
|---|---|---|---|
| In Scope | 69 (71%) | 53 (60%) | -16 |
| Scope Creep | 16 (16%) | 19 (22%) | +3 |
| Borderline | 3 (3%) | 16 (18%) | +13 |

**Key findings:**
1. SOW Gap 2 (Sleepover) is narrowly worded — "minimum sleepover top-up" mechanism (IFA-specific) is not covered
2. The 4 Simplification tickets (327–330) are rework of initial designs, not refinement — SOW commits to one build cycle
3. PAYM-262 (Hibiscus release) explicitly excluded by SOW Section 5 Assumption 8
4. PAYM-334 (custom UI widget) has already been built — flag for commercial reconciliation regardless of classification

### Output — Excel Workbook

Generated `docs/Hireup JIRA Scope Analysis.xlsx` with 5 formatted sheets:

| Sheet | Contents |
|---|---|
| Summary | Revised counts (53/19/16), key findings |
| All Tickets | Master table — all 88 tickets colour-coded (green/red/orange), frozen header, auto-filter |
| Scope Creep | Filtered view of 19 scope creep tickets with explanations |
| Borderline | Filtered view of 16 borderline tickets with explanations |
| Reclassifications | All 23 tickets that changed classification, original → revised with rationale |

Google Sheets version pending — 2cloudnine MCP has read/update/format tools but no create tool. User to create blank sheet for population.

**Repo:** https://github.com/guy2c9/hireup (private)

## 2026-04-16 — XML-Aligned Deliverables and Commercial Packaging

Follow-up work converted the revised analysis into deliverables aligned strictly to the tickets present in `Downloads/JIRA.xml`.

**Key updates:**
- Created `docs/jira-ticket-classification-xml.csv` with one row per ticket found in the XML export.
- Filtered the final table to the `97` tickets actually present in `JIRA.xml`.
- Preserved the per-ticket fields requested by the user: `Ticket`, `Summary`, `Classification`, `Source References`, and `Explanation`.
- Created `docs/jira-scope-creep-themes.md` to group the `19` scope-creep / feature-request tickets into commercial Change Request themes.

**Important reconciliation note:**
- The older workbook `docs/Hireup JIRA Scope Analysis.xlsx` contains `98` ticket rows.
- The extra ticket is `PAYM-187`, which is present in the older workbook/markdown analysis but **not** in `Downloads/JIRA.xml`.
- The CSV deliverable intentionally excludes `PAYM-187` so the final output remains faithful to the XML source requested by the user.

**Final XML-aligned counts:**

| Category | Count |
|---|---:|
| In Scope | 63 |
| Scope Creep / Feature Request | 19 |
| Borderline | 15 |
| Total XML Tickets | 97 |

**Commercial scope-creep themes packaged for CR discussion:**
1. Sleepover engine extension — 7 tickets
2. Portable LSL compliance stream — 3 tickets
3. Future product release adoption (Hibiscus) — 1 ticket
4. Minimum contracted hours automation — 1 ticket
5. FDVL / pay advice compliance — 1 ticket
6. GL reporting enhancement — 1 ticket
7. Slack / alerting integration — 1 ticket
8. Operational tooling / audit / monitoring — 3 tickets
9. Custom UI for ad hoc timesheet entry — 1 ticket

**Files added:**
- `docs/jira-ticket-classification-xml.csv`
- `docs/jira-scope-creep-themes.md`

## 2026-04-17 — Finalised Multi-Agent Review and Commercial Strategy

Follow-up session to finalise the scope analysis with a second multi-agent review pass and produce a clean deliverable.

**Multi-Agent Review (Pass 2) — Three finalisation agents:**

1. **Contractual Defensibility Agent** — Scored all 19 scope creep tickets on a 1–5 defensibility scale, assessed likely client pushback, and estimated commercial value (T-shirt + $ range). Found 7 tickets rock-solid (5/5), 8 strong (4/5), and 4 moderate (3/5).

2. **Borderline Risk Assessment Agent** — Assessed all 15 borderline tickets with lean percentages (% in scope vs out), risk levels, and recommended commercial approach. Triaged into: 5 Absorb, 7 Negotiate, 3 CR.

3. **Commercial Packaging Agent** — Recommended bundling 19 scope creep tickets into 3 Change Requests with negotiation strategy, concession tactics, and timing guidance.

**Commercial Strategy Outputs:**

| CR | Themes | Est. Value |
|---|---|---|
| CR-1 | Sleepover Engine Extension (7 tickets) | $20k–$25k |
| CR-2 | Portable LSL Compliance (3 tickets) | $25k–$35k |
| CR-3 | Enhancements & Integrations bundle (9 tickets) | $14k–$20k |

| Metric | Low | High |
|---|---|---|
| Total scope creep | $44,000 | $59,000 |
| Net recoverable (after goodwill concessions) | $46,000 | $67,000 |
| Goodwill investment | $13,000 | $20,000 |

**Key negotiation recommendations:**
1. Raise CR-1 and CR-2 before PPT2 completes — strongest positions
2. Absorb 5 borderline tickets as goodwill (~$8–12k) to strengthen credibility
3. Negotiate 50/50 split on Simplification cluster (327–330) — shared accountability
4. Offer 10–15% package discount if all 3 CRs approved together
5. PAYM-334 (custom widget) already built — include in CR-3 at reduced rate

**Google Sheet updated:** `Hireup Commercials - JIRA vs Original Scope`
- All Tickets tab completed (28 missing rows appended)
- Scope Creep tab: added defensibility scores, $ estimates, client pushback columns
- Borderline tab: added lean %, risk level, commercial approach columns
- Review Findings tab: rewritten with full commercial strategy

**New deliverable:** `docs/Hireup Scope Analysis — Finalised.xlsx` — clean 5-tab workbook with full formatting, colour-coding, and all finalised data. Intended for upload to Google Drive as a replacement for the original sheet.

**Files added/updated:**
- `docs/Hireup Scope Analysis — Finalised.xlsx` (new)
- `docs/history.md` (updated)

## Authoritative Deliverable

`docs/Hireup Scope Analysis — Finalised.xlsx` is the **final, authoritative version** for all client-facing and commercial activity.

The other artefacts in `docs/` are working documents from earlier passes and are **superseded**:

| File | Status |
|---|---|
| `docs/Hireup Scope Analysis — Finalised.xlsx` | **Authoritative — use this** |
| `docs/Hireup JIRA Scope Analysis.xlsx` | Superseded (earlier 88/98-row workbook, includes PAYM-187 not in XML) |
| `docs/jira-scope-analysis.md` | Superseded (53/19/16 counts do not match final 63/19/15 XML-aligned figures; internal inconsistencies in section headings) |
| `docs/jira-ticket-classification-xml.csv` | Superseded (snapshot of data now reflected in Finalised xlsx) |
| `docs/jira-scope-creep-themes.md` | Superseded (CR theming consolidated into the Finalised workbook) |

**Final authoritative counts:** 63 In Scope, 19 Scope Creep, 15 Borderline (97 total XML-aligned tickets).

## 2026-04-17 — Hireup Workflow Codified as Reusable MCP Skill

Submitted a new 2cloudnine MCP skill — `scope-management` — that captures the workflow used on Hireup for re-use on future engagements.

**Skill summary (7 steps):**
1. Ingest scope materials (SOW/DW/RW/RAID/plan/CRs) with an abbreviation table
2. Ingest the working register — encourages providing the top-level sources (Google Drive folder, JIRA project key + XML, Salesforce engagement) rather than individual files
3. First-pass classification with specific source citations
4. Multi-agent independent review (3 agents: contractual strict, non-gap in-scope, scope-creep counter-check)
5. Commercial packaging into CR themes (defensibility score, $ range, client pushback)
6. Produce xlsx deliverable (Summary, All Tickets, Scope Creep, Borderline, CR Package, Reclassifications log)
7. Save outcome via `project_save` — linked to the existing `project-artifacts` skill

**Gotchas baked in (Hireup-derived lessons):**
- SOW wording is narrower than it feels — cite exact section, not generic references
- Parent epics vs child tickets — epics are containers, not countable scope creep
- Future-release exclusions (Assumption 8) — almost always scope creep
- Already-built scope creep (e.g. PAYM-334) — flag for commercial reconciliation
- Simplification / rework (e.g. PAYM-327–330) — shared accountability, borderline not in-scope
- Ticket-count drift across exports (XML vs CSV vs workbook) — name the authoritative source
- Reporter matters — customer-raised tickets carry more commercial weight than internal ones

**Submission tracking:**

| Item | Pilot Issue |
|---|---|
| `scope-management` skill | **ART-2057** |
| 'project management' domain feature request | **ART-2058** |
| Output structure / gotcha additions for ART-2057 | **ART-2059** |

Skill filed under `documentation` domain (closest valid fit). ART-2058 requests a new `project management` domain so scope/CR/delivery-governance skills have a proper home. If approved, the skill frontmatter will be updated from `documentation` to `project management`.

### Output Structure Update — ART-2059

After inspecting the two authoritative Hireup workbooks, filed a follow-up against ART-2057 to fold the exact output specification into the skill before delivery. Workbook structure captured:

**Workbook A — Baseline Scope Classification** (file: `{Customer} Scope Analysis — Finalised.xlsx`)
- Tab 1: Executive Summary (project info, counts, commercial headline)
- Tab 2: All Tickets — `Ticket | Summary | Type | Status | Priority | Classification | Source References | Explanation`
- Tab 3: Scope Creep — CR Themes — `Theme | Tickets | Why Out of Scope | Recommended CR Wording | Estimate T-shirt | $ Low | $ High | Defensibility (1–5) | Client Pushback`
- Tab 4: Borderline — `Ticket | Summary | Lean % In | Lean % Out | Risk Level | Recommended Approach | Rationale`
- Tab 5: Review Findings — multi-agent outcomes, reclassifications log, commercial strategy

**Workbook B — CR-Aware Commercial Reconciliation** (file: `{Customer} — CR-Aware Commercial Reconciliation.xlsx`)
- Tab 1: Executive Summary (CR count, totals, risks, carve-outs)
- Tab 2: CR Register — `CR ID | Title | Status | Date Raised | Date Signed | $ Low | $ High | Agreed $ | Ticket Count | Priority | Contractual Basis | Notes`
- Tab 3: Ticket–CR Map — `Ticket | Summary | Original Class | Revised Class | Assigned CR | Coverage | Confidence | Rationale | Carve-out Flag`
- Tab 4: Commercial Actions — `# | Action | Owner | Timing | Status | $ Impact Low | $ Impact High | Dependencies | Notes`
- Tab 5: Risk Register — `# | Risk | Severity | Linked CR | Mitigation | Owner | Status | Date Identified`

**Formatting rules:** green/red/orange row shading by classification, frozen header + auto-filter, `$` with thousands separator, dates DD/MM/YYYY (AU), British spelling, exact file naming.

**New Gotcha added:** fault-admitting CR language ("Discovery under-scoped") admits 2cloudnine fault under SOW 3.2 — reframe as "emergent requirement during build" (lesson from Hireup CR02).

**Why direct skill update failed:** `skill_authoring_submit` with `skillId` and `skill_authoring_request_update` both returned internal errors — the skill is in the delivery queue, not yet in the live registry. ART-2059 is the path for the delivery team to incorporate during build.

**Why this matters for Hireup specifically:** Any future revisions to the Hireup scope analysis should run through the `scope-management` skill workflow for consistency. When the skill becomes live on the 2cloudnine MCP, invoke it directly rather than ad-hoc repeating the Hireup steps.

## 2026-04-17 — CR-Aware Reconciliation (Pass 3)

Second multi-agent review pass triggered by discovery of three new CR/process documents supplied by Guy:
- `Hireup CR01 - Shift-Level Payroll Tax & FP_NFP Cost Item.docx` (Andrew Humann, 27/11/2025, $16,000)
- `Hireup CR02 - Additional Information in Pay Advices.docx` (Andrew Humann, 20/01/2026, $6,000)
- `Hireup – Project Evolution 2cloudnine Process Changes.docx` (Julian McGrath, December 2025 — 5-stage process design)

**4 independent agents dispatched:**

1. **Agent A — CR01 Ticket Mapping:** Concluded CR01 is **net-new scope**, not capture of existing scope creep. No JIRA ticket in the 97-ticket set references shift-level location or FP/NFP cost items. $16k materially under-priced (true effort $24k–$30k). Existing 3-CR pipeline ($46k–$67k) remains fully live and undiminished.

2. **Agent B — CR02 Ticket Mapping:** Identified PAYM-167, 329, 337, 342, 123 as covered by CR02. Flagged $6k as under-priced (60–100 hrs realistic → $15k–$22.5k). CR02 language "significantly more complex than initially identified from Discovery" is a **contractual gift to Hireup** — Discovery is a 2cloudnine deliverable under SOW 3.2; the phrase admits 2c9 fault.

3. **Agent C — Project Evolution Impact:** Classified the 5 stages. Stages 1–3 covered by CR01. **Stage 4 (month-end reclassification, SRO Part/All toggle) is scope creep. Stage 5 (journal reversal → correction → linkage audit trail) is borderline-leaning-creep**, beyond CR01's passing "journal reversal capability" line. Identified 4 new scope items not in 97-ticket set.

4. **Agent D — Commercial Reconciliation:** Produced revised commercial position. Recommended new **CR-4 Project Evolution Addendum ($31k–$50k)** for Stages 4–5. Ticket reclassifications: PAYM-167 → CR02, PAYM-329 → CR02, PAYM-337 → CR02, PAYM-342 → CR02, PAYM-358 → CR01 template coverage.

**Revised commercial position:**

| Metric | Original | Post-CR | Δ |
|---|---|---|---|
| Net Recoverable Low | $46,000 | **$108,000** | +$62,000 |
| Net Recoverable High | $67,000 | **$142,500** | +$75,500 |
| % of $170k SOW | 27–39% | **64–84%** | +37pp |

**Breakdown of additional recoverable:**
- CR01 raised $16,000 (signing pending)
- CR02 raised $6,000 (recommend rewrite for +$9k–$16.5k uplift)
- CR-4 Project Evolution Addendum $31k–$50k (new, recommended)

**Top contractual risks surfaced:**
- CR02 "Discovery under-scoped" language admits 2c9 fault — must be rewritten before signing
- CR01 "journal reversal capability" could be read broadly to subsume Stage 4–5 — requires covering letter carve-out before countersignature
- Dec-2025 Project Evolution doc post-dates Nov-2025 CR01 — document as "emergent post-CR" to preserve CR-4 position

**Top 10 commercial actions documented in new deliverable.**

### New Deliverable

`docs/Hireup SCHADS — CR-Aware Commercial Reconciliation.xlsx` — 5-tab formatted workbook supplementing the authoritative Finalised.xlsx (does NOT replace it):

| Tab | Contents |
|---|---|
| 1. Executive Summary | Revised commercial position, headline, CR table |
| 2. CR Register | 7 CRs tracked (CR01, CR02, CR02-Uplift, CR-1, CR-2, CR-3, CR-4) with $ ranges, status, contractual basis |
| 3. Ticket–CR Map | All 40 non-in-scope + adjacent tickets mapped to CRs with confidence ratings |
| 4. Commercial Actions | Top 10 actions with owner, timing, $ impact, dependencies |
| 5. Risk Register | 10 contractual risks with severity, mitigation, linked CR |

**Working documents added:**
- `docs/cr-extracts/CR01-Shift-Level-Payroll-Tax.txt` (extracted from docx)
- `docs/cr-extracts/CR02-Additional-Info-Pay-Advices.txt`
- `docs/cr-extracts/Project-Evolution.txt`
- `docs/cr-extracts/Finalised-xlsx-dump.txt`
- `docs/cr-extracts/agent-a-cr01.md` (Agent A findings)
- `docs/cr-extracts/agent-b-cr02.md` (Agent B findings)
- `docs/cr-extracts/agent-c-project-evolution.md` (Agent C findings)
- `scripts/build_cr_aware_xlsx.py` (deliverable generator)

**Google Sheet note:** 2cloudnine MCP has no `create_spreadsheet` tool, only read/update/format/append. The local xlsx is ready to upload to Google Drive (auto-converts to a native Google Sheet). The existing `Hireup Commercials — JIRA vs Original Scope` Google Sheet is NOT touched. A separate new Sheet will be used once the blank container is created.
