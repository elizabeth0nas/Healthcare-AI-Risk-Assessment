# ClinScribe AI Evidence Pack

## 1. Purpose

This evidence pack supports the initial AI risk assessment of a hypothetical AI-powered clinical note summarization system.

It contains simulated vendor documentation, internal stakeholder statements, technical observations, and incident records.

The purpose is to assess evidence reliability, identify inconsistencies, evaluate AI safeguards, and determine whether the proposed controls adequately address identified risks.

**Assessment status:** Initial assessment  
**Evidence status:** Simulated; not independently verified  
**Assessment methodology:** NIST AI Risk Management Framework  
**System:** ClinScribe AI  
**Assessment boundary:** Clinical note summarization and supporting workflows.

> _All records, names, dates, and events are fictional. No actual patient information or production system data is used._

---

## 2. Evidence Inventory

| Evidence ID | Source | Description | Related risks |
|---|---|---|---|
| E-01 | Vendor questionnaire | Model training and customer data use | R-02 |
| E-02 | Contract extract | Data retention and service improvement | R-02, R-08 |
| E-03 | IT architecture notes | EHR integration and third-party model provider | R-02, R-04, R-08 |
| E-04 | Clinician feedback | Reported omissions in generated summaries | R-01, R-05 |
| E-05 | Access review extract | Shared clinical support account | R-03 |
| E-06 | Security review | Incomplete AI activity logging information | R-07, R-08 |
| E-07 | Vendor product sheet | Human oversight claims | R-01, R-06 |
| E-08 | Incident ticket | Unexpected clinical detail in generated summary | R-01, R-04, R-06, R-07 |

---

## 3. Simulated Evidence Records

### E-01 Vendor Security Questionnaire
**Source:** AI vendor  
**Question:** Is customer data used to train or improve your underlying AI models?
**Vendor response:** No. Customer data is not used to train the underlying foundation model.
**Additional statement:** Customer interactions may be processed to maintain service quality.

**Missing information:**
- Does service quality processing involve human review?
- Are prompts and generated outputs retained?
- Does the statement cover third-party model providers?
- Is the restriction contractually enforceable?
- Does the response distinguish model training from other forms of data use?

**Initial assessment:** The response does not establish that customer information is never retained or used for secondary purposes.

**Related risk:** R-02.
### E-02 Contract and Data Processing Extract
**Source:** Simulated vendor agreement
**Relevant wording:**

"The service provider may retain limited customer information where reasonably necessary for service improvement, troubleshooting, and operational support, subject to applicable contractual safeguards."

**Observations:**
- No specific retention period is stated in the extract.
- The meaning of "service improvement" is not defined.
- The extract does not identify all categories of information retained.
- No supporting deletion evidence has been supplied.

**Conflict requiring investigation:**

E-01 states that customer data is not used to train the underlying model. E-02 permits limited retention for service improvement.

These statements are not necessarily contradictory, but the distinction between model training, service improvement, and operational retention needs clarification.

**Evidence requested:**
- Complete data processing agreement.
- Data retention schedule.
- Subprocessor inventory.
- Data deletion and disposal procedures.
- Written explanation of service improvement activities.

**Related risks:** R-02, R-08.

### E-03 IT Architecture Notes
**Source:** Internal IT discussion notes
**Statement from IT:** ClinScribe AI connects to the organization's electronic health record environment.
**Additional observation:** A technical architecture diagram references an external model provider.

**Outstanding questions:**
- Is the external model provider an approved subprocessor?
- What patient information is transmitted?
- Is data encrypted in transit and at rest?
- Are model provider permissions restricted?
- Are prompts and outputs transmitted outside the organization's controlled environment?
- Is the architecture diagram current?

**Evidence limitation:** The diagram has no version number or approval date.
**Initial assessment:** The actual data flow and third-party processing arrangements cannot yet be confirmed.
**Related risks:** R-02, R-04, R-08.

### E-04 Clinician Feedback

**Source:** Simulated clinical user feedback

Two clinicians report that generated summaries have omitted medication changes and patient-reported symptoms.

**Additional information:**
- No patient or encounter identifiers are included.
- No source-to-summary comparison has been provided.
- No frequency analysis is available.
- No formal clinical validation report has been supplied.

**Initial assessment:** The reports are potential indicators of clinical documentation risk. They do not establish the frequency, severity, or systematic nature of the problem.

**Questions requiring investigation:**
- Were the omissions clinically significant?
- Did the original clinical notes contain the omitted information?
- Were clinicians able to identify and correct the omissions?
- Does performance vary across specialties or patient populations?
- Has the vendor tested these failure scenarios?

**Related risks:** R-01, R-05.

### E-05 Access Review Extract
**Source:** Simulated internal access review
**Observation:** A shared clinical support account appears in the access export.

**Missing information:**
- Named account owner.
- Business justification.
- Assigned permissions.
- Authentication requirements.
- Last access review date.
- Activity attributable to individual users.

**Initial assessment:** The existence of a shared account raises accountability and access-control concerns. Its authorization status and actual usage remain unverified.

**Evidence requested:**
- Account ownership record.
- Role and permission assignment.
- Authentication configuration.
- Recent access logs.
- Access review approval.

**Related risk:** R-03.

### E-06 Security Logging Review
**Source:** Simulated security team discussion
**Statement:** Application access logs are available.

