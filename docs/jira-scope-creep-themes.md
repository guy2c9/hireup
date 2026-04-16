# Hireup Scope Creep Themes

This groups the `19` JIRA tickets classified as `Scope Creep` from [jira-ticket-classification-xml.csv](/Users/guybaxter/Documents/Claude%20Code/hireup/docs/jira-ticket-classification-xml.csv).

## Change Request Themes

| Theme | Tickets | Why this is out of scope | Recommended Change Request wording |
|---|---|---|---|
| Sleepover engine extension | `PAYM-45`, `PAYM-312`, `PAYM-313`, `PAYM-319`, `PAYM-324`, `PAYM-325`, `PAYM-326` | The SOW only commits to sleepover booking configuration so compliance hours are paid at the lower rate and to handling sleepovers with no time worked. These tickets extend into minimum sleepover top-ups, 18+ hour logic, back-to-back scenarios, OT aggregation, midday penalty handling, and new pay codes. | `Design, build, test, and deploy an enhanced sleepover interpretation solution covering minimum sleepover top-up logic, long-duration sleepovers, back-to-back sleepovers, OT aggregation across booking types, midday penalty treatment, and supporting pay-code changes.` |
| Portable LSL compliance stream | `PAYM-159`, `PAYM-173`, `PAYM-241` | Portable LSL is not referenced in the SOW, Discovery Workbook, or Requirements Workbook. This is a new compliance workstream requiring custom fields, workbook definition, and state-specific reporting. | `Design and implement Portable Long Service Leave support for Hireup, including data model changes, requirement definition, and reporting outputs for the required state schemes.` |
| Future product release adoption | `PAYM-262` | SOW Section 5 explicitly excludes future product releases other than the Flame Trees items already named. Hibiscus is a later release. | `Plan, test, and coordinate adoption of the Hibiscus release in the Hireup environment, including impact assessment, configuration uplift, regression testing, and deployment support.` |
| Minimum contracted hours automation | `PAYM-271` | This is a new custom solution for work schedules and automatic top-up handling, and is not covered in the SOW or discovery artefacts. | `Design and implement a minimum contracted hours solution for part-time and permanent workers, including work schedule design, top-up calculation behaviour, leave interaction rules, testing, and deployment.` |
| Legislative pay advice / FDVL handling | `PAYM-279` | FDVL processing and the specific requirement to suppress it from pay advice are not in the scoped documents. | `Define, configure, and test a compliant FDVL process, including payroll treatment, pay advice presentation rules, security/privacy controls, and user guidance.` |
| GL reporting enhancement | `PAYM-98` | The SOW covers GL and Netsuite export setup, but not a custom dual-location reporting design. | `Design and deliver an enhanced GL export/report output that includes both primary location and service-delivery location fields, with testing and business sign-off.` |
| Slack / alerting integration | `PAYM-166` | No scope document mentions Slack or alerting integrations. The ticket is explicitly tagged `Nice to have`. | `Design and implement a Slack-based payroll alerting integration for agreed event triggers, message routing, operational ownership, and support procedures.` |
| Operational tooling, documentation, and monitoring | `PAYM-280`, `PAYM-333`, `PAYM-354` | These tickets are BAU enablement items: process/tooling for future pay-code generation, code/flow audit, and production API monitoring. They are outside the implementation deliverables. | `Provide post-implementation operational enablement services covering BAU payroll administration tooling, technical audit/documentation of custom code and flows, and production API monitoring/reporting.` |
| Custom UI for ad hoc timesheet entry | `PAYM-334` | The SOW allows configuration of Salesforce UI, not bespoke widget development. The integration model assumes timesheet creation from the Hireup Platform. | `Design, build, test, and deploy a custom Salesforce UI component to support ad hoc timesheet entry and creation workflows for payroll users.` |

## Source anchors

| Source | Relevance |
|---|---|
| `Hireup SOW - Final - August 25.docx` Section `4` | Defines the narrow sleepover gap wording and other named deliverables |
| `Hireup SOW - Final - August 25.docx` Section `5` | States that future product releases are excluded and changes after discovery require a Change Request |
| `HireUp - Payroll Discovery Workbook FINAL 20260115.xlsx` | Confirms that items not captured in discovery/scoping are to be treated as change work |
| `HireUp - Requirements workbook (User Stories).xlsx` | Used to verify whether a requirement was identified as `Standard`, `Custom`, `Gap Fit`, or not identified at all |
| `Hireup - RAID.xlsx` | Confirms some items are already recognised as CR-style workstreams |

## Notes

- `PAYM-334` appears to have already been built according to the JIRA commentary. Even if treated as scope creep, it should be commercially reconciled as consumed work rather than treated as future optional scope.
- `PAYM-166` is the clearest pure feature request because the ticket itself says `Nice to have`.
- The sleepover cluster is the largest commercial issue because it is a family of related tickets that likely should be handled as one packaged Change Request rather than seven separate commercial discussions.
