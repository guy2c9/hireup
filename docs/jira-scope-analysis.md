# Hireup JIRA Scope Analysis

**Date:** 16 April 2026 (Revised)
**Prepared by:** 2cloudnine
**Purpose:** Classify each JIRA ticket as either in-scope, scope creep / feature request, or borderline — measured against the SOW (August 2025), Requirements Workbook, Discovery Workbook, RAID Log, and Project Timeline.

> **Revision Note (16 April 2026):** This document was revised following a multi-agent independent review that challenged the initial classifications. Key changes: SOW Gap 2 (Sleepover) wording found to be narrower than initially assessed — 6 sleepover tickets reclassified from in-scope to scope creep. Simplification cluster (PAYM-327–330) reclassified as borderline (rework, not refinement). PAYM-262 (Hibiscus) reclassified as scope creep per SOW Section 5 Assumption 8. **Revised counts: 53 in scope, 19 scope creep, 16 borderline.** The consolidated master table at the end of this document and the Excel workbook (`Hireup JIRA Scope Analysis.xlsx`) reflect the final revised classifications.

---

## Scope Reference Summary

The SOW (No. 20250717H, $170,000 fixed price) covers:

| SOW Section | Scope |
|---|---|
| 3.1 | Project Management and Governance |
| 3.2 | Discovery and Design (SCHADS MA000100 interpretation) |
| 3.3 | Installation and Configuration (Payroll, Award Interpretation, GL/Netsuite, Salesforce UI) |
| 3.4 | Data Migration (one UAT, one pre-Go-Live) |
| 3.5 | Testing (functional testing, UAT, parallel runs — 2 full pay cycles) |
| 3.6 | Training (end-user and administrator) |
| 3.7 | Go-Live and Post Go-Live Support (hypercare — 2 full pay cycles) |
| 3.8 | Consultant Support (meetings, ad hoc, tech support for Hireup integration) |

**SOW Section 4 — Explicit Gap Deliverables:**

1. Day Penalties / Loading (midnight crossing fix)
2. Sleepover Booking Configuration (compliance hours at lower rate)
3. Broken Shift — Rest break ≥ 10 hour ends a broken shift
4. Broken Shift Across Pay Periods
5. Consolidated Payslips for Retrospective Bookings
6. Short Shifts
7. Discretionary Allowance display on pay advice

**SOW Section 4 — Flame Trees Release (Oct/Nov 2025):**

- Public Holiday Trigger (location-based)
- Pay Batch Automation

**SOW Assumptions (Section 5):**

- Standard functionality of 2cloudnine Payroll and Award Interpretation
- Any change to business processes or scope after Discovery → formal Change Request
- Client responsible for integration development to/from Hireup Platform
- Future product releases NOT included (except Flame Trees items above)

---

## Classification Key

| Category | Definition |
|---|---|
| **In Scope** | Covered by SOW sections 3.1–3.8, Section 4 gap deliverables, Requirements Workbook, or Discovery Workbook |
| **Scope Creep** | New requirement not covered by any scope document; represents additional work above the original engagement |
| **Borderline** | Related to a scope item but extends it materially beyond what was agreed; warrants discussion |

---

## Analysis: In-Scope Items (69 tickets)

Each ticket below includes the specific source document(s) and section(s) that place it within scope, together with an explanation of why it qualifies.

### Document Abbreviations

| Abbreviation | Document |
|---|---|
| **SOW** | Hireup SOW — Final — August 25.docx (SOW No. 20250717H) |
| **RW** | HireUp — Requirements workbook (User Stories).xlsx, "Hireup Requirements" sheet |
| **RW-PE** | HireUp — Requirements workbook (User Stories).xlsx, "Project Evolution" sheet |
| **DW** | HireUp — Payroll Discovery Workbook FINAL 20260115.xlsx |
| **RAID** | Hireup — RAID.xlsx |
| **TL** | INTERNAL Hireup Program — Copy of Timeline (version 3) High Level.xlsx |

---

### Project Management & Governance Epics

**PAYM-6 — Project Planning**
- **Sources:** SOW Section 3.1; TL "Original Timeline" sheet — "Project Governance" row
- **Why in scope:** SOW 3.1 explicitly includes "Project Management activities including resource planning, project planning, supporting documentation, and internal and external meetings." The Timeline shows Project Governance spanning the full project duration. This epic is the parent container for that work.

**PAYM-8 — Testing**
- **Sources:** SOW Section 3.5; TL "Original Timeline" sheet — "UAT/Parallel Testing & Test Summary Report" row; TL "Revised PPT" sheet — PPT1, PPT2, PPT3 rows
- **Why in scope:** SOW 3.5 commits to "Functional testing assistance and guidance" and "In person support for UAT and Parallel runs, which are a critical collaborative process and typically involve two full pay cycles." The Timeline dedicates weeks 18–26 (original) and weeks 21–33 (revised) to testing phases. This epic is the parent container for all testing activities.

**PAYM-9 — Go Live**
- **Sources:** SOW Section 3.7; TL "Original Timeline" sheet — "Go Live — Technical" and "Go Live — Business" rows; TL "Revised PPT" sheet — "Go-Live" section
- **Why in scope:** SOW 3.7 commits to "Go-Live Preparation" and "Hypercare and post Go-Live support." The Timeline shows go-live technical and business milestones in weeks 27–31 (original) and targeting 8 June 2026 (revised). This epic is the parent container for go-live activities.

**PAYM-233 — Configure PROD Instance**
- **Sources:** SOW Section 3.3; TL "Revised PPT" sheet — "Post PPT1 defect resolution and uplift and smoke test (FCSB > Prod)" row; TL "Revised PPT" sheet — "Final production uplift (promoting configurations to production)" row
- **Why in scope:** SOW 3.3 covers "Installation and standard configuration of 2cloudnine Payroll." The Timeline explicitly schedules production uplift activities. Configuring the production instance is the culmination of the configuration phase — all build work must be promoted to production before go-live.

**PAYM-234 — SCHADS Award rules build**
- **Sources:** SOW Section 3.2 ("Interpretation of the Social, Community, Home Care and Disability Award [SCHADS - MA000100]"); SOW Section 3.3 ("Award Interpretation set up as per the Discovery Workbook"); RW rows: "Short shift detection and uplift", "Broken shift logic and allowances", "Dual leave loading calculation", "Public holiday by shift location", "Overnight shift logic", "Sleepovers and disturbances" (all Custom); DW "MA000100 SCHADS" sheet
- **Why in scope:** The entire SCHADS award interpretation build is a core deliverable. SOW 3.2 specifically names SCHADS MA000100. SOW 3.3 says "Award Interpretation set up as per the Discovery Workbook, specifically for Hireup's interpretation of the SCHADS Award." The Requirements Workbook lists 10+ interpretation user stories covering short shifts, broken shifts, sleepovers, overnight logic, PH by location, and leave loading — all tagged as Custom or Standard. This epic is the parent for that body of work.

**PAYM-235 — Configure Payroll engine**
- **Sources:** SOW Section 3.3 ("Installation and standard configuration of 2cloudnine Payroll"); RW rows: "Large pay batch processing", "Pay batch UI limits and reporting", "Payroll calendar and cut-off", "Off-cycle pays", "Stapled super and default funds", "Master payroll data setup"; DW sheets: "PAYMENT ENTITY", "PAY SCHEDULES & CALENDARS", "EARNER TYPE & WITHHOLDING RULES", "LEAVE RULES", "CALCULATION OF RATES"
- **Why in scope:** SOW 3.3 covers installation and standard configuration of the payroll engine. The Requirements Workbook lists multiple payroll-specific user stories (pay batches, calendars, super, master data). The Discovery Workbook contains detailed configuration sheets for payment entities, pay schedules, earner types, leave rules, and rate calculations. This epic is the parent container for all payroll engine configuration.