**However, the security team cannot confirm whether the following are captured:**
- User prompts.
- AI-generated summaries.
- Model or version identifiers.
- Clinician corrections.
- Approval or rejection actions.
- Relevant timestamps and correlation identifiers.

**Initial assessment:** The existence of application logs does not establish sufficient AI activity traceability.

**Questions requiring investigation:**
- Can an AI-generated summary be linked to its source encounter?
- Can investigators reconstruct the sequence of events?
- Are logs protected against unauthorized modification?
- Are retention periods defined?
- Are sensitive clinical details appropriately protected in logs?

**Related risks:** R-07, R-08.

### E-07 Vendor Product Sheet
**Source:** Simulated vendor marketing documentation
**Vendor claim:** "ClinScribe AI incorporates human-in-the-loop review to support safe clinical documentation."

**Missing implementation details:**
- Is clinician approval mandatory?
- Can an unreviewed summary enter the official patient record?
- Can users bypass review?
- Are corrections recorded?
- Are approval actions attributable to individual users?
- Are users trained to recognize AI-generated errors?

**Initial assessment:** A marketing statement is not sufficient evidence of an enforced human oversight control.

**Evidence requested:**
- Product configuration screenshots.
- Workflow demonstration.
- User acceptance testing.
- Approval and correction audit records.
- Clinical workflow documentation.

**Related risks:** R-01, R-06.

### E-08 Simulated Incident Ticket

**Ticket reference:** INC-008  
**Description:** User reports an unexpected clinical detail in an AI-generated summary.

**Ticket resolution:** "User corrected summary."

**Missing information:**
- Original input and generated output.
- Whether the unexpected detail was fabricated or drawn from another source.
- Whether patient safety was affected.
- Whether the incident was escalated.
- Whether the issue occurred again.
- Whether the vendor was notified.
- Root-cause analysis.

**Initial assessment:** Closing a ticket because a user corrected the output does not establish that the underlying issue was resolved.

The event should be reviewed to determine whether it indicates an output accuracy problem, an input manipulation issue, or another system failure.

**Related risks:** R-01, R-04, R-06, R-07.

---

## 4. Evidence Reliability Assessment

| Evidence ID | Reliability concern | Current assessment |
|---|---|---|
| E-01 | Vendor self-attestation without supporting technical evidence | Unverified |
| E-02 | Contract extract may not represent the complete agreement | Incomplete |
| E-03 | Architecture diagram lacks version and approval details | Incomplete |
| E-04 | Informal feedback without case-level validation | Uncorroborated |
| E-05 | Access export lacks ownership and authorization details | Incomplete |
| E-06 | Verbal statement without log samples or configuration evidence | Unverified |
| E-07 | Marketing claim without workflow demonstration | Unverified |
| E-08 | Incident ticket lacks investigation and closure evidence | Incomplete |

**Assessment principle:** Evidence reliability must be evaluated before using it to establish control effectiveness or reduce risk scores.

---

## 5. AI Guardrail Assessment Initial Position

| Guardrail | Evidence reviewed | Initial position |
|---|---|---|
| Human oversight | E-07, E-08 | Claimed but not demonstrated |
| Output accuracy | E-04, E-08 | Potential failure indicators; validation missing |
| Data protection | E-01, E-02, E-03 | Retention and third-party processing unclear |
| Access restrictions | E-05 | Shared account requires investigation |
| Prompt-injection resistance | E-03, E-08 | No adversarial testing evidence supplied |
| Bias and performance | E-04 | Subgroup performance evidence missing |
| Logging and monitoring | E-06, E-08 | AI activity traceability unverified |
| Accountability | E-02, E-03, E-06, E-07 | Responsibilities require clarification |

**Important:** These are preliminary assessment findings, not confirmed control failures. Missing evidence does not automatically prove that a control does not exist. It means its existence or effectiveness has not been established.

---

## 6. Outstanding Evidence Requests

| Priority | Request | Purpose |
|---|---|---|
| High | Complete data processing agreement and subprocessor list | Clarify data handling and third-party exposure |
| High | Demonstration of mandatory clinician approval | Verify human oversight |
| High | Clinical accuracy testing and validation results | Assess output reliability |
| High | Sample AI activity logs and logging configuration | Verify traceability |
| High | Access permissions and shared account ownership | Validate access restrictions |
| Medium | Adversarial and prompt-injection test results | Assess input manipulation safeguards |
| Medium | Subgroup performance evaluation | Assess potential performance disparities |
| Medium | Incident investigation and escalation procedures | Verify incident accountability |

---

## 7. Preliminary Assessment Conclusion

The available simulated evidence identifies several areas requiring further investigation before ClinScribe AI can be considered ready for production deployment.

The most significant concerns involve clinical output reliability, patient information handling, human oversight, and the ability to investigate AI-related incidents.

The evidence does not establish that the system is unsafe or non-compliant. However, the current documentation is insufficient to demonstrate that the proposed safeguards are implemented and effective.

**Preliminary recommendation:** Defer unrestricted production approval pending resolution of high-priority evidence gaps and validation of critical AI guardrails.

No residual risk reduction is assumed at this stage.


## 8. Assessment Limitations

_This evidence pack is entirely hypothetical. It does not represent an actual vendor assessment, security test, clinical validation, legal determination, or production incident._

All conclusions are provisional and would require corroborating evidence in a real assessment.
