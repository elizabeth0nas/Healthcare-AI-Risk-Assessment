# ClinScribe AI Guardrail and Control Effectiveness Assessment

## 1. Purpose

This assessment evaluates whether the proposed AI safeguards are appropriately designed, implemented, tested, and monitored.

The assessment distinguishes between documented controls and controls supported by evidence of operating effectiveness.

**Assessment status:** Preliminary  
**System:** ClinScribe AI  
**Methodology:** NIST AI Risk Management Framework  
**Evidence reviewed:** E-01 through E-08

## 2. Control Effectiveness Criteria

| Assessment stage | Evaluation question |
|---|---|
| Designed | Is the safeguard appropriately defined to address the risk? |
| Implemented | Is the safeguard configured and operating within the system? |
| Tested | Has its functionality and effectiveness been demonstrated? |
| Monitored | Is control performance reviewed and are exceptions investigated? |
| Effective | Is there sufficient evidence that the safeguard operates as intended? |

A control must not be considered effective solely because it appears in a policy, vendor questionnaire, or product description.

## 3. AI Guardrail Assessment

| Guardrail | Evidence | Preliminary assessment | Outstanding requirement |
|---|---|---|---|
| Human oversight | E-07, E-08 | Not demonstrated | Verify mandatory clinical approval and test bypass scenarios. |
| Output accuracy | E-04, E-08 | Not demonstrated | Obtain clinical validation and investigate reported errors. |
| Data protection | E-01, E-02, E-03 | Unverified | Confirm retention, secondary use, encryption, and subprocessors. |
| Access restrictions | E-05 | Incomplete | Verify account ownership, permissions, and access reviews. |
| Prompt-injection resistance | E-03, E-08 | Not demonstrated | Obtain adversarial testing and assess connected-tool permissions. |
| Bias and performance | E-04 | Insufficient evidence | Obtain representative performance and subgroup evaluation results. |
| Logging and monitoring | E-06, E-08 | Incomplete | Verify AI activity logging, integrity, retention, and review procedures. |
| Accountability | E-02, E-03, E-06, E-07 | Incomplete | Establish documented ownership and escalation responsibilities. |

## 4. Detailed Assessment R-01 Human Oversight

**Risk:** AI omits or changes clinically significant details in a summary.
**Related evidence:** E-04, E-07, E-08.

### Control objective

Prevent inaccurate, incomplete, or potentially unsafe AI-generated clinical summaries from being finalized in the official clinical record without appropriate review and approval by authorized clinical personnel.

### Required safeguards

- Mandatory approval by an appropriately authorized clinician.
- Ability to correct, reject, or escalate an AI-generated summary.
- Restrictions on unauthorized approval overrides.
- Attributable records of review, correction, rejection, and approval.
- Monitoring and investigation of override activity.
- Testing of normal and exception workflows.

### Assessment findings

The vendor describes human-in-the-loop review. However, the available evidence does not establish whether approval is technically enforced or whether an unreviewed summary can enter the clinical record.
A further hypothetical control-testing scenario raises an additional concern: an administrator may be able to disable mandatory approval, and the override action may not be logged.
This scenario is a proposed test condition, not a confirmed production finding.

### Evidence required

1. Workflow demonstration showing the approval process.
2. Configuration evidence confirming mandatory approval.
3. Role and permission matrix identifying authorized approvers and administrators.
4. Negative testing demonstrating that an unapproved summary cannot be finalized.
5. Override testing, including unauthorized and emergency override scenarios.
6. Audit records showing who performed each action and when.
7. Evidence of periodic review and escalation of override activity.

### Preliminary control conclusion

**Status: Not yet demonstrated effective.**

The normal approval workflow may be appropriately designed, but bypass functionality, auditability, and monitoring remain unverified.

A vendor attestation may support the assessment, but should be corroborated with test results, configuration evidence, and independently reviewable records.

### Recommended remediation

- Require clinical approval before finalization.
- Restrict override permissions to explicitly authorized personnel.
- Log all approval changes and override activity.
- Implement periodic review of exceptions.
- Require documented risk-owner approval for exceptional overrides.
- Test bypass prevention and audit logging before production approval.

**Residual risk:** Not assigned pending remediation and effectiveness testing.

## 5. Control Testing Plan

| Test ID | Test objective | Expected result | Evidence of successful testing |
|---|---|---|---|
| T-01 | Attempt to finalize a summary without clinical approval | System blocks finalization | Test results and configuration evidence |
| T-02 | Attempt an unauthorized approval override | Unauthorized action is blocked | Access-control test results |
| T-03 | Perform an authorized override | Action is restricted and recorded | Attributable audit record |
| T-04 | Submit a summary containing deliberately misleading clinical text | System safeguards and review workflow handle the scenario appropriately | Adversarial test results and clinical review |
| T-05 | Review a generated summary containing an omitted medication change | Clinician can identify, correct, and reject the output | Clinical validation records |
| T-06 | Reconstruct a simulated AI-related incident | Relevant events can be traced | Audit-log sample and incident reconstruction |

Testing must be conducted in an authorized test environment using synthetic data.

## 6. Governance and Accountability

| Role | Responsibility |
|---|---|
| AI product owner | Owns product configuration and technical safeguards. |
| Clinical safety lead | Defines clinical approval and safety requirements. |
| Information security lead | Reviews security controls, access, and logging. |
| Privacy lead | Reviews patient data processing and privacy safeguards. |
| AI governance lead | Coordinates AI risk assessment and governance reporting. |
| Risk owner | Reviews findings and approves risk treatment or formal risk acceptance. |
| Vendor | Supplies technical documentation and supporting test evidence. |

## 7. Overall Assessment Conclusion

The available evidence does not yet demonstrate that all proposed AI guardrails are implemented and operating effectively.

The most significant outstanding concerns relate to clinical oversight, output reliability, data handling, access management, and AI activity traceability.

Critical safeguards should be validated before unrestricted production deployment.

No control effectiveness or residual risk reduction is assumed without supporting evidence.

---

*This assessment is hypothetical and does not constitute a real system audit, clinical validation, legal opinion, or certification determination.*