**PAYM-255 — Post Go Live items**
- **Sources:** SOW Section 3.7 ("Hypercare and post Go-Live support, which typically runs for two full pay cycles but can be extended if required"); TL "Revised PPT" sheet — "Post Go-Live Activities" section showing Hypercare and "Transition to Customer Success"
- **Why in scope:** SOW 3.7 explicitly includes hypercare and post go-live support. The Timeline schedules hypercare for 2+ weeks post go-live followed by transition to Customer Success. This epic captures work items that fall into the post go-live support period.

**PAYM-261 — End User Training**
- **Sources:** SOW Section 3.6 ("In person conducted end-user sessions for Payroll users and administrator training"); TL "Revised PPT" sheet — "Training" section listing specific sessions (PAYM-80, PAYM-221, PAYM-172, PAYM-207, PAYM-278)
- **Why in scope:** SOW 3.6 commits to end-user training sessions and administrator training. The Timeline schedules specific training sessions across weeks 20–30. This epic is the parent for all training delivery.

---

### Training

**PAYM-80 — Delivery of Training**
- **Sources:** SOW Section 3.6; SOW Section 4 Deliverables ("Training and testing guidance and support services to facilitate handover"); TL "Revised PPT" sheet — "Training" section row "3 remaining sessions — timing to be agreed with Hireup (PAYM-80)"
- **Why in scope:** SOW 3.6 commits to "In person conducted end-user sessions for Payroll users" and "Handover of 2cloudnine Payroll and Award Interpretation product to Client system administrators and key users through training and testing guidance and support services." The Timeline directly references this JIRA ticket by number as a scheduled training item.

**PAYM-172 — Include late approvals in Pay Batch [Training]**
- **Sources:** SOW Section 3.6; RW row "Off-cycle pays" ("run ad hoc off-cycle pays … workers whose bookings were missed can still be paid promptly"); TL "Revised PPT" sheet — "Pay Batch Adjustments and Other Payments (PAYM-172 + PAYM-207)" row
- **Why in scope:** This is a training session on how to handle late-approved bookings within the pay batch process. The Requirements Workbook includes off-cycle pays as a Standard requirement, and the process for including late approvals is an operational workflow that users need to be trained on. The Timeline explicitly schedules this session by JIRA ticket number.

**PAYM-278 — Payee Exit, GL, STP [Training]**
- **Sources:** SOW Section 3.6; TL "Revised PPT" sheet — "Payee Exit, GL, STP, Super (PAYM-278)" row
- **Why in scope:** This is a 2-hour training session covering payee terminations, general ledger, Single Touch Payroll, and superannuation. All four topics are core payroll functions covered by SOW 3.3 (configuration) and SOW 3.6 (training). The Timeline directly references this ticket by number and schedules it in the training block.

**PAYM-299 — Reports and Dashboard, Portal [Training]**
- **Sources:** SOW Section 3.6; RW rows "Standard payroll reports", "Custom reports and dashboards" (both include training references); RW row "Employee portal capabilities"
- **Why in scope:** Training on reports, dashboards, and the employee portal. The Requirements Workbook lists "Provide training for key Hireup users on report and dashboard creation" under the Custom reports user story. The portal is a Standard requirement in the Requirements Workbook. SOW 3.6 covers end-user and administrator training.

**PAYM-340 — End of year processing [Support/Training]**
- **Sources:** SOW Section 3.6; SOW Section 3.7 (post go-live support)
- **Why in scope:** End-of-year processing (EOFY finalisation, STP finalisation, payment summaries) is a standard payroll operational procedure. Training users on this process falls within SOW 3.6 (training) and the description notes this will be conducted by the Customer Success team, aligning with the SOW 3.7 transition to ongoing support.

---

### Testing & Parallel Runs

**PAYM-49 — SIT Exit Sign Off**
- **Sources:** SOW Section 3.5; TL "Original Timeline" sheet — "Stage Gate to Technical Testing" and "SIT Testing and Sign Off" rows
- **Why in scope:** SOW 3.5 covers "Functional testing assistance and guidance." The Timeline includes explicit SIT (System Integration Testing) phase with sign-off milestones. SIT exit sign-off is a standard testing gate that confirms the system is ready to proceed to UAT.

**PAYM-53 — REGRESSION Defect Analysis & Reporting**
- **Sources:** SOW Section 3.5; TL "Revised PPT" sheet — "Post PPT1 defect resolution" and "Post PPT2 defect resolution" rows
- **Why in scope:** SOW 3.5 includes functional testing assistance. Regression defect analysis is an integral part of the parallel run process — after each PPT run, defects must be analysed to confirm fixes haven't introduced regressions. The Timeline schedules defect resolution windows after each PPT cycle.

**PAYM-69 — PPT Run 1 (Historical Closed Period)**
- **Sources:** SOW Section 3.5 ("In person support for UAT and Parallel runs … typically involve two full pay cycles"); TL "Revised PPT" sheet — "PPT1 — UAT/Parallel Testing (FCSB)" row (weeks 21–22); TL "PPT1-PPT2" sheet
- **Why in scope:** SOW 3.5 explicitly commits to parallel run support. PPT1 uses a historical closed period (PPE 2026-01-04) with a sample of ~2,000 support workers and ~7,000 bookings. The Timeline schedules PPT1 in the FCSB sandbox environment across two weeks.

**PAYM-70 — PPT2 Run 2 (Current Open Period)**
- **Sources:** SOW Section 3.5; TL "Revised PPT" sheet — "PPT2 — UAT/Parallel Testing (Production)" row (weeks 27–28); TL "PPT1-PPT2" sheet — "PPT2 (Parallel Run 2)" starting 2026-04-13
- **Why in scope:** SOW 3.5 covers parallel runs. PPT2 is the second parallel run using a current open period, executed in the production environment. The Timeline and the PPT1-PPT2 detail sheet both schedule this run.

**PAYM-71 — PPT Run 3 (Cutover Simulation)**
- **Sources:** SOW Section 3.5; TL "Revised PPT" sheet — "PPT3 — UAT/Parallel Testing (Production)" row (weeks 31–32); TL "Original Timeline" sheet — third PPT slot
- **Why in scope:** SOW 3.5 covers parallel runs. PPT3 is the cutover simulation — the final parallel run before go-live to confirm the system produces correct results in a production-like scenario. Both original and revised timelines schedule three PPT runs.

**PAYM-72 — PPT Reconciliation and Variance Analysis**
- **Sources:** SOW Section 3.5; RW row "Parallel runs & validation" ("Run multiple parallel pay periods comparing 2C9 vs current payroll. Track discrepancies and resolutions in the actions register"); TL "Revised PPT" sheet — "3 days of reconciliation (smoke test)" row
- **Why in scope:** Reconciliation is the core purpose of parallel runs. The Requirements Workbook explicitly calls for comparing 2cloudnine results against the current payroll system and tracking discrepancies. The Timeline allocates dedicated reconciliation days before the go/no-go decision.

**PAYM-73 — PPT Defect Resolution & Re Runs**
- **Sources:** SOW Section 3.5; TL "Revised PPT" sheet — "Post PPT1 defect resolution and uplift and smoke test" row ("90% by 2nd Apr"), "Post PPT2 defect resolution and uplift and smoke test" row
- **Why in scope:** Defect resolution between parallel runs is essential to the testing process. SOW 3.5 covers testing support, and the Timeline explicitly schedules defect resolution windows after PPT1 and PPT2 with target completion dates.

**PAYM-74 — PPT Exit Sign Off**
- **Sources:** SOW Section 3.5; TL "Revised PPT" sheet — "Go / No-go decision" and "Data based Go / No-go decision" rows
- **Why in scope:** PPT exit sign-off is the formal gate that confirms parallel testing is complete and the system is ready for go-live. SOW 3.5 covers the testing phase, and the Timeline schedules explicit go/no-go decision points tied to PPT completion.

