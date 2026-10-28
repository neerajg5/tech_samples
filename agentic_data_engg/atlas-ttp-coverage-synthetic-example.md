# AI Technique Coverage Matrix — Synthetic Example

> **Illustrative sample only.** The system, control descriptions, status, and review notes below are fictional. Technique labels are broad topics, not verified MITRE ATLAS identifiers. Select and verify current technique names and IDs from the official framework for your assessment.

**System:** Example multi-agent application  
**Owner:** Example security engineering team  
**Version:** 0.1  
**Review cadence:** On framework, architecture, model, or control changes  
**Status:** Teaching example; not evidence of actual coverage

## Coverage method

For each relevant AI-specific technique, record the affected component, the expected behavior, the implemented control, and evidence from a test or review. Mark planned, partial, and verified work distinctly. A matrix row is a tracking aid; it does not prove that a control is deployed or effective.

### Example status labels

| Status | Meaning in this fictional sample |
|---|---|
| Proposed | Applicability or treatment still needs review. |
| Partial | Some control work exists, but the stated scenario is not fully tested. |
| Tested | A named test produced a recorded result for the stated scope and version. |
| Gap | No adequate treatment or evidence is currently identified. |

## Technique-to-control coverage

| AI technique topic | Component / boundary | Expected behavior | Example control to evaluate | Evidence to link | Sample status | Gap / next action | Owner |
|---|---|---|---|---|---|---|---|
| Prompt injection | User input to coordinator and specialist agent | Untrusted instructions do not override the task policy or authorization boundary. | Validate input handling, constrain tool permissions, and test direct and indirect injection cases. | Versioned probe set, result, code/config reference, and reviewer. | Partial | Add coverage for retrieved content and multi-step agent handoffs. | Agent application owner |
| Sensitive-data extraction | Agent response to user or downstream service | The system returns only fields authorized for the requesting context. | Apply output authorization and test known synthetic sensitive-data patterns. | Negative tests, response schema, and access-control decision log. | Proposed | Define what counts as sensitive for the use case. | Data protection owner |
| Data poisoning | Ingestion pipeline to retrieval or model input | Untrusted or altered source data is detected or withheld from use. | Validate source, schema, provenance, and bounded anomaly indicators before promotion. | Ingestion tests, source record, quarantine decision, and approval. | Gap | Define data lineage and safe recovery procedure. | Data platform owner |
| Unsafe tool use | Agent to tool gateway | An agent can call only tools allowed for its role and task. | Enforce server-side allowlists and deny unapproved calls; test each role/tool combination. | Authorization test matrix and policy version. | Partial | Test prompt-driven tool substitution and denied-call handling. | Tool platform owner |
| Model or configuration change | Model registry to deployed service | Only reviewed model/configuration versions are promoted, with traceable rollback. | Require versioned approval, integrity checks, and deployment review. | Change request, artifact identity, deployment event, and rollback exercise. | Proposed | Define approval authority and artifact provenance. | Model operations owner |
| Agent memory manipulation | Agent state store | Untrusted state changes cannot silently alter future actions. | Define trusted writers, validate state schema and integrity, and test tampering and recovery. | State-store tests, access policy, and recovery evidence. | Gap | Determine whether persistent agent memory exists in scope. | Agent platform owner |

## Evidence record

| Field | Example |
|---|---|
| Technique/topic and verified framework ID | Confirm from the official framework release used for the review |
| System/model version | Record an immutable version or release reference |
| Test date and environment | State the scope and relevant deployment configuration |
| Test input and expected result | Use approved, non-sensitive test data |
| Actual result | Record pass, fail, inconclusive, or not run; retain details in an approved evidence store |
| Owner and follow-up | Name the accountable role and due date |
| Review approval | Record who reviewed the evidence and any remaining risk decision |

## Using the matrix responsibly

1. Select techniques that apply to the actual model, agent, tools, data, and deployment.
2. Verify technique names and identifiers against the current official MITRE ATLAS knowledge base.
3. Translate each selected technique into a safe, scoped test with an expected result.
4. Link each row to implementation and test evidence; do not treat a tool name or policy file as proof.
5. Track gaps with owners, due dates, and approval requirements; update coverage after a retest.

This example is not an ATLAS mapping or certification. Confirm applicability, identifiers, and test safety with the responsible security reviewers.
