# STRIDE Threat Register — Synthetic Example

> **Illustrative sample only.** This document uses a fictional service and scenarios. It is not a record of any real organisation, product, deployment, control, incident, or risk decision. Replace every example with evidence from your own system before using this register.

**Owner:** Example application security lead  
**Version:** 0.1  
**Review cadence:** On architecture, data-flow, or trust-boundary changes  
**Status:** Teaching example; not an assessed production register

## How to use this register

Use STRIDE to prompt a review of each component and trust boundary. For every threat, record the scenario, potential impact, control or test, remaining risk, evidence, owner, and next review. A listed control is a claim to verify, not evidence that it is deployed or effective.

### Example residual-risk scale

| Rating | Example interpretation |
|---|---|
| Low | A control has evidence for the stated scenario; residual exposure remains subject to review. |
| Medium | A gap remains, or the main safeguard detects rather than prevents the scenario. |
| High | A material gap has no verified treatment; assign an owner and escalation path. |

Define and approve the scale for your organisation. The example ratings below are invented for demonstration.

## Attack Surface 1 — Service-to-Service Requests

_A coordinator sends work to specialist services across an internal API boundary._

| STRIDE | Synthetic threat scenario | Example control or test | Example residual | Follow-up evidence |
|---|---|---|---|---|
| Spoofing | A caller uses a copied service credential to submit an unauthorized request. | Verify caller identity at the API boundary; test missing, expired, and wrong-role credentials. | Medium — rotation and alert coverage need review. | Negative test results, policy version, and alert record. |
| Tampering | A request field is changed after review but before processing. | Bind approval to a versioned request; reject a request whose version changes. | Low — example assumption only. | Integration-test result and versioned audit event. |
| Repudiation | A service operator disputes whether a request was dispatched. | Record the request identifier, caller, timestamp, and outcome in an access-controlled audit trail. | Medium — retention and access review remain. | Sample audit event and retention configuration. |
| Information disclosure | A response includes fields the requesting role should not see. | Apply response-field authorization; test with distinct synthetic roles. | Medium — nested fields need coverage. | Role-based response tests and review record. |
| Denial of service | Repeated requests exhaust a specialist service's worker capacity. | Apply per-caller limits and bounded queues; test overload and recovery behavior. | Medium — capacity limits need service-owner approval. | Load-test summary, limit configuration, and recovery observation. |
| Elevation of privilege | A caller requests an action outside its assigned capability. | Enforce deny-by-default permissions at the receiving service; test each role/action pair. | Low — example assumption only. | Authorization matrix and negative test results. |

## Attack Surface 2 — Tool Gateway

_Agents request a tool through a gateway that checks identity, arguments, and permissions._

| STRIDE | Synthetic threat scenario | Example control or test | Example residual | Follow-up evidence |
|---|---|---|---|---|
| Spoofing | An unregistered agent invokes a tool endpoint. | Authenticate the agent and bind its identity to an allowlist; test unknown identities. | Medium — enrollment process needs review. | Authentication tests and allowlist change history. |
| Tampering | An agent changes a tool argument to select another customer's record. | Validate argument ownership at the tool boundary; test cross-account identifiers. | Medium — downstream authorization must also be checked. | Boundary-test results and sanitized audit event. |
| Repudiation | A caller denies having invoked a sensitive tool. | Log tool name, request ID, caller, decision, and outcome; exclude secrets and unnecessary personal data. | Low — sample logging design only. | Redacted log sample and access policy. |
| Information disclosure | Tool output returns data beyond the requesting task's need. | Minimize output fields and enforce access checks before retrieval. | Medium — output schemas need review. | Schema tests and data-access review. |
| Denial of service | Repeated expensive tool calls exhaust shared capacity. | Set per-tool quotas and request timeouts; test throttling and graceful failure. | Medium — quota values are deployment-specific. | Limit configuration and throttling test. |
| Elevation of privilege | An agent calls a tool intended for a different role. | Enforce tool permissions server-side for every invocation. | Low — sample assumption only. | Role-to-tool test matrix. |

## Attack Surface 3 — Retrieval and Data Stores

_An agent retrieves indexed documents and structured records through a data-access layer._

| STRIDE | Synthetic threat scenario | Example control or test | Example residual | Follow-up evidence |
|---|---|---|---|---|
| Spoofing | An untrusted service submits writes as the indexing service. | Authenticate writers and separate read/write roles. | Medium — key-management review remains. | Writer identity tests and role configuration. |
| Tampering | A document is changed without updating its review status. | Store version, source, and integrity metadata; alert on unexpected replacement. | Medium — source validation is separate work. | Integrity test and change audit. |
| Repudiation | A data update cannot be linked to its source or actor. | Record source ID, version, actor, and timestamp for each change. | Medium — provenance completeness needs sampling. | Sample lineage record. |
| Information disclosure | Retrieval crosses a tenant or access-group boundary. | Enforce authorization before retrieval and test cross-group queries. | High until negative tests pass. | Cross-group test results and access-policy review. |
| Denial of service | Broad retrieval requests return excessive data or consume capacity. | Bound result count and query duration; test worst-case filters. | Low — workload assumptions need confirmation. | Query-limit configuration and test result. |
| Elevation of privilege | A low-privilege agent selects a restricted collection. | Map collections to service roles and reject unauthorized collection names. | Medium — enforcement must be tested at the data boundary. | Role/collection test matrix. |

## Review record

| Review date | Change reviewed | Evidence checked | Open items | Reviewer |
|---|---|---|---|---|
| YYYY-MM-DD | Describe architecture or data-flow change | Link test, code review, or configuration evidence | Record owner and due date | Name or role |

## Adapting the sample

1. Draw the current components, data flows, and trust boundaries.
2. Review each boundary using the six STRIDE prompts; add only scenarios that fit your system.
3. Link each proposed control to its implementation and a test or other evidence.
4. Assign a role, due date, and escalation path to every unresolved item.
5. Revisit the register when components, identities, data, or deployment boundaries change.

Do not copy the sample ratings or controls as approved decisions. Validate the actual system and follow your organisation's risk-acceptance process.