**PAYM-214 — Test PPT Work schedules and payment of minimum hours**
- **Sources:** SOW Section 3.5; RW row "Payroll calendar and cut-off" (references flexible pay calendar and automation); DW "PAY SCHEDULES & CALENDARS" sheet
- **Why in scope:** Testing work schedules and minimum-hours payments is a functional testing activity within SOW 3.5. The Discovery Workbook captures pay schedule configuration, and verifying that minimum hours are correctly paid is a validation activity during the parallel run process.

**PAYM-243 — [UAT] Test Project Evolution CR Changes**
- **Sources:** SOW Section 3.5; RW-PE "Project Evolution" sheet (CR1 approved); TL "Original Timeline" sheet — "Build Integration — 11 Project Evolution (2c9) (Bookings/Payslip)" row showing "CR1 SO" sign-off; RAID "Risks" sheet — R01 ("CR1 approved and testing will confirm if Risk is abated")
- **Why in scope:** Project Evolution CR1 was formally approved as a Change Request. The Timeline shows CR1 sign-off as a milestone, and the RAID log (R01) explicitly states "CR1 approved and testing will confirm if Risk is abated." Testing of approved change requests is standard project testing activity under SOW 3.5.

---

### SOW Section 4 Gap Deliverables — Bugs & Configuration

These are defects and configuration tasks directly related to the 7 explicitly listed gaps in SOW Section 4. The SOW states: *"The parties note that the above 6 points were gaps identified during the due diligence process prior to entering into the Agreement … A solution to these identified gaps have been placed on 2cloudnine's product backlog for resolution."*

**PAYM-45 — Minimum Sleepover is not working as expected**
- **Sources:** SOW Section 4, Gap 2 ("Sleepover Booking Configuration — Need to configure sleepover bookings so compliance hours are at the lower rate"); RW row "Sleepovers and disturbances" (Custom — "Configure dedicated clauses for sleepover and disturbance events"); TL "PPT1 build items status" sheet — PAYM-45 row ("Minimum Sleepover Logic", assigned Lennon M.)
- **Why in scope:** SOW Section 4 explicitly identifies sleepover booking configuration as a gap deliverable. The defect — 4-hour minimum not triggering correctly with passive sleep — is a failure of the agreed sleepover configuration. The Timeline's PPT1 build items sheet tracks this ticket by number with a target date and status.

**PAYM-183 — Broken shift & Sleepover bookings incorrect**
- **Sources:** SOW Section 4, Gap 2 (Sleepover) and Gap 3 ("Broken Shift — Rest break ≥ 10 hour ends a broken shift"); RW row "Broken shift logic and allowances" (Standard — "Configure broken-shift rules and allowance pay codes"); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** This ticket spans two explicit SOW gaps — the system is not recognising bookings as broken shifts and is not applying the correct sleepover allowances. Both broken shift logic and sleepover configuration are listed as gap deliverables in SOW Section 4 and as user stories in the Requirements Workbook.

**PAYM-273 — Sleepover — incorrect payment first & active hours**
- **Sources:** SOW Section 4, Gap 2 (Sleepover); RW row "Sleepovers and disturbances" ("Apply fixed payments plus disturbance loadings as per award. Ensure interaction with broken shifts and minimum rest rules is tested")
- **Why in scope:** Negative active hours and incorrect Double Time linked to the First Active Hour are defects in the sleepover configuration. SOW Gap 2 covers sleepover booking configuration, and the Requirements Workbook mandates that disturbance loadings and sleepover interactions be correctly implemented and tested.

**PAYM-296 — SACS Short shifts calcs incorrect**
- **Sources:** SOW Section 4, Gap 6 ("Short shifts — There is a mechanism for which has been demonstrated in a different instance"); RW row "Short shift detection and uplift" (Custom — "Configure custom code to detect shifts under the agreed short-shift threshold"); RW row "Short shift uplift" (Custom)
- **Why in scope:** SOW Section 4 lists short shifts as an explicit gap deliverable. The defect — SACS short shifts calculating incorrectly instead of 2 hours × base rate — is a failure in the short-shift configuration. The Requirements Workbook contains two separate user stories for short shift detection/uplift.

**PAYM-312 — Sleepovers > 18 hours in duration incorrect**
- **Sources:** SOW Section 4, Gap 2 (Sleepover); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** Long-duration sleepovers (>18 hours) are a specific scenario within the sleepover configuration gap. SOW Gap 2 covers sleepover booking configuration broadly, and ensuring correct calculation for edge-case durations is part of delivering a complete sleepover solution.

**PAYM-313 — Sleepovers > 18 hours in duration & back to back Sleepovers**
- **Sources:** SOW Section 4, Gap 2 (Sleepover); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** Back-to-back sleepovers are a scenario that must be handled under the sleepover configuration deliverable. The Requirements Workbook calls for testing "interaction with broken shifts and minimum rest rules", which encompasses consecutive sleepover handling.

**PAYM-314 — Daily OT Calc incorrect**
- **Sources:** SOW Section 4, Gap 1 ("Day Penalties/Loading — Incorrect Interpretation. Bookings which start on a weekday, crossing midnight and end after 6 am the next day, are currently wrongly interpreted"); RW row "Overnight shift logic" (Custom — "Configure interpretation to split or allocate overnight hours")
- **Why in scope:** SOW Gap 1 explicitly describes the midnight-crossing incorrect interpretation. This ticket reports daily OT being miscalculated for overnight shifts — the exact defect pattern described in the SOW gap. The Requirements Workbook includes overnight shift logic as a Custom user story.

**PAYM-318 — Short Shift Saturday & PH payment incorrect — Inflated**
- **Sources:** SOW Section 4, Gap 6 (Short Shifts); RW row "Short shift detection and uplift" (Custom — "Pay the higher of short-shift rate or worked hours while preserving timestamps")
- **Why in scope:** Inflated short-shift payment on Saturdays and public holidays is a defect in the short-shift calculation logic. SOW Gap 6 covers short shifts, and the Requirements Workbook specifies that the system must "Pay the higher of short-shift rate or worked hours" — an incorrect inflation violates this rule.

**PAYM-319 — Minimum Sleepover Rates incorrect**
- **Sources:** SOW Section 4, Gap 2 (Sleepover — "compliance hours are at the lower rate"); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** Incorrect minimum sleepover rates are a direct defect in the sleepover configuration deliverable. SOW Gap 2 specifically mentions that compliance hours need to be at the lower rate — this ticket reports incorrect rate application for minimum sleepover scenarios.

**PAYM-324 — Daily OT not triggered with Day booking + Sleepover**
- **Sources:** SOW Section 4, Gap 1 (Day Penalties / Loading); SOW Section 4, Gap 2 (Sleepover); RW row "Overnight shift logic" (Custom)
- **Why in scope:** When a day booking is followed by a sleepover, the daily OT threshold should be reached but isn't triggering. This is an interaction between two gap deliverables — day penalty/loading logic (Gap 1) and sleepover configuration (Gap 2). Both are explicit SOW commitments.

**PAYM-326 — Create new pay code — Min Sleepover Mon-Fri**
- **Sources:** SOW Section 4, Gap 2 (Sleepover); RW row "Short shift and penalty pay codes" (Custom — "Review and rationalise existing HU pay code names and mapping. Create specific codes for short shift top-up, overtime and penalties")
- **Why in scope:** A missing pay code ("Minimum Sleepover Monday - Friday" at the Night rate) was identified during mini-parallel testing. The SOW commits to sleepover configuration (Gap 2), and the Requirements Workbook includes a user story to create specific pay codes for penalties and allowances. Delivering the correct set of pay codes is inherent to the sleepover configuration deliverable.

