**Healthcare AI Risk Register**

1. Purpose

This register documents hypothetical risks associated with an AI-powered clinical note summarization system. It identifies potential impacts, proposed controls, accountability, and residual risk for further review.

* Assessment status: Initial simulated assessment
* Methodology: NIST AI RMF
* Risk scoring: Qualitative scoring for portfolio demonstration only

2. Scoring Method

Likelihood and impact are scored from 1 to 5.

* Likelihood: 1 = Rare; 2 = Unlikely; 3 = Possible; 4 = Likely; 5 = Almost certain.

* Impact: 1 = Negligible; 2 = Minor; 3 = Moderate; 4 = Major; 5 = Severe.

Inherent risk score = Likelihood × Impact.

Priority bands:

* 1–4: Low

* 5–9: Moderate

* 10–16: High

* 17–25: Critical

These thresholds are a proposed example, not a universal standard. 
Actual scoring requires organizational risk criteria and supporting evidence.

3. Risk Register

ID
Risk scenario
Potential impact
Likelihood
Impact
Inherent score
Proposed controls
Proposed owner

| Risk ID | Risk scenario | Potential Impact | Likelihood | Impact | Inherent Score | Proposed controls | Proposed owner
|---|---|---:|---:|---:|---|---|---|
| R-01 | AI omits or changes clinically significant details in a summary | Inaccurate documentation & potential patient harm | 3 | 5 | 15 - High| Clinician verification; source-to-summary checks; testing against representative clinical cases; correction and escalation workflow | Clinical safety lead|
| R-02 | Patient information is disclosed to an unauthorized party | Patient data exposure, regulatory breach and patient trust | 3 | 5 | 15 - High | Least-privilege access; encryption; approved data-processing arrangements; retention limits; access logging | Security and privacy leads|
| R-03 | Unauthorized access | Confidentiality breach and inappropriate data use | 3 | 5 | 15 - High| Strong authentication; role-based access; periodic access reviews; monitoring and alerting | Identity and access management owner|
| R-04 | Malicious or untrusted input manipulates the model through prompt injection | Sensitive data exposure or unreliable output | 3 | 4 | 12 - High | Input and output handling; isolation of untrusted content; restricted tools and permissions; adversarial testing; human review | AI security lead|
| R-05 | Output quality varies across patient populations or clinical contexts| Unequal documentation quality and potential downstream harm | 3 | 5 | 15 - High| Representative evaluation data; subgroup performance analysis where lawful and appropriate; documented limitations; clinical review | AI product and clinical leads|
| R-06 | Clinicians over-rely on AI-generated summaries| Errors are accepted without adequate review | 3 | 5 | 15 - High| Clear draft labeling; mandatory review before record finalization; user training; audit of review and correction patterns | Clinical operations lead|
| R-07 | Insufficient logging prevents investigation of an AI-related incident| Delayed response and inability to establish what occurred | 3 | 4 | 12 - High | Privacy-conscious audit logging; incident response procedures; retention rules; periodic incident exercises | Security operations lead|
| R-08 | Responsibility for errors, monitoring, and escalation is unclear | Delayed remediation and unmanaged risk | 3 | 4 | 12 - High | Defined accountability; documented risk acceptance; escalation criteria; change management; periodic governance reviews | AI governance lead |

4. Risk Treatment Principles

- Prioritize risks that could cause severe patient harm or expose sensitive information.

- Assign each risk to an accountable owner.

- Record the evidence required to verify that proposed controls operate effectively.

- Reassess likelihood and impact after controls have been implemented and tested.

- Escalate risks that exceed the organization's approved risk tolerance.

- Do not treat a proposed control as implemented or effective until supporting evidence is reviewed.

5. Residual Risk Assessment

Residual scores have not yet been assigned. They must be determined after control implementation and effectiveness testing. 
A reduction in risk must not be assumed merely because a control is documented.

6. Framework Alignment

- NIST AI RMF: Governance, context mapping, risk measurement, and risk treatment.
- EU AI Act: Applicability and obligations require assessment of intended purpose, system role, and deployment context.
- ISO/IEC 27090: Relevant AI cybersecurity threats and risk-treatment considerations.
- ISO/IEC 42001: AI governance responsibilities, risk processes, monitoring, and continual improvement.
- CHAI: Healthcare AI assurance considerations, including safety, transparency, performance, and monitoring.
- HIPAA: Applicable privacy and security requirements, depending on organizational role and circumstances.
- HITECH Act: Healthcare information security, breach notification, and HIPAA enforcement provisions.
- HITRUST CSF: Integrated healthcare information security, privacy and compliance control framework.

Detailed control-level mappings and requirement references will be documented separately.

7. Limitations

All scenarios, scores, and proposed controls in this register are illustrative. They are not based on production telemetry, clinical validation, an actual security assessment, or a confirmed legal classification.
