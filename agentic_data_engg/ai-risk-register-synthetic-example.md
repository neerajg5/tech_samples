# AI Risk Register — Synthetic Example

> **Illustrative sample only.** All organisation names, scenarios, scores, controls, thresholds, roles, and review dates are fictional. This document is not an assessment of a real AI management system and does not establish compliance with any standard or law.

**Organisation:** Example organisation  
**Owner:** AI risk lead  
**Version:** 0.1  
**Review cadence:** Quarterly and after material changes  
**Classification:** Public teaching example; do not enter confidential information

## Purpose and use

This register complements technical threat analysis by recording broader AI risks, accountable owners, evidence, decisions, and review triggers. Tailor the categories and approval process to the organisation. A register entry documents a risk claim; it does not demonstrate that a control operates.

### Example scoring

| Factor | Example scale |
|---|---|
| Likelihood | 1 (rare) to 5 (frequent), using locally approved definitions |
| Impact | 1 (limited) to 5 (severe), using locally approved definitions |
| Inherent score | Likelihood × impact before considering controls |
| Residual score | Reassessed after reviewing control evidence and remaining exposure |
| Escalation | Example only: residual score of 15 or higher goes to the designated risk authority |

The scale and threshold are illustrative. Establish a consistent rubric and governance approval before use.

## Risk register

### Model performance

#### DEMO-AI-01 — Model behavior changes as input data shifts

| Attribute | Synthetic example |
|---|---|
| Risk | A change in incoming data causes recommendations to become less reliable for a defined use case. |
| Objective affected | Provide recommendations that meet approved performance criteria. |
| Likelihood | 3 — illustrative estimate only |
| Impact | 4 — illustrative estimate only |
| Inherent score | 12 |
| Example control | Monitor defined input and outcome indicators against an approved reference; require review when a threshold is crossed. |
| Evidence to collect | Monitoring specification, reference-data approval, alert test, review record, and decision on whether to pause or roll back. |
| Residual score | 8 — fictional estimate pending evidence |
| Owner | Model owner |
| Review trigger | Material change in data, model version, intended use, or monitoring threshold. |
| Decision status | Open in this synthetic example; no acceptance implied. |

### Fairness and user impact

#### DEMO-AI-02 — Outcome differences across relevant user groups go unnoticed

| Attribute | Synthetic example |
|---|---|
| Risk | Aggregate performance appears acceptable while a relevant subgroup experiences materially different outcomes. |
| Objective affected | Deliver outcomes consistent with approved fairness and user-protection requirements. |
| Likelihood | 3 — illustrative estimate only |
| Impact | 5 — illustrative estimate only |
| Inherent score | 15 |
| Example control | Define group comparisons, minimum sample sizes, review criteria, and escalation owners before deployment. |
| Evidence to collect | Approved metric definitions, data-quality checks, subgroup results, limitations, and a documented human review. |
| Residual score | 10 — fictional estimate pending evidence |
| Owner | Responsible domain and model-risk owners |
| Review trigger | New population, outcome definition, data source, or material metric change. |
| Decision status | Escalate for review under the fictional example threshold. |

### Operations and oversight

#### DEMO-AI-03 — An operator relies on generated text that conflicts with a deterministic result

| Attribute | Synthetic example |
|---|---|
| Risk | A generated explanation appears to approve an action that a separate policy check rejected. |
| Objective affected | Ensure people receive clear and consistent decision information. |
| Likelihood | 2 — illustrative estimate only |
| Impact | 4 — illustrative estimate only |
| Inherent score | 8 |
| Example control | Keep the policy result authoritative, test contradictory outputs, and route conflicts to a human review path. |
| Evidence to collect | Negative test cases, UI behavior, audit record, and reviewer disposition. |
| Residual score | 4 — fictional estimate pending evidence |
| Owner | Application owner |
| Review trigger | Prompt, model, policy, user-interface, or escalation-flow change. |
| Decision status | Open pending a test of the integrated workflow. |

## Decision and review log

| Date | Risk ID | Decision or change | Evidence reference | Approver | Next review |
|---|---|---|---|---|---|
| YYYY-MM-DD | DEMO-AI-00 | Record treatment, acceptance, or further analysis | Link an approved evidence location | Role/name | YYYY-MM-DD |

## Applying this register in a real programme

1. Align each entry to an approved objective, intended use, and accountable owner.
2. Link technical scenarios to the relevant STRIDE, PASTA, and AI-technique analyses rather than duplicating them.
3. Record inherent risk, controls, evidence, residual risk, and escalation decisions separately.
4. Treat planned controls as open actions until implementation and evidence are reviewed.
5. Set review triggers that follow model, data, user, architecture, and operating changes.

Do not copy these scores, controls, or role assignments into a live register without domain review and approval.