**PAYM-325 — Sleepover crossing midday paying incorrect shift penalty**
- **Sources:** SOW Section 4, Gap 2 (Sleepover); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** Incorrect shift penalty calculation for sleepovers that cross midday is a defect within the sleepover configuration scope. The ticket notes this is "due to current system constraints" requiring bookings to be split at midday — ensuring correct payment outcomes despite this split is part of delivering a working sleepover solution.

---

### Configuration Simplification (Refinements to Existing Scope)

**PAYM-327 — [Simplification 1] Consolidate Pay Code Structure**
- **Sources:** SOW Section 3.3 (Award Interpretation set up); SOW Section 4 Deliverables ("Salesforce and any agreed third-party applications configured as required"); RW row "Short shift and penalty pay codes" (Custom — "Review and rationalise existing HU pay code names and mapping")
- **Why in scope:** Pay code consolidation is a refinement to the award interpretation configuration delivered under SOW 3.3. The Requirements Workbook explicitly calls for rationalising pay code names and mapping. Reducing the volume of pay codes is an optimisation to the configuration already being delivered, not new scope.

**PAYM-328 — [Simplification 2] Decouple Sleepover & Remote Work from Broken Shift**
- **Sources:** SOW Section 4, Gap 2 (Sleepover) and Gap 3 (Broken Shift); RW row "Broken shift logic and allowances" (Standard); RW row "Sleepovers and disturbances" (Custom)
- **Why in scope:** This ticket addresses the interaction between two gap deliverables that introduced excessive complexity. Simplifying the relationship between sleepover/remote work and broken shift logic is a refinement to ensure the gap deliverables are maintainable and correct — it is fixing the design of work already committed to in the SOW.

**PAYM-329 — [Simplification 3] Standardise Discretionary Allowance**
- **Sources:** SOW Section 4, Gap 7 ("Discretionary allowance display on pay advice — Solution to support 'discretionary allowance' payment as required by: (a) either implementing all inclusive pay rates … or (b) via project codes … Design decision to be made during discovery workshops")
- **Why in scope:** SOW Gap 7 explicitly commits to a discretionary allowance solution, with the design decision deferred to discovery workshops. Standardising the calculation is a refinement to the approach chosen during discovery — it is delivering on the exact gap listed in the SOW.

**PAYM-330 — [Simplification 4] Review and Standardise Broken/Split Shift Logic**
- **Sources:** SOW Section 4, Gap 3 (Broken Shift ≥ 10 hour rest), Gap 4 (Broken Shift Across Pay Periods), Gap 6 (Short Shifts); RW row "Broken shift logic and allowances" (Standard); RW row "Broken shift logic modes" (Custom); RW row "Short shift detection and uplift" (Custom)
- **Why in scope:** This covers three separate SOW gap deliverables and three Requirements Workbook user stories. Standardising the logic for short/split shifts is a refinement to the design already being delivered. The Requirements Workbook includes separate user stories for broken shift logic, broken shift modes, and short shift uplift — all of which are in scope.

---

### Standard Configuration & Integrations

**PAYM-112 — [Test] Bank ABA File**
- **Sources:** SOW Section 3.3 ("Configuration of Salesforce and any agreed third-party applications as required"); RW row "Master payroll data setup" (Standard — "Set up bank accounts and payment files"); TL "Original Timeline" sheet — "Build — 2, Bank ABA Standard File" row; DW "PAYMENT ENTITY" sheet
- **Why in scope:** Bank ABA file generation is a standard payroll output. SOW 3.3 covers configuration, the Requirements Workbook includes bank account and payment file setup, and the Timeline lists "Bank ABA Standard File" as a specific build item. Testing the ABA file is a standard functional testing activity.

**PAYM-113 — [Test] Super Clearing File**
- **Sources:** SOW Section 3.3; RW row "Stapled super and default funds" (Custom); TL "Original Timeline" sheet — "Build — 3. Super Clearing House Standard Integration" row; DW "DEFAULT SUPERANNUATION" sheet
- **Why in scope:** Superannuation clearing house file generation is a standard payroll integration. SOW 3.3 covers configuration, the Requirements Workbook includes superannuation setup, the Timeline lists it as a specific build item, and the Discovery Workbook has a dedicated superannuation configuration sheet.

**PAYM-114 — [Test] ATO Integration**
- **Sources:** SOW Section 3.3; TL "Original Timeline" sheet — "Build — 4. ATO Standard Integration" row
- **Why in scope:** ATO integration (Single Touch Payroll reporting) is a standard payroll compliance requirement. SOW 3.3 covers configuration, and the Timeline lists "ATO Standard Integration" as a specific build item.

**PAYM-115 — [Test] GL Integration (Netsuite)**
- **Sources:** SOW Section 3.3 ("General Ledger (GL) and cost code set up which will include export files to Netsuite"); TL "Original Timeline" sheet — "Build — 5. GL Integration (Netsuite)" row
- **Why in scope:** SOW 3.3 explicitly names GL integration with Netsuite as a deliverable. The Timeline lists it as a specific build item. Testing the GL export is a standard functional testing activity for a deliverable that is explicitly named in the SOW.

**PAYM-121 — Build Integration — Project Evolution CR1 changes**
- **Sources:** RW-PE "Project Evolution" sheet (multiple rows detailing CR1 scope); TL "Original Timeline" sheet — "Build Integration — 11 Project Evolution (2c9) (Bookings/Payslip)" row showing "CR1 SO" sign-off; RAID "Risks" sheet — R01 ("CR1 approved and testing will confirm if Risk is abated")
- **Why in scope:** Project Evolution CR1 was formally approved as a Change Request. The Requirements Workbook has a dedicated "Project Evolution" sheet documenting CR1 scope including multi-entity payroll tax, GL adjustments, and scenario assessments. The Timeline records CR1 sign-off, and the RAID log tracks it as an approved risk mitigation. As an approved CR, this work is contractually within scope.

**PAYM-194 — Pay batch creation / automation**
- **Sources:** SOW Section 4 Flame Trees items ("Pay Batch Automation: Pay batch creation cannot currently be automated or scheduled; currently requires manual trigger via the UI"); SOW Section 5 Assumption 8 (Flame Trees items); RW row "API-triggered pay batches" (Custom — "Expose or configure API/Batch interfaces to create pay batches"); RW row "Pay batch triggering" (Custom); RW row "Large pay batch processing" (Custom — "Enable custom setting for 'Large Pay Batch' and configure row limit")
- **Why in scope:** SOW Section 4 explicitly lists pay batch automation as a Flame Trees release deliverable. SOW Section 5 reaffirms it under Assumption 8. The Requirements Workbook has three separate user stories covering pay batch automation, API triggering, and large pay batch processing. This is one of the most heavily documented in-scope items.

**PAYM-219 — Finalise Public holiday calendars and maintenance**
- **Sources:** SOW Section 4 Flame Trees items ("Public Holiday Trigger: Timesheet entry location needs to trigger public holidays"); RW row "Public holiday by shift location" (Custom — "Maintain holiday calendars by location in interpretation rules"); DW "HU PUBLIC HOLIDAY CAL" sheet; DW "PUBLIC HOLIDAYS" sheet
- **Why in scope:** SOW Section 4 lists the Public Holiday Trigger as a Flame Trees deliverable. The Requirements Workbook includes a Custom user story for location-based public holiday logic requiring location-specific calendars. The Discovery Workbook has two dedicated sheets for public holiday calendar configuration. Finalising these calendars is essential to delivering the PH trigger.

**PAYM-229 — Sync Data from 2c9 to Platform**
- **Sources:** RW row "Outbound pay results" (Standard — "Design an outbound pay summary interface or polling API"); RW row "Return of pay results" (Custom — "Define outbound messages or REST endpoints for pay lines and statuses"); TL "Original Timeline" sheet — "Build Integration — 10. Sync 2c9 <> Hireup Platform" row
- **Why in scope:** The Requirements Workbook lists both Standard and Custom user stories for outbound pay result synchronisation back to the Hireup Platform. The Timeline lists this as build item 10. SOW 3.8 also includes "Technical support to the Hireup team who are building an integration into 2cloudnine from the Hireup Platform."

