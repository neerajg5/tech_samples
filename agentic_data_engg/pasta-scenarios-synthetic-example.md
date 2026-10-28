# PASTA Threat Analysis — Synthetic Example

> **Illustrative sample only.** This document describes a fictional system and invented scoring examples. It is not a record of any real organisation, product, deployment, control, incident, regulatory assessment, or risk decision. Replace all assumptions with approved objectives and evidence from your own system.

**Owner:** Example security risk lead  
**Version:** 0.1  
**Review cadence:** On material changes to objectives, architecture, threats, or controls  
**Status:** Teaching example; not an assessed production model

## Scoring approach used in this example

This sample uses a simple likelihood (1–5) × impact (1–5) score. A fictional pre-control score of 15 or more triggers escalation to a designated risk owner. The scale and threshold below are for illustration only: agree definitions, escalation roles, and acceptance authority before applying any scoring method.

| Score | Example interpretation |
|---|---|
| 1–4 | Lower relative priority; document rationale and review triggers. |
| 5–9 | Moderate relative priority; identify treatment and owner. |
| 10–14 | High relative priority; set a due date and review with the risk owner. |
| 15–25 | Escalate under this sample's fictional rule; do not treat escalation as automatic risk acceptance. |

## Stage 1 — Business objectives

| Objective | Why it matters in this fictional example | Evidence to define |
|---|---|---|
| Return recommendations only for authorized cases. | Prevents an unapproved request from influencing an outcome. | Approved authorization policy and negative test cases. |
| Keep a traceable record of each decision. | Supports investigation, review, and correction. | Required audit fields, retention policy, and access rules. |
| Provide a reliable response within an agreed service window. | Supports predictable use by the intended operator. | Service-level target and measurement method. |

These objectives are fictional prompts, not regulatory requirements. Substitute objectives approved by the relevant business, legal, compliance, and risk owners.

## Stage 2 — Technical scope

| Component | Example responsibility | Trust boundary |
|---|---|---|
| User-facing coordinator | Validates a request and routes work. | User to application |
| Specialist recommendation service | Produces a constrained recommendation. | Coordinator to specialist |
| Tool gateway | Mediates access to approved tools. | Agent to tool |
| Retrieval store | Returns authorized reference material. | Application to stored data |
| Audit service | Records decision metadata and outcomes. | Application to audit storage |
| External model provider | Processes prompts when selected by deployment configuration. | Application to external provider |

Confirm what data crosses each boundary, which identity acts, and which components are actually in scope. This example makes no claim that any particular provider or control is safe or appropriate.

## Stage 3 — Application decomposition

```text
User request
    |
    v
Coordinator -----> Specialist service
    |                      |
    |                      +-----> Tool gateway -----> Approved tool
    |                      |
    |                      +-----> Retrieval store
    |
    +-----> Audit service

Optional boundary:
Specialist service -----> External model provider
```

Before using this diagram, replace it with a data-flow diagram of the target application. Mark trust boundaries, identities, sensitive data, and external services.

## Stage 4 — Threat scenarios and pre-control risk

| ID | Synthetic scenario | Related STRIDE prompt | Likelihood | Impact | Pre-control score |
|---|---|---|---:|---:|---:|
| DEMO-01 | A crafted request attempts to make a specialist return information from another case. | Information disclosure | 2 | 4 | 8 |
| DEMO-02 | A retry causes the same case action to be processed more than once. | Tampering / repudiation | 3 | 3 | 9 |
| DEMO-03 | A caller submits a tool request using an identity assigned to another service. | Spoofing / elevation of privilege | 3 | 5 | 15 |

The scores are made up to demonstrate the format. Define likelihood and impact anchors and have reviewers apply them consistently; a multiplication result is not a measured probability.

## Stage 5 — Vulnerability and evidence review

| Scenario | Evidence to inspect | Example question |
|---|---|---|
| DEMO-01 | Authorization tests, retrieval policy, response schema | Do negative tests show that one case cannot retrieve another case's data? |
| DEMO-02 | Retry behavior, idempotency handling, audit events | Does a repeated request create a duplicate action, and can the event be traced? |
| DEMO-03 | Identity policy, tool permissions, gateway tests | Does the receiving boundary reject a caller with the wrong role? |

Record findings from tests, code review, configuration inspection, and operational records separately. Do not infer a control's effectiveness from its description alone.

## Stage 6 — Controls and residual risk

| ID | Example treatment to evaluate | Likelihood after | Impact after | Example residual score | Required follow-up |
|---|---|---:|---:|---:|---|
| DEMO-01 | Enforce case-level authorization before retrieval and before response; test both paths. | 1 | 4 | 4 | Retain negative test evidence and review after access-policy changes. |
| DEMO-02 | Use an idempotency key and record a unique action ID; test repeated submissions. | 1 | 3 | 3 | Confirm retry behavior in the deployed workflow. |
| DEMO-03 | Authenticate service identity and enforce deny-by-default role permissions at the gateway. | 2 | 5 | 10 | Escalate to the risk owner under the fictional threshold until evidence supports reassessment. |

Residual scores are still estimates. Record the evidence and assumptions behind each change; do not lower a score merely because a control is planned.

## Stage 7 — Risk decision and review

| Decision field | Example entry |
|---|---|
| Risk owner | Role accountable for the risk, not just the implementation task |
| Decision | Treat, avoid, transfer, or accept through the organisation's approved process |
| Evidence | Test report, code reference, configuration record, or operational result |
| Approval | Named authority and date where the process requires it |
| Review trigger | Architecture, model, data, identity, or deployment change |
| Next review | YYYY-MM-DD |

## Adapting the sample

1. Confirm business objectives and boundaries with accountable domain owners.
2. Draw data flows and select scenarios relevant to those objectives.
3. Score inherent risk before controls and residual risk only after reviewing evidence.
4. Define escalation and approval rules before scoring; keep them beside the results.
5. Link each treatment to a code change, configuration, test, or operational owner.
6. Reassess when architecture or control evidence changes.

This template does not replace a formal risk method, legal review, or your organisation's risk-acceptance process.
