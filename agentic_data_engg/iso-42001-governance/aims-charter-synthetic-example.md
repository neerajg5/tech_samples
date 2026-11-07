# AI Management System Charter — Synthetic Example

> **Fictional teaching sample.** The organisation, system, roles, measures, and
> workflows below are invented. This is not a real charter, legal advice, or
> evidence of compliance. Adapt it with qualified owners before use.

- **Organisation:** Example Organisation
- **Charter owner:** AI Governance Lead
- **Executive sponsor:** Example Executive Committee
- **Review:** At least annually and after a material change

## 1. Purpose and authority

This charter describes how Example Organisation coordinates the people,
processes, and controls used to govern its AI systems. It connects the AI
policy to system-level risk decisions, approval, monitoring, and improvement.
It does not replace the authority of business, legal, risk, privacy, security,
or domain owners.

## 2. Example system boundary

This sample covers an **Eligibility Support Assistant**, a fictional service
that summarizes approved case information and recommends cases for employee
review.

### Included in this example

- Request intake and identity checks.
- Data preparation and approved reference sources.
- The model and orchestration workflow.
- The employee review interface and decision-record service.
- Monitoring, incident handling, and system-change processes.

### Excluded from this example

- Final eligibility decisions, which remain with an authorized employee.
- Unrelated business applications.
- External services outside the organisation's control, except for their
  procurement and supplier-risk assessment.

The owner must revisit these boundaries when data flows, users, models,
connected services, or intended uses change.

## 3. Governance roles

| Role | Charter responsibility |
|---|---|
| Executive sponsor | Provides direction and resolves escalated resource or risk decisions. |
| Business owner | Owns intended use, affected-user needs, and the business decision to operate the service. |
| System owner | Coordinates design, operation, monitoring, changes, and evidence. |
| AI risk owner | Challenges risk assessments and tracks treatment decisions. |
| Independent reviewer | Reviews validation or assurance evidence without approving their own work. |

The organisation appoints people to these roles separately and records
delegations and approval limits in its controlled responsibility record.

## 4. Governance process

| Stage | Minimum activity | Example record |
|---|---|---|
| Intake | Describe purpose, users, affected people, and system boundary. | System proposal |
| Risk assessment | Identify harms, obligations, controls, owners, and review triggers. | Risk assessment and treatment log |
| Validation | Test expected behavior, failure paths, data limitations, and human workflow. | Test plan and results |
| Approval | Review evidence and decide whether release conditions are met. | Approval record with conditions |
| Operation | Review service behavior, incidents, user concerns, and changes. | Monitoring and incident records |
| Improvement | Assign corrective actions, verify closure, and revise governance records. | Action log and review minutes |

Teams keep traceable links between a risk, its control, the evidence used to
review it, and the resulting decision. A planned control remains an open
action until its operation is verified.

## 5. Objectives and measures

The following are example objective prompts, not prescribed thresholds:

| Objective | Example measure | Owner |
|---|---|---|
| Keep outputs within the approved purpose. | Results of tests for in-scope and out-of-scope requests. | System owner |
| Provide meaningful human review. | Review records contain the case reference, reviewer role, decision, and rationale. | Business owner |
| Identify material performance changes. | Monitoring reviews completed against an approved schedule and response rule. | Model owner |
| Resolve reported concerns. | Each report has a triage decision, owner, and recorded disposition. | Service owner |

Before use, define each measure's numerator, denominator, data source, time
period, operating environment, decision threshold, and response. A target is
not evidence that the target has been met.

## 6. Escalation and change

The system owner routes material incidents, failed controls, and changes to
the designated risk owner. The risk owner determines whether to pause use,
request further evidence, or escalate under approved authority. The decision,
rationale, owner, and next review trigger are recorded.

Material changes to data, model, workflow, user population, supplier, or
intended use receive an impact review before release. Emergency changes follow
the organisation's approved incident and change procedures.

## 7. Management review

The executive sponsor schedules a review at an organisation-approved
frequency. Inputs may include risk changes, validation results, monitoring,
incidents, user concerns, supplier changes, unresolved actions, and resource
needs. The review records decisions, action owners, due conditions, and
follow-up evidence.

## 8. Adoption checklist

1. Confirm the system inventory, intended use, users, interfaces, and
   exclusions.
2. Assign accountable roles and approval limits.
3. Approve lifecycle processes, objectives, evidence sources, and escalation
   rules.
4. Record management approval and review the charter after material changes.