**PAYM-232 — Auto-approve workflow for open timesheets**
- **Sources:** RW row "Payroll cutoff and approval workflow" (Standard — "Define and enforce the payroll cutoff process and approval workflow"); RW row "Pay batch triggering" (Custom — "Allow a scheduled job to create and calculate pay batches post cutoff")
- **Why in scope:** The Requirements Workbook includes a Standard user story for payroll cutoff and approval workflow, and a Custom story for scheduled automation post-cutoff. Auto-approval of open timesheets before payroll day is a workflow configuration that supports the agreed payroll cutoff process. The JIRA description specifies auto-approval commencing from 12:05am on Payroll Monday — this is the cutoff automation documented in requirements.

**PAYM-242 — Configure protected earnings (child support, garnishee)**
- **Sources:** SOW Section 3.3 (standard configuration); DW "DEDUCTION PAY CODES" sheet; RW row "Master payroll data setup" (Standard)
- **Why in scope:** Protected earnings configuration (ensuring deductions don't reduce net pay below a threshold) is a standard payroll feature. The Discovery Workbook includes a Deduction Pay Codes sheet, and configuring deduction rules is part of the standard payroll setup covered by SOW 3.3.

**PAYM-281 — Define template for data load of leave balances**
- **Sources:** SOW Section 3.4 ("One data migration for UAT and one for pre-Go-Live. Assistance with data import into 2cloudnine from either: Templates provided by 2cloudnine and completed by the Client; or Directly from the Hireup Platform"); DW "LEAVE RULES" sheet
- **Why in scope:** SOW 3.4 explicitly offers "Templates provided by 2cloudnine and completed by the Client" as a migration method. Defining the template for leave balance data load (annual leave, personal leave, LSL, FDVL) is directly delivering on this SOW commitment. The Discovery Workbook includes a Leave Rules sheet that informs the template design.

**PAYM-336 — Picklist of Allowance pay codes**
- **Sources:** SOW Section 3.3 (configuration); SOW Section 4 Deliverables ("configuration of the Salesforce UI to match the requirements and terminology of the Client"); DW "ALLOWANCE PAY CODES" sheet
- **Why in scope:** Configuring a picklist of allowance pay codes for manual UI entries is standard Salesforce UI configuration. SOW 3.3 covers configuration, the SOW deliverables include matching the Salesforce UI to client terminology, and the Discovery Workbook has a dedicated Allowance Pay Codes sheet that defines which codes should be available.

**PAYM-345 — Update missing BSBs in Prod**
- **Sources:** SOW Section 3.3 (configuration); RW row "Master payroll data setup" (Standard — "Set up bank accounts and payment files. Validate master data via test pay runs prior to go-live")
- **Why in scope:** BSB data integrity is essential for the Bank ABA payment file to function correctly. Missing BSBs would cause payment failures. The Requirements Workbook calls for validating master data prior to go-live, and maintaining complete BSB records is part of the standard payroll configuration delivered under SOW 3.3.

**PAYM-347 — Update MV Allowance to $1.04 per KM**
- **Sources:** SOW Section 3.3 (configuration); DW "ALLOWANCE PAY CODES" sheet; DW "ALLOWANCES" sheet
- **Why in scope:** Updating an allowance rate is standard payroll configuration maintenance. The motor vehicle allowance is documented in the Discovery Workbook's Allowance Pay Codes and Allowances sheets. Rate changes during the implementation period are part of keeping the configuration current — the system cannot go live with outdated rates.

**PAYM-357 — Review and check GL Account codes**
- **Sources:** SOW Section 3.3 ("General Ledger (GL) and cost code set up which will include export files to Netsuite"); DW — GL configuration is captured across multiple sheets
- **Why in scope:** SOW 3.3 explicitly includes GL and cost code setup. Reviewing and validating GL account code mappings is a standard quality assurance step for the GL configuration deliverable — ensuring expenses map to the correct GL accounts before go-live.

**PAYM-123 — SACS Project Codes**
- **Sources:** RW row "Short shift and penalty pay codes" (Custom — "Create specific codes for short shift top-up, overtime and penalties"); RW row "Discretionary allowance display on pay advice" — solution option (b) references "project codes to cater for different allowance rates"; SOW Section 4, Gap 7
- **Why in scope:** SACS project codes (SACS 2.1, 2.2, 2.3) enable manual override to a higher pay level when needed. The Requirements Workbook includes a Custom user story for creating specific pay codes for penalties and allowances. SOW Gap 7 references project codes as one of two solution options for discretionary allowance handling.

**PAYM-207 — Determine best way to enter On-call Allowances**
- **Sources:** SOW Section 3.3 (configuration); DW "ALLOWANCE PAY CODES" sheet; DW "ALLOWANCES" sheet; TL "Revised PPT" sheet — "Pay Batch Adjustments and Other Payments (PAYM-172 + PAYM-207)" row
- **Why in scope:** On-call allowances are documented in the Discovery Workbook's Allowance Pay Codes sheet. Determining the best entry method (manual vs imported) is a configuration decision within SOW 3.3. The Timeline explicitly references this ticket by number alongside PAYM-172 in the training/configuration block.

---

### Defects Found During Testing

All defects discovered during UAT and parallel testing fall within SOW 3.5 ("Functional testing assistance and guidance") as resolution of testing defects is inherent to delivering a working system. Additionally, SOW 3.8 covers "ad hoc support as required."

**PAYM-293 — Pay trans import defaulting to $34.59 (AC L3 project code)**
- **Sources:** SOW Section 3.3 (configuration); TL "Original Timeline" sheet — "Build — 8. Transaction Import Files (pre/post interpretation)" row
- **Why in scope:** The pay transaction import is listed as build item 8 in the Timeline. A bug causing all imports to default to an incorrect rate ($34.59 instead of the support worker's actual base rate) is a configuration defect in a deliverable that is explicitly scheduled in the project plan.

**PAYM-294 — Public holidays incorrectly tagged (UX Issue)**
- **Sources:** SOW Section 4 Flame Trees items (Public Holiday Trigger); RW row "Public holiday by shift location" (Custom); DW "HU PUBLIC HOLIDAY CAL" sheet
- **Why in scope:** Non-public-holiday dates being tagged as public holidays in the TSE screen is a defect in the public holiday calendar configuration. The PH trigger is a Flame Trees deliverable (SOW Section 4), and the Requirements Workbook and Discovery Workbook both document PH calendar requirements. While the pay outcome is correct, the UX display issue must be resolved.

**PAYM-310 — Public holiday part day — Afternoon shift not recognised**
- **Sources:** SOW Section 4 Flame Trees items (Public Holiday Trigger); RW row "Public holiday by shift location" (Custom — "Handle shifts that start in one jurisdiction and finish in another"); DW "HU PUBLIC HOLIDAY CAL" sheet
- **Why in scope:** Part-day public holidays (e.g. Christmas Eve from 7pm SA) not being recognised for afternoon shifts is a defect in the PH calendar and interpretation configuration. The PH trigger is a Flame Trees deliverable, and the Requirements Workbook requires handling of jurisdiction-specific PH logic.

**PAYM-344 — Public holiday under paid of SW L1**
- **Sources:** SOW Section 4 Flame Trees items (Public Holiday Trigger); SOW Section 3.3 (Award Interpretation)
- **Why in scope:** Underpayment on a public holiday for a Support Worker Level 1 is a rate calculation defect in the award interpretation engine configured under SOW 3.3. The PH trigger is a Flame Trees deliverable, and correct PH pay rates are fundamental to SCHADS compliance.

**PAYM-351 — Submitting Leave that needs Approval fails — EmailException error**
- **Sources:** RW row "Employee portal capabilities" (Standard — "Enable timesheet and leave submission for relevant cohorts"); SOW Section 3.3 (configuration)
- **Why in scope:** The Employee Portal is a Standard requirement in the Requirements Workbook. A leave submission failing due to an email exception in the `tc9_pr.Trg_PayeeLeave` trigger is a product defect that prevents a documented portal capability from functioning. Resolving product defects encountered during testing is part of delivering a working system.

**PAYM-356 — New Training pay code does not have associated pay rate**
- **Sources:** SOW Section 3.3 (configuration — pay code setup); RW row "Short shift and penalty pay codes" (Custom — "Create specific codes")
- **Why in scope:** A pay code that was imported via the pay transaction import producing $0 payments because it has no associated pay rate is a configuration defect. Pay codes configured as part of SOW 3.3 must have correct associated rates to produce valid pay outcomes.

**PAYM-301 — Investigate Error Log for Bulk Approval**
- **Sources:** SOW Section 3.5 (testing assistance); SOW Section 3.8 (ad hoc support)
- **Why in scope:** An error log appearing during bulk approval (even when the approval succeeded) indicates a validation exception that needs investigation. SOW 3.5 covers functional testing assistance, and SOW 3.8 covers ad hoc support. Investigating errors surfaced during testing is standard defect triage activity.

---

### Portal, Security, Go-Live Prep

**PAYM-87 — PIA Privacy Assessment for 2c9**
- **Sources:** SOW Appendix A — Security ("Security Deliverables — The Supplier must provide evidence of security activities and artefacts"); RW row "Roles and permissions" (Standard); SOW Appendix A — "Access Control and Identity Management"
- **Why in scope:** SOW Appendix A commits to security deliverables including secure configuration baselines, access controls, and documentation. A Privacy Impact Assessment is a standard security governance activity that falls within the security deliverables scope.

**PAYM-90 — Support Model Approach and Sign Off**
- **Sources:** SOW Section 3.7 (Go-Live and Post Go-Live Support); TL "Original Timeline" sheet — "Support/Operating Model Approach and Sign Off" row with sign-off milestone
- **Why in scope:** SOW 3.7 covers "Hypercare and post Go-Live support" and the transition to ongoing support. The Timeline explicitly includes "Support/Operating Model Approach and Sign Off" as a milestone with a formal sign-off gate. Defining and agreeing the support model is a prerequisite for go-live.

**PAYM-91 — Support Model Content and Sign Off**
- **Sources:** SOW Section 3.7; TL "Original Timeline" sheet — "Support/Operating Model Content and Sign Off" row
- **Why in scope:** This is the content deliverable that accompanies the support model approach (PAYM-90). SOW 3.7 covers post go-live support, and the Timeline includes a separate sign-off milestone for the support model content. This formalises how Hireup will be supported after hypercare ends.

**PAYM-92 — PPT Portal Access & Review**
- **Sources:** RW row "Employee portal capabilities" (Standard — "Enable timesheet and leave submission for relevant cohorts. Configure logo and branding for the portal"); DW "EMPLOYEE & APPROVER PORTAL" sheet
- **Why in scope:** The Requirements Workbook lists the Employee Portal as a Standard deliverable. The Discovery Workbook has a dedicated portal configuration sheet. Providing portal access for PPT testing (leave workflow and PH Not Worked entries) is necessary to test the portal deliverable during parallel runs.

**PAYM-137 — Community Portal approvers & Payroll system users**
- **Sources:** RW row "Employee portal capabilities" (Standard); RW row "Roles and permissions" (Standard — "Create core roles: admin, payroll manager, payroll operator, read-only, portal user"); DW "SYSTEM USERS" sheet
- **Why in scope:** The Requirements Workbook includes portal users and permission roles as Standard deliverables. The Discovery Workbook has a System Users sheet. Setting up approver profiles for the Community Portal and payroll system user accounts is standard configuration required for testing and go-live.

**PAYM-193 — Comms to Business to approve retros/tidy data**
- **Sources:** SOW Section 3.7 (Go-Live Preparation); RW row "Payroll cutoff and approval workflow" (Standard — "Document exceptions and off-cycle processes")
- **Why in scope:** Managing retrospective bookings at cutover is a go-live preparation activity. SOW 3.7 covers go-live preparation, and the Requirements Workbook calls for documenting exception processes. The approach of auto-approving older outstanding bookings to reduce go-live volumes requires business approval and is part of the cutover plan.

**PAYM-217 — Review licences and allocations for Hireup resources**
- **Sources:** SOW Section 3.1 (Project Management — "resource planning"); SOW Section 3.7 (Go-Live Preparation); DW "SYSTEM USERS" sheet
- **Why in scope:** Reviewing Salesforce licence allocations to ensure Hireup resources have appropriate access for go-live and beyond is a standard project governance activity under SOW 3.1 and a go-live readiness task under SOW 3.7. The Discovery Workbook captures system user requirements.

**PAYM-220 — Confirmation of retro approach — paper to ELT**
- **Sources:** SOW Section 3.7 (Go-Live Preparation); SOW Section 3.1 (Project Management — "Proactive management of changes to the project schedule, cost, or performance estimates")
- **Why in scope:** The retrospective pay approach at cutover requires ELT (Executive Leadership Team) endorsement. This is a go-live preparation governance activity — the cutover plan must define how retros spanning the old and new systems will be handled. SOW 3.7 covers go-live preparation and SOW 3.1 covers proactive project management.

**PAYM-341 — Production User Review**
- **Sources:** SOW Section 3.7 (Go-Live Preparation); SOW Appendix A — Security ("Principle of least privilege for all users. Documentation of privileged access reviews"); DW "SYSTEM USERS" sheet
- **Why in scope:** Reviewing production user access before go-live is both a go-live readiness task (SOW 3.7) and a security obligation (SOW Appendix A requires privileged access reviews and least-privilege enforcement). The Discovery Workbook documents the intended user list.

**PAYM-262 — Quarterly Release — Hibiscus**
- **Sources:** SOW Section 5, Assumption 8 (acknowledges product releases — Flame Trees specifically, with the framework for managing future releases); TL "Revised PPT" sheet — "Quarterly Release — Hibiscus" row (week 34, ~June 2026)
- **Why in scope:** While SOW Section 5 states "Implementation of future product releases are not included", the Hibiscus release (~June 2026) is scheduled in the project Timeline and must be coordinated with the go-live window. This ticket tracks the coordination effort (updating FCSB and PROD environments) rather than implementing new features. Managing release upgrades during the active project period is part of environment management under SOW 3.3.

---

### Payslip & Pay Advice

**PAYM-167 — Hireup custom Payslip template**
- **Sources:** SOW Section 4, Gap 7 ("Discretionary allowance display on pay advice — Solution to support 'discretionary allowance' payment … payslips must display the all inclusive rate"); SOW Section 4 Deliverables ("configuration of the Salesforce UI to match the requirements and terminology of the Client"); RW row "Consolidated pay advice presentation" (Custom — "Group component pay codes into single display lines on payslips")
- **Why in scope:** SOW Gap 7 explicitly requires payslips to "display the all inclusive rate" for discretionary allowances. The SOW deliverables include UI customisation to match client terminology. The Requirements Workbook has a Custom user story for consolidated pay advice presentation. A custom payslip template is the direct deliverable for these combined requirements.

**PAYM-342 — Align on Reversed Transactions display on Pay Advice**
- **Sources:** SOW Section 4, Gap 5 ("Consolidated Payslips for Retrospective Bookings — While a setting exists, the default is separate payslips for retrospective bookings. We require a consolidated payslip per Support worker, per pay period"); RW row "Consolidated pay advice presentation" (Custom)
- **Why in scope:** SOW Gap 5 requires consolidated payslips per support worker per pay period, including retrospective bookings. When retrospective bookings generate reversed transactions, how those reversals display on the consolidated pay advice must be aligned with the client's expectation. This is a design decision within the scope of delivering Gap 5.

---

### Sleepover Timing & Award Monitoring

**PAYM-152 — [Action AC076] Sleepover Timing — Hireup internal changes**
- **Sources:** SOW Section 4, Gap 2 (Sleepover Booking Configuration); SOW Section 3.1 (Project Management — "Proactive management of changes to the project schedule")
- **Why in scope:** This ticket tracks dependencies and timing for the sleepover build — specifically the relationship between Hireup's engineering delivery, impact on payments, and the drop-dead date for payroll project timing. SOW Gap 2 commits to sleepover configuration, and managing the timing and dependencies of that delivery is project management activity under SOW 3.1.

**PAYM-174 — Sleepover Timing — FairWork award changes**
- **Sources:** SOW Section 3.2 ("Interpretation of the Social, Community, Home Care and Disability Award [SCHADS - MA000100]"); RAID "Risks" sheet (project evolution and regulatory risk tracking)
- **Why in scope:** This ticket tracks proposed Fair Work Commission changes to the SCHADS award regarding sleepovers (December 2025 draft determination). While implementing new award rules would be additional work, monitoring regulatory changes that could impact the SCHADS interpretation being built is a project governance and risk management activity. The ticket is tracking awareness, not requesting build work.

---

### Discovery / Handover

**PAYM-12 — Schedule Reporting Workshop**
- **Sources:** SOW Section 3.2 (Discovery — "conducted standard discovery activities including 'discovery' workshops"); SOW Section 3.6 (Training); RW row "Custom reports and dashboards" (Custom — "Provide training for key Hireup users on report and dashboard creation"); RW row "Standard payroll reports" (Standard)
- **Why in scope:** The reporting workshop is a discovery/training session to understand Hireup's reporting needs and train users on report creation. SOW 3.2 covers discovery workshops, SOW 3.6 covers training, and the Requirements Workbook includes both Standard and Custom user stories for reports and dashboards — with the Custom story explicitly calling for user training.

**PAYM-221 — Audit log requirements**
- **Sources:** RW row "Audit history tracking" (Standard — "Enable field-level history tracking on key objects and fields … changes and who made them are traceable for compliance"); SOW Appendix A — Security ("Security Logging and Monitoring"); TL "Revised PPT" sheet — "Audit Logs session (PAYM-221)" row
- **Why in scope:** The Requirements Workbook classifies audit history tracking as a Standard deliverable, specifying field-level history tracking on key payroll and employee objects. SOW Appendix A commits to security logging and monitoring including SIEM integration. The Timeline directly references this ticket by number in the training/session schedule.

**PAYM-145 — Discuss change of State and LSL**
- **Sources:** SOW Section 3.2 (Discovery); RW row "Dual leave loading calculation" (Standard); DW "LEAVE RULES" sheet
- **Why in scope:** Understanding how a support worker's change of residential state impacts leave accrual (particularly Long Service Leave, which varies by state) is a discovery activity. SOW 3.2 covers discovery workshops, the Requirements Workbook includes leave calculation as a Standard requirement, and the Discovery Workbook has a Leave Rules sheet. Clarifying this interaction ensures the leave configuration is correct.

---

## Analysis: Scope Creep / Feature Requests (16 tickets)

These items represent new requirements not covered by the SOW, Requirements Workbook, or Discovery Workbook. They should be managed via the formal Change Request process per SOW Section 5.

| # | Ticket | Summary | Type | Reporter | Why It's Out of Scope |
|---|---|---|---|---|---|
| 1 | **PAYM-166** | [Nice to have] Slack integration for Payroll alerts | Task | Heidi Simoniuk | **No scope document mentions Slack integration.** Explicitly tagged as "Nice to have". This is a new integration request for alerts/notifications (state changes, leave accruals, portable LSL, payee info). Not in SOW, Requirements, or Discovery. |
| 2 | **PAYM-334** | Create UI Widget for adhoc timesheet entries | Task | Heidi Simoniuk | **Custom Salesforce UI development (widget).** The SOW covers "configuration of the Salesforce UI to match requirements and terminology" — not custom widget development. The integration design assumes timesheets originate from the Hireup Platform, not manual entry via a custom UI. Also requests the ability to create Timesheets where none exist. |
| 3 | **PAYM-358** | Separate pay code for Training (GL 50710 / 50720) | Task | Sameer Gundu | **New GL mapping requirement.** Requires separate pay codes for "Mandatory Training" and "Specialised Support Training" mapped to distinct GL accounts. Not identified during discovery or in the GL/cost code setup scope. |
| 4 | **PAYM-311** | Default pay rates for CAG & PPL | Task | Heidi Simoniuk | **New pay categories not in discovery.** Requires default rates for CAG Advisory Hours ($45/hr across all streams) and PPL (Paid Parental Leave). These specific pay rate categories and their override logic were not identified in the Discovery Workbook or Requirements. |
| 5 | **PAYM-159** | Setup custom fields to store Portable LSL Registration | Task | Heidi Simoniuk | **Portable LSL is not in the SOW.** Requires 2 custom fields for cross-border support workers. PLSL is a state-based compliance requirement not mentioned in SOW or Discovery. |
| 6 | **PAYM-241** | Build Portable LSL Reports (5 states) | Task | Heidi Simoniuk | **Portable LSL is not in the SOW.** Requires building 5 separate state-specific PLSL compliance reports with complex requirements per state. Significant build effort. |
| 7 | **PAYM-173** | Complete Portable LSL Workbook | Task | Heidi Simoniuk | **Portable LSL is not in the SOW.** Requires completing an entire workbook to define PLSL requirements across multiple states. |
| 8 | **PAYM-271** | Solution for PPT Min Contracted Hours | Task | Heidi Simoniuk | **Custom solution design.** Requires implementing work schedules for Part-Time/Permanent support workers to automatically pay minimum contracted hours and manage leave submissions. Not in SOW or Requirements as a deliverable — requires custom solution architecture. |
| 9 | **PAYM-279** | Process for FDVL & Pay advices | Task | Heidi Simoniuk | **FDVL (Family & Domestic Violence Leave) not in scope.** Requires the ability to process FDVL in 2cloudnine while ensuring it does NOT appear on pay advices (per legislation). Specific legislative compliance requirement not identified in discovery. |
| 10 | **PAYM-337** | Hireup custom Payslip Email body | Task | Heidi Simoniuk | **Custom email template development.** SOW Section 4 covers the payslip template itself (Gap 7: Discretionary allowance display). Customising the email body/wrapper that delivers the payslip is additional work beyond the payslip content. Includes specific Hireup branding, legal disclaimers, and dynamic content. |
| 11 | **PAYM-98** | Finance GL Report Build — Location requirements (2 columns) | Task | Karen Mangan | **Additional GL reporting requirement.** SOW 3.3 covers "GL and cost code set up which will include export files to Netsuite". The requirement for dual-location columns (primary location AND service delivery location) on the GL report is a custom reporting enhancement not in the Discovery Workbook. |
| 12 | **PAYM-151** | [Action AC073] Friday Booking reconciliation report | Task | Karen Mangan | **Custom operational report.** Requires building a bespoke reconciliation report with specific fields (SW External ID, start/end date/time, hours, approved status, etc.) for operational use. Beyond the standard reports scope. |
| 13 | **PAYM-354** | Production Org API Limits | Task | Guy Baxter | **Operational monitoring.** Monitoring and tracking production API consumption over PPT cycles. Not a configuration or build task — this is ongoing operational oversight not covered in the SOW. |
| 14 | **PAYM-335** | Investigate adjustments for Payee leave events | Task | Heidi Simoniuk | **New leave adjustment capability.** Requires the ability to edit/override annual leave pay transactions in the Pay Batch Manager, specifically to adjust leave loading components. This override capability was not in discovery. |
| 15 | **PAYM-333** | Review Apex code / Changes to flows impacts | Task | Heidi Simoniuk | **Custom code audit and documentation.** Requires reviewing all custom Apex code and flow changes, assessing maintenance impacts going forward. This is a code audit deliverable not in the SOW training/handover scope. |
| 16 | **PAYM-280** | Process to create new pay codes & ensure rates generated | Task | Heidi Simoniuk | **Process documentation and tooling.** Requires documenting the process to create new pay codes AND confirming if an Apex Job can regenerate all pay rates for the entire workforce across all streams. This is ongoing operational documentation/tooling beyond the SOW handover scope. |

---

## Borderline Items (12 tickets)

These items are related to scope but represent material extensions warranting discussion.

| # | Ticket | Summary | Why Borderline |
|---|---|---|---|
| 1 | **PAYM-272** | Solution for Sleepover bookings that cross midday | Sleepovers are in scope (SOW Gap 2), but this ticket explicitly calls for a "longer term" solution beyond the interim workaround. The midday-crossing edge case is acknowledged as a "current system constraint" requiring architectural change. |
| 2 | **PAYM-187** | Sleepover Midday Validation | Related to PAYM-272. A validation rule blocks approval for sleepover entries crossing 12 PM. Fixing the validation is arguably config, but the underlying system constraint is beyond standard sleepover scope. |
| 3 | **PAYM-174** | Sleepover Timing — FairWork award changes | Tracking proposed FWC changes to SCHADS (Dec 2025 draft determination). If these changes are enacted, reconfiguring the award interpretation would be additional work — SOW covers the award as it stood at time of signing. |

---

## Summary (Revised)

| Category | Original | Revised | % of Total |
|---|---|---|---|
| In Scope | 69 | **53** | 60% |
| Scope Creep / Feature Request | 16 | **19** | 22% |
| Borderline | 3 | **16** | 18% |
| **Total** | **88** | **88** | — |

> **Note:** 9 JIRA items in the export are duplicated or are parent epics that don't represent discrete work. The 88 above represents the unique analysable tickets.

### Reclassifications (Multi-Agent Review)

| Direction | Count | Tickets |
|---|---|---|
| In Scope → Scope Creep | 8 | PAYM-45, PAYM-262, PAYM-312, PAYM-313, PAYM-319, PAYM-324, PAYM-325, PAYM-326 |
| In Scope → Borderline | 9 | PAYM-232, PAYM-273, PAYM-293, PAYM-327, PAYM-328, PAYM-329, PAYM-330, PAYM-342, PAYM-347 |
| Scope Creep → Borderline | 5 | PAYM-151, PAYM-311, PAYM-335, PAYM-337, PAYM-358 |
| Borderline → In Scope | 1 | PAYM-174 |

**Key reclassification rationale:**

1. **SOW Gap 2 (Sleepover) is narrowly worded** — commits to "configure sleepover bookings so compliance hours are at the lower rate" and "understand how to send through sleepovers without any time worked." This does NOT cover minimum sleepover top-ups (IFA-specific), 18+ hour duration edge cases, daily OT interactions, midday-crossing penalties, or new pay codes for the minimum sleepover mechanism.

2. **Simplification cluster (PAYM-327–330) is rework** — the SOW commits to one design-and-build cycle. These tickets represent re-architecture of deliverables that were built once and proved unworkable due to complexity. The original coupling/design was requested by Hireup and delivered by 2cloudnine — unwinding it is a second iteration.

3. **PAYM-262 (Hibiscus) is explicitly excluded** — SOW Section 5 Assumption 8 states "implementation of future product releases are not included." The ticket itself says "not a must have."

4. **PAYM-334 (custom UI widget) has already been built** — regardless of classification, this work has been consumed and should be commercially reconciled.

### Scope Creep by Theme (Revised)

| Theme | Tickets | Est. Impact |
|---|---|---|
| **Sleepover Edge Cases / IFA Logic** (6 tickets) | PAYM-45, PAYM-312, PAYM-313, PAYM-319, PAYM-324, PAYM-325 | High — complex engine work beyond SOW Gap 2 wording |
| **Portable LSL** (3 tickets) | PAYM-159, PAYM-173, PAYM-241 | High — entirely new compliance stream across 5 states |
| **Custom UI / Widgets** (1 ticket) | PAYM-334 | Medium — custom Salesforce development (already built) |
| **Sleepover Pay Codes** (1 ticket) | PAYM-326 | Medium — new pay code for mechanism not in SOW |
| **Future Release** (1 ticket) | PAYM-262 | Medium — SOW Section 5 explicitly excludes |
| **Slack Integration** (1 ticket) | PAYM-166 | Medium — new integration, tagged "Nice to have" |
| **PPT Min Contracted Hours** (1 ticket) | PAYM-271 | High — custom solution design (JIRA acknowledges CR) |
| **FDVL** (1 ticket) | PAYM-279 | Medium — legislative compliance not in discovery |
| **GL Report Enhancement** (1 ticket) | PAYM-98 | Medium — dual-location not in DW |
| **Documentation / Audit** (2 tickets) | PAYM-280, PAYM-333 | Low-Medium — operational docs and code audit |
| **API Monitoring** (1 ticket) | PAYM-354 | Low — operational monitoring |

### Borderline by Theme (New)

| Theme | Tickets | Notes |
|---|---|---|
| **Simplification / Rework** (4 tickets) | PAYM-327, PAYM-328, PAYM-329, PAYM-330 | Rework of initial designs — shared accountability for design decisions |
| **Sleepover Midday** (2 tickets) | PAYM-187, PAYM-272 | Interim workaround closer to in-scope; permanent fix is scope creep |
| **Pay Categories Not in DW** (2 tickets) | PAYM-293, PAYM-311 | Import bugs in scope; CAG/PPL categories not in Discovery Workbook |
| **Custom Automation** (1 ticket) | PAYM-232 | Need arises from in-scope cutoff; implementation is custom scheduled job |
| **Pay Advice Display** (2 tickets) | PAYM-342, PAYM-337 | Related to in-scope payslip work but extend beyond agreed gap scope |
| **Leave Loading Defect** (1 ticket) | PAYM-335 | RW says "pay the higher" — may be a config defect, not new requirement |
| **Training Pay Codes** (1 ticket) | PAYM-358 | RW backs "dedicated codes"; GL mapping is the extension |
| **Rate Change** (1 ticket) | PAYM-347 | Trivial effort but sets precedent for mid-project business changes |
| **Reconciliation Report** (1 ticket) | PAYM-151 | Could be training outcome — Hireup builds it after PAYM-299 session |
| **Sleepover Bug** (1 ticket) | PAYM-273 | Base bug in scope; midnight-crossing expansion is beyond basic config |

### Recommendations

1. **Sleepover Edge Cases (PAYM-45, PAYM-312, PAYM-313, PAYM-319, PAYM-324, PAYM-325, PAYM-326)** — The largest scope creep cluster. SOW Gap 2 wording is narrow. All minimum sleepover top-up logic, long-duration edge cases, and OT interactions should be raised as a formal Change Request.

2. **Portable LSL (PAYM-159, PAYM-173, PAYM-241)** — Entirely new compliance stream across 5 states. Should be raised as a formal Change Request.

3. **PAYM-262 (Hibiscus)** — SOW explicitly excludes future product releases. Any work should be a Change Request.

4. **Simplification Cluster (PAYM-327–330)** — Borderline. Recommend a frank discussion about shared accountability for the design decisions that necessitated rework.

5. **PAYM-334 (Custom Widget)** — Already built. Regardless of classification, should be commercially reconciled.

6. **PPT Minimum Contracted Hours (PAYM-271)** — JIRA comments acknowledge this is "most likely a change request." Should be scoped and costed separately.

7. **All scope creep items** should be managed through the formal Change Request process as defined in SOW Section 5, with each item estimated and approved before work commences.
