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
