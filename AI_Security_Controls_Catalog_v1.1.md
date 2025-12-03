# AI Security Controls Catalog

**[Organization Name]**

**Version 1.1**

**[Effective Date]**

---

| Field | Value |
|-------|-------|
| Document Owner | [Chief Information Security Officer] |
| Parent Policy | Enterprise AI Governance Policy |
| Related Documents | AI Risk Assessment Framework, AI System Documentation Standards, AI Implementation Playbook |
| Review Cycle | Annual or upon significant framework updates |

---

## Table of Contents

1. Introduction
2. Control Framework Overview
3. Governance Controls (GOV)
4. Data Governance Controls (DATA)
5. Model Lifecycle Controls (MODEL)
6. Operational Security Controls (OPS)
7. Supply Chain Controls (SUPPLY)
8. LLM/GenAI Security Controls (LLM)
9. Appendix A: Control Applicability Matrix
10. Appendix B: Framework Mapping

---

## 1. Introduction

### 1.1 Purpose

This catalog defines the security and governance controls applicable to AI systems at [Organization Name]. It provides a comprehensive set of controls organized by domain, with implementation guidance and risk-tier applicability to enable proportionate security measures based on AI system classification.

### 1.2 Scope

This catalog applies to all AI systems within scope of the Enterprise AI Governance Policy. Controls are designed to address the unique risks associated with AI systems throughout their lifecycle, from development through deployment and ongoing operations. The controls supplement, rather than replace, existing information security controls and should be implemented in conjunction with the organization's broader security framework.

*For practical implementation guidance, including sequencing recommendations, quick wins, and domain-specific checklists, refer to the AI Implementation Playbook, Section 4: Control Implementation Guides.*

*Documentation requirements for control implementation evidence are specified in the AI System Documentation Standards, Section 6: Security Documentation Standards.*

### 1.3 Framework Sources

Controls in this catalog are derived from and mapped to the following authoritative sources:

| Framework | Description |
|-----------|-------------|
| NIST AI RMF 1.0 | NIST AI Risk Management Framework providing Govern, Map, Measure, and Manage functions with associated subcategories |
| ISO/IEC 42001:2023 | AI Management System standard with 39 Annex A controls covering AI system lifecycle governance |
| OWASP LLM Top 10 | 2025 edition addressing security risks specific to Large Language Model applications |
| NIST CSF 2.0 | Cybersecurity Framework providing foundational security controls extended for AI contexts |

### 1.4 How to Use This Catalog

This catalog should be used in conjunction with the AI Risk Assessment Framework. After an AI system has been assessed and assigned a risk tier, reference this catalog to identify applicable controls:

1. Identify the AI system's risk tier (HIGH, MODERATE, or LOW)
2. Review each control domain relevant to the AI system
3. Implement controls marked as applicable for the assigned risk tier
4. Document control implementation in the AI system's governance record
5. Validate control effectiveness during periodic assessments

---

## 2. Control Framework Overview

### 2.1 Control Domains

Controls are organized into six domains that address the full spectrum of AI security and governance requirements:

| Domain ID | Domain Name | Description |
|-----------|-------------|-------------|
| GOV | Governance | Organizational policies, roles, accountability, and oversight mechanisms for AI systems |
| DATA | Data Governance | Data quality, provenance, privacy, and protection throughout the AI data lifecycle |
| MODEL | Model Lifecycle | Development, validation, deployment, and maintenance of AI models |
| OPS | Operational Security | Runtime security, monitoring, incident response, and access management |
| SUPPLY | Supply Chain | Third-party AI vendors, models, components, and data sources |
| LLM | LLM/GenAI Security | Controls specific to Large Language Models and Generative AI applications |

### 2.2 Control Structure

Each control in this catalog includes the following elements:

| Element | Description |
|---------|-------------|
| Control ID | Unique identifier using format [DOMAIN]-[NUMBER] (e.g., GOV-01, DATA-03) |
| Control Name | Brief descriptive name for the control |
| Control Description | Detailed statement of what the control requires |
| Implementation Guidance | Practical guidance on how to implement the control |
| Risk Tier Applicability | Indicates which risk tiers (H/M/L) require this control |
| Framework Mapping | Reference to source framework controls (NIST AI RMF, ISO 42001, OWASP) |

### 2.3 Risk Tier Applicability

Controls are designated as required (R), recommended (r), or not applicable (—) for each risk tier:

| Designation | Meaning |
|-------------|---------|
| **HIGH (H)** | All controls marked 'R' for HIGH are mandatory. Full implementation with evidence required. |
| **MODERATE (M)** | Controls marked 'R' for MODERATE are mandatory. Controls marked 'r' are recommended based on context. |
| **LOW (L)** | Controls marked 'R' for LOW are mandatory. Most advanced controls are optional for LOW risk systems. |

### 2.4 Control Summary by Domain

| Domain | Focus Area | Controls | HIGH Req | LOW Req |
|--------|------------|----------|----------|---------|
| GOV | Governance | 8 | 8 | 4 |
| DATA | Data Governance | 8 | 8 | 4 |
| MODEL | Model Lifecycle | 10 | 10 | 4 |
| OPS | Operational Security | 8 | 8 | 5 |
| SUPPLY | Supply Chain | 6 | 6 | 3 |
| LLM | LLM/GenAI Security | 10 | 10 | 5 |
| **TOTAL** | | **50** | **50** | **25** |

---

## 3. Governance Controls (GOV)

Governance controls establish the organizational structures, policies, and accountability mechanisms necessary for responsible AI system management.

### GOV-01: AI System Inventory

| | |
|---|---|
| **Control ID** | GOV-01 |
| **Control Name** | AI System Inventory |
| **Description** | The organization shall establish and maintain a comprehensive inventory of all AI systems, including internally developed systems, third-party AI services, and AI components embedded in other applications. |
| **Implementation Guidance** | Implement a centralized AI system registry that captures: system name and unique identifier, business owner and technical owner, risk classification tier, deployment status (development/staging/production), data sources and types processed, model type and version, deployment date and last assessment date, vendor information for third-party systems. Review and update the inventory at least quarterly. Integrate with IT asset management and CMDB where applicable. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.1, MAP 1.1 \| ISO 42001: A.4.2, A.4.4 \| NIST CSF: ID.AM-1, ID.AM-2 |

### GOV-02: AI System Ownership

| | |
|---|---|
| **Control ID** | GOV-02 |
| **Control Name** | AI System Ownership |
| **Description** | Each AI system shall have a designated System Owner who is accountable for the system's compliance with governance requirements, risk management, and operational performance throughout its lifecycle. |
| **Implementation Guidance** | Document the System Owner assignment in the AI system registry. System Owner responsibilities include: ensuring risk assessments are completed and current, approving changes to the AI system, coordinating with security and compliance stakeholders, maintaining required documentation, reporting to the AI Governance Board as required, ensuring adequate resources for governance activities. System Owners should be at an appropriate management level commensurate with the system's risk tier. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.2, GOVERN 2.1 \| ISO 42001: A.4.3 \| NIST CSF: ID.GV-2 |

### GOV-03: AI Governance Board Oversight

|                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Control ID**              | GOV-03                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Control Name**            | AI Governance Board Oversight                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Description**             | An AI Governance Board shall provide executive oversight of AI systems, including approval authority for HIGH risk deployments, policy direction, and strategic alignment of AI initiatives with organizational objectives.                                                                                                                                                                                                                                            |
| **Implementation Guidance** | Establish a cross-functional AI Governance Board with representation from: executive leadership, information security, privacy/compliance, clinical leadership (for healthcare applications), legal, data science/AI technical leadership. The Board should meet at least quarterly and additionally as needed for HIGH risk approvals. Document Board charter, membership, decision-making authority, and escalation procedures. Maintain minutes of Board decisions. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Framework Mapping**       | NIST AI RMF: GOVERN 1.1, GOVERN 1.3 \| ISO 42001: 5.1, A.2.2 \| NIST CSF: ID.GV-1                                                                                                                                                                                                                                                                                                                                                                                      |

### GOV-04: AI Risk Assessment Process

| | |
|---|---|
| **Control ID** | GOV-04 |
| **Control Name** | AI Risk Assessment Process |
| **Description** | The organization shall implement a formal risk assessment process for evaluating AI systems against defined risk factors and assigning appropriate risk classifications to determine governance and control requirements. |
| **Implementation Guidance** | Implement the AI Risk Assessment Framework for all AI systems. Ensure assessments are conducted: prior to initial deployment, upon significant changes to use case or functionality, upon substantial model retraining, at scheduled intervals per risk tier (6 months for HIGH, annually for MODERATE, every 2 years for LOW), following AI-related incidents. Document assessment results and maintain assessment history. Integrate risk assessment into project intake and change management processes. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MAP 1.1, MAP 1.5, MEASURE 1.1 \| ISO 42001: A.5.3, A.5.4 \| NIST CSF: ID.RA-1, ID.RA-3 |

### GOV-05: AI System Documentation

| | |
|---|---|
| **Control ID** | GOV-05 |
| **Control Name** | AI System Documentation |
| **Description** | AI systems shall maintain comprehensive documentation proportionate to their risk tier, including system architecture, model information, data sources, validation results, and operational procedures. |
| **Implementation Guidance** | Documentation requirements by tier: HIGH - Full documentation package including model cards, training data provenance, validation reports, bias assessments, architecture diagrams, operational runbooks, and incident response procedures. MODERATE - Standard documentation including system description, data flow diagrams, validation summary, control implementation evidence. LOW - Basic documentation including use case description, system registration, data classification. Use standardized templates to ensure consistency. Store documentation in a centralized, access-controlled repository. See **AI System Documentation Standards** for detailed requirements. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.5, MAP 1.3 \| ISO 42001: A.4.5, A.6.2.4 \| NIST CSF: ID.GV-3 |

### GOV-06: AI Training and Awareness

| | |
|---|---|
| **Control ID** | GOV-06 |
| **Control Name** | AI Training and Awareness |
| **Description** | The organization shall provide AI-specific training to workforce members based on their roles and responsibilities related to AI systems, including developers, users, and oversight personnel. |
| **Implementation Guidance** | Develop and deliver role-based training: General AI Awareness - all workforce members interacting with AI systems (AI governance principles, acceptable use, reporting procedures). AI Developer Training - development staff (secure AI development, bias mitigation, documentation requirements, testing procedures). AI User Training - end users of AI systems (appropriate reliance, limitations awareness, escalation procedures). Leadership Training - governance and oversight personnel (risk management, regulatory requirements, strategic considerations). Track training completion and require refresher training annually or upon significant policy changes. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: GOVERN 2.2 \| ISO 42001: A.4.6 \| NIST CSF: PR.AT-1, PR.AT-2 |

### GOV-07: AI Ethics and Responsible Use

| | |
|---|---|
| **Control ID** | GOV-07 |
| **Control Name** | AI Ethics and Responsible Use |
| **Description** | The organization shall establish and communicate ethical principles for AI use, ensuring that AI systems are developed and operated in alignment with organizational values, patient safety priorities, and societal expectations. |
| **Implementation Guidance** | Document and communicate AI ethical principles addressing: patient safety and clinical validity, transparency and explainability, fairness and non-discrimination, privacy and data protection, human oversight and accountability, beneficial use and harm avoidance. Integrate ethical review into the AI approval process for HIGH risk systems. Establish mechanisms for stakeholders to raise ethical concerns. Consider establishing an AI Ethics Advisory function for complex ethical questions. Review ethical principles annually and update based on emerging best practices. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.2, MAP 1.6 \| ISO 42001: A.2.3, A.8.4 \| NIST CSF: ID.GV-2 |

### GOV-08: Regulatory Compliance Management

| | |
|---|---|
| **Control ID** | GOV-08 |
| **Control Name** | Regulatory Compliance Management |
| **Description** | The organization shall identify, monitor, and ensure compliance with applicable regulatory requirements affecting AI systems, including healthcare-specific regulations, privacy laws, and emerging AI-specific legislation. |
| **Implementation Guidance** | Maintain awareness of regulatory requirements including: HIPAA and state health privacy laws, FDA regulations for AI/ML-based medical devices and Software as a Medical Device (SaMD), state AI-specific legislation, FTC guidance on AI and automated decision-making, emerging requirements (EU AI Act for organizations with European operations or partners). Conduct regulatory impact assessments for HIGH risk AI systems. Engage Legal and Compliance in review of AI systems with significant regulatory exposure. Monitor regulatory developments and update compliance requirements accordingly. Document compliance status in the AI system registry. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.4, GOVERN 1.6 \| ISO 42001: A.3.2, A.3.4 \| NIST CSF: ID.GV-3, ID.GV-4 |

---

## 4. Data Governance Controls (DATA)

Data governance controls ensure that data used in AI systems is appropriately managed throughout its lifecycle.

### DATA-01: Training Data Provenance

| | |
|---|---|
| **Control ID** | DATA-01 |
| **Control Name** | Training Data Provenance |
| **Description** | The organization shall document and maintain records of the origin, lineage, and processing history of data used to train or fine-tune AI models, ensuring traceability and enabling assessment of data quality and appropriateness. |
| **Implementation Guidance** | For internally trained or fine-tuned models, document: original data sources and collection methods, data processing and transformation steps, filtering or sampling criteria applied, date ranges of data included, known limitations or gaps in the data. For third-party models, obtain vendor documentation of training data characteristics where available. Maintain provenance records in a format that enables auditing. For HIGH risk systems, provenance documentation should be sufficient to reproduce the training dataset or explain why reproduction is not possible. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 2.1, MAP 2.3 \| ISO 42001: A.6.2.3, A.7.3 \| NIST CSF: ID.AM-3 |

### DATA-02: Data Quality Assessment

| | |
|---|---|
| **Control ID** | DATA-02 |
| **Control Name** | Data Quality Assessment |
| **Description** | Data used in AI systems shall be assessed for quality, including accuracy, completeness, consistency, timeliness, and relevance to the intended use case, with documented quality metrics and acceptance criteria. |
| **Implementation Guidance** | Establish data quality dimensions appropriate to the AI use case: accuracy (correctness of data values), completeness (presence of required data elements), consistency (uniformity across data sources), timeliness (currency of data for intended use), relevance (appropriateness for the AI application). Define quality thresholds and acceptance criteria. Implement automated data quality checks where feasible. Document quality assessment results and remediation actions. For HIGH risk systems, conduct independent data quality reviews. Reassess data quality when data sources change or quality issues are identified. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 2.2, MEASURE 2.6 \| ISO 42001: A.7.2, A.7.4 \| NIST CSF: ID.AM-3 |

### DATA-03: Data Privacy and Consent

| | |
|---|---|
| **Control ID** | DATA-03 |
| **Control Name** | Data Privacy and Consent |
| **Description** | AI systems shall process personal data only with appropriate legal basis, consent where required, and in compliance with applicable privacy regulations including HIPAA. |
| **Implementation Guidance** | Identify all personal data processed by the AI system. Determine and document the legal basis for processing (consent, legitimate interest, treatment operations, etc.). For PHI, ensure HIPAA-compliant authorizations or applicable exceptions. Implement data minimization - collect only data necessary for the AI use case. Conduct Privacy Impact Assessment for systems processing sensitive personal data. Document data subject rights and how they will be honored. For AI training data, ensure appropriate consent or authorization covers AI/ML use cases. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MAP 2.1 \| ISO 42001: A.7.5 \| NIST CSF: PR.DS-1 |

### DATA-04: Data Classification and Handling

| | |
|---|---|
| **Control ID** | DATA-04 |
| **Control Name** | Data Classification and Handling |
| **Description** | Data used in AI systems shall be classified according to sensitivity and handled in accordance with organizational data protection policies. |
| **Implementation Guidance** | Apply organizational data classification scheme to all AI training, validation, and operational data. Implement handling controls appropriate to classification level: encryption at rest and in transit for sensitive data, access controls limiting data access to authorized personnel, secure storage in approved environments, audit logging of data access, secure disposal when no longer needed. Document data classification in AI system inventory. Special handling required for PHI, mental health, substance abuse, HIV, and genetic data. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MAP 2.1 \| ISO 42001: A.7.1 \| NIST CSF: PR.DS-1, PR.DS-2 |

### DATA-05: Data Retention and Disposal

| | |
|---|---|
| **Control ID** | DATA-05 |
| **Control Name** | Data Retention and Disposal |
| **Description** | Training data, model artifacts, and operational data shall be retained and disposed of in accordance with organizational retention policies and regulatory requirements. |
| **Implementation Guidance** | Define retention periods for: training datasets, validation datasets, model artifacts and versions, operational logs and outputs, documentation and assessments. Implement secure disposal procedures ensuring data cannot be recovered. Consider regulatory requirements (HIPAA minimum 6 years, FDA requirements for medical devices). Document retention decisions in AI system records. For third-party AI, understand vendor data retention practices. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: GOVERN 1.5 \| ISO 42001: A.7.6 \| NIST CSF: PR.DS-3 |

### DATA-06: Data Integrity Protection

| | |
|---|---|
| **Control ID** | DATA-06 |
| **Control Name** | Data Integrity Protection |
| **Description** | Controls shall be implemented to protect the integrity of data used in AI systems, preventing unauthorized modification of training data, model inputs, or outputs. |
| **Implementation Guidance** | Implement integrity controls including: checksums or hashes for training data validation, version control for datasets, access controls preventing unauthorized modification, audit logging of data changes, input validation for operational data. For HIGH risk systems, implement tamper detection mechanisms. Protect against data poisoning attacks by validating data sources and monitoring for anomalous data patterns. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.2 \| ISO 42001: A.7.4 \| NIST CSF: PR.DS-6 |

### DATA-07: Synthetic Data Governance

| | |
|---|---|
| **Control ID** | DATA-07 |
| **Control Name** | Synthetic Data Governance |
| **Description** | When synthetic data is used for AI training or testing, controls shall ensure the synthetic data does not enable re-identification and maintains appropriate statistical properties. |
| **Implementation Guidance** | Document synthetic data generation methodology. Assess and document re-identification risk. Validate that synthetic data maintains statistical properties needed for intended use. Apply same classification as source data unless formal de-identification assessment conducted. Implement access controls for synthetic data commensurate with residual risk. Do not use synthetic data as substitute for real-world validation for clinical AI. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 2.3 \| ISO 42001: A.7.3 |

### DATA-08: Data Bias Assessment

| | |
|---|---|
| **Control ID** | DATA-08 |
| **Control Name** | Data Bias Assessment |
| **Description** | Training and validation data shall be assessed for potential biases that could result in discriminatory or inequitable AI system outputs. |
| **Implementation Guidance** | Analyze training data demographics and compare to intended deployment population. Identify underrepresented groups that may experience degraded model performance. Document known data gaps and limitations. For healthcare AI, assess representation across: age groups, sex/gender, race/ethnicity, geographic regions, socioeconomic factors, disease severity/comorbidities. Document bias assessment methodology and findings. Implement data collection strategies to address identified gaps where feasible. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 2.3, MEASURE 2.10 \| ISO 42001: A.8.4 |

---

## 5. Model Lifecycle Controls (MODEL)

Model lifecycle controls address the development, validation, deployment, and maintenance of AI models.

### MODEL-01: Secure Model Development

| | |
|---|---|
| **Control ID** | MODEL-01 |
| **Control Name** | Secure Model Development |
| **Description** | AI models shall be developed using secure development practices that address AI-specific risks throughout the development lifecycle. |
| **Implementation Guidance** | Implement secure AI development practices including: secure development environment with access controls, code review for ML pipelines, dependency scanning for ML libraries, secrets management for API keys and credentials, separation of development/test/production environments. Use approved ML frameworks and libraries. Document development environment configuration. Implement version control for all code and configurations. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 3.4 \| ISO 42001: A.6.2.2 \| NIST CSF: PR.DS-7 |

### MODEL-02: Model Documentation (Model Cards)

| | |
|---|---|
| **Control ID** | MODEL-02 |
| **Control Name** | Model Documentation (Model Cards) |
| **Description** | AI models shall be documented using a standardized model card format that describes the model's purpose, performance characteristics, limitations, and appropriate use. |
| **Implementation Guidance** | Create model cards including: model description and architecture, intended use and users, training data summary, performance metrics on validation data, performance across demographic subgroups, known limitations and failure modes, ethical considerations, update history. Update model cards when models are retrained or modified. Make model cards accessible to system users and oversight personnel. See **AI System Documentation Standards, Section 3** for detailed model card requirements. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MAP 1.3, MEASURE 2.5 \| ISO 42001: A.6.2.4 |

### MODEL-03: Model Validation

| | |
|---|---|
| **Control ID** | MODEL-03 |
| **Control Name** | Model Validation |
| **Description** | AI models shall undergo formal validation to verify performance meets requirements before deployment and after significant changes. |
| **Implementation Guidance** | Establish validation requirements including: defined performance metrics and thresholds, held-out test dataset separate from training data, validation across relevant subgroups, comparison to baseline or alternative approaches. For HIGH risk systems: independent validation by personnel not involved in development, external validation on different data sources where feasible. Document validation methodology and results. Require re-validation after retraining or significant changes. See **AI Implementation Playbook, Section 3** for validation execution guidance. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.6, MEASURE 2.7 \| ISO 42001: A.6.2.5 |

### MODEL-04: Bias and Fairness Testing

| | |
|---|---|
| **Control ID** | MODEL-04 |
| **Control Name** | Bias and Fairness Testing |
| **Description** | AI models shall be tested for bias and fairness across protected groups before deployment and periodically during operation. |
| **Implementation Guidance** | Define protected attributes to test (age, sex, race/ethnicity, etc.). Select appropriate fairness metrics (demographic parity, equalized odds, predictive parity). Establish acceptable disparity thresholds. Test model performance across subgroups. Document testing methodology and results. For identified disparities: analyze root causes, implement mitigation where feasible, document residual disparities and justification for acceptance. Repeat bias testing after retraining and periodically in production. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.10, MEASURE 2.11 \| ISO 42001: A.8.4 |

### MODEL-05: Adversarial Robustness Testing

| | |
|---|---|
| **Control ID** | MODEL-05 |
| **Control Name** | Adversarial Robustness Testing |
| **Description** | AI models shall be tested for robustness against adversarial inputs and attacks appropriate to the system's risk level and threat model. |
| **Implementation Guidance** | For HIGH risk systems, conduct adversarial testing including: input perturbation testing, evasion attack simulation, boundary case testing, stress testing with out-of-distribution inputs. Document threat model and attack scenarios tested. Implement defenses for identified vulnerabilities. For clinical AI, test with clinically plausible adversarial examples. Consider engaging specialized AI security testing resources for HIGH risk systems. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: r, LOW: — |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.9 \| ISO 42001: A.8.3 \| OWASP LLM: LLM09 |

### MODEL-06: Model Version Control

| | |
|---|---|
| **Control ID** | MODEL-06 |
| **Control Name** | Model Version Control |
| **Description** | AI models shall be subject to version control that tracks all changes and enables rollback to previous versions. |
| **Implementation Guidance** | Implement version control for: model artifacts (weights, configurations), training code and pipelines, training and validation datasets (or references), hyperparameters and settings. Use semantic versioning (MAJOR.MINOR.PATCH). Maintain version history with change documentation. Enable rapid rollback to previous versions. Retain previous versions per retention requirements. Link model versions to documentation and validation results. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.4 \| ISO 42001: A.6.2.6 \| NIST CSF: PR.DS-7 |

### MODEL-07: Model Change Management

| | |
|---|---|
| **Control ID** | MODEL-07 |
| **Control Name** | Model Change Management |
| **Description** | Changes to AI models shall be subject to formal change management processes proportionate to the system's risk tier. |
| **Implementation Guidance** | Establish change management process including: change request documentation, impact assessment, approval workflow per risk tier, testing requirements before deployment, rollback procedures. Change types requiring management: retraining (any), architecture changes, threshold adjustments, feature changes, dependency updates. Document all changes in change log. For HIGH risk systems, require validation testing for all changes. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.4 \| ISO 42001: A.6.2.6 \| NIST CSF: PR.IP-3 |

### MODEL-08: Model Explainability

| | |
|---|---|
| **Control ID** | MODEL-08 |
| **Control Name** | Model Explainability |
| **Description** | AI systems shall provide explanations of their outputs appropriate to the use case, user needs, and risk level. |
| **Implementation Guidance** | Determine appropriate explainability level based on: use case requirements, user needs, regulatory requirements, risk tier. Implement explainability techniques such as: feature importance, attention visualization, counterfactual explanations, confidence scores. For clinical AI, explanations should support clinical reasoning. Document explainability approach and limitations. Test that explanations are accurate and useful to intended users. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.8 \| ISO 42001: A.8.2 |

### MODEL-09: Model Reproducibility

| | |
|---|---|
| **Control ID** | MODEL-09 |
| **Control Name** | Model Reproducibility |
| **Description** | AI model training shall be documented sufficiently to enable reproduction of training results. |
| **Implementation Guidance** | Document elements needed for reproducibility: training data or data generation process, preprocessing and feature engineering steps, model architecture and hyperparameters, training procedure and stopping criteria, random seeds, software versions and dependencies. For HIGH risk systems, verify reproducibility by retraining and comparing results. Accept that perfect reproducibility may not be achievable for all models; document expected variation. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: r, LOW: — |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.5 \| ISO 42001: A.6.2.4 |

### MODEL-10: Model Retirement

| | |
|---|---|
| **Control ID** | MODEL-10 |
| **Control Name** | Model Retirement |
| **Description** | Procedures shall be established for retiring AI models, including secure disposition and transition to replacement systems. |
| **Implementation Guidance** | Establish retirement procedures including: stakeholder notification, transition planning to replacement system or manual process, secure archival of model artifacts and documentation, secure deletion of models from production systems, update AI inventory to reflect retired status. Retain documentation per retention requirements. Assess impact on dependent systems. For clinical AI, coordinate with clinical stakeholders on transition. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MANAGE 4.2 \| ISO 42001: A.6.2.8 |

---

## 6. Operational Security Controls (OPS)

Operational security controls address runtime security, access management, monitoring, and incident response.

### OPS-01: AI System Access Control

| | |
|---|---|
| **Control ID** | OPS-01 |
| **Control Name** | AI System Access Control |
| **Description** | Access to AI systems, including APIs, administrative interfaces, and underlying infrastructure, shall be controlled based on the principle of least privilege. |
| **Implementation Guidance** | Implement role-based access control (RBAC) with defined roles: administrator, developer, operator, user. Require authentication for all access. Implement MFA for administrative access to HIGH risk systems. Review access permissions quarterly. Implement API authentication and rate limiting. Log all access attempts. Promptly revoke access for terminated or transferred personnel. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.2 \| ISO 42001: A.5.6 \| NIST CSF: PR.AC-1, PR.AC-4 |

### OPS-02: AI System Logging and Monitoring

| | |
|---|---|
| **Control ID** | OPS-02 |
| **Control Name** | AI System Logging and Monitoring |
| **Description** | AI systems shall implement comprehensive logging of system activities, inputs, outputs, and security events to enable monitoring, auditing, and incident investigation. |
| **Implementation Guidance** | Log: authentication and access events, administrative actions, model predictions/outputs (with appropriate privacy controls), errors and exceptions, performance metrics, security events. Protect log integrity. Retain logs per organizational requirements (minimum 1 year for HIGH risk). Implement real-time monitoring for HIGH risk systems. Forward logs to SIEM for security monitoring. Balance logging completeness with privacy (avoid logging sensitive inputs where not needed). |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.3 \| ISO 42001: A.5.5 \| NIST CSF: DE.AE-3, PR.PT-1 |

### OPS-03: Model Performance Monitoring

| | |
|---|---|
| **Control ID** | OPS-03 |
| **Control Name** | Model Performance Monitoring |
| **Description** | AI models in production shall be continuously monitored for performance degradation, data drift, and anomalous behavior. |
| **Implementation Guidance** | Monitor: prediction accuracy (where ground truth available), input data distribution (data drift), output distribution (concept drift), latency and throughput, error rates. Establish baseline metrics and alert thresholds. Implement automated drift detection where feasible. Review monitoring dashboards per schedule (weekly for HIGH, monthly for MODERATE). Investigate and document drift events. Trigger re-validation when significant drift detected. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MEASURE 3.2, MANAGE 3.1 \| ISO 42001: A.9.3 |

### OPS-04: AI Incident Response

| | |
|---|---|
| **Control ID** | OPS-04 |
| **Control Name** | AI Incident Response |
| **Description** | Procedures shall be established for responding to AI-specific security incidents, including containment, investigation, and recovery. |
| **Implementation Guidance** | Develop AI incident response procedures addressing: incident detection and classification, immediate containment (including kill switch activation), investigation procedures, communication and escalation, recovery and restoration, post-incident review. Define AI-specific incident types: adversarial attacks, data poisoning, model extraction, bias events, clinical safety events. Integrate with organizational incident response program. Conduct tabletop exercises annually for HIGH risk systems. See **AI Implementation Playbook, Section 10** for detailed procedures. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 4.1 \| ISO 42001: A.5.7 \| NIST CSF: RS.RP-1 |

### OPS-05: Human Override Capability

| | |
|---|---|
| **Control ID** | OPS-05 |
| **Control Name** | Human Override Capability |
| **Description** | AI systems shall include mechanisms for human operators to override, modify, or disable AI outputs or operations. |
| **Implementation Guidance** | Implement override capabilities including: ability for users to reject/modify AI recommendations, kill switch to disable AI functionality, fallback to manual process when AI unavailable. For HIGH risk systems, override should be accessible without special tools or permissions. Log all override actions with user and reason. Monitor override rates as signal of potential issues. Document override procedures in operational runbook. For clinical AI, ensure clinicians can always override AI recommendations. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.1 \| ISO 42001: A.8.5 |

### OPS-06: AI System Availability

| | |
|---|---|
| **Control ID** | OPS-06 |
| **Control Name** | AI System Availability |
| **Description** | AI systems shall be designed and operated to meet availability requirements appropriate to their criticality and risk tier. |
| **Implementation Guidance** | Define availability requirements based on business impact. Implement appropriate measures: redundancy for critical systems, failover procedures, backup and recovery, capacity planning. Establish SLAs for availability. Monitor availability metrics. Document fallback procedures when AI system unavailable. For clinical AI, ensure availability requirements support clinical workflows. Test recovery procedures periodically. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.2 \| ISO 42001: A.5.4 \| NIST CSF: PR.PT-5 |

### OPS-07: AI Output Validation

| | |
|---|---|
| **Control ID** | OPS-07 |
| **Control Name** | AI Output Validation |
| **Description** | AI system outputs shall be validated for reasonableness and safety before being acted upon or presented to users. |
| **Implementation Guidance** | Implement output validation including: range/boundary checks, consistency checks, anomaly detection for unusual outputs, confidence thresholds, output filtering for harmful content (GenAI). For clinical AI, implement clinical reasonableness checks. Flag low-confidence predictions for human review. Suppress or quarantine outputs that fail validation. Log validation failures for investigation. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.3 \| ISO 42001: A.8.3 |

### OPS-08: AI System Hardening

| | |
|---|---|
| **Control ID** | OPS-08 |
| **Control Name** | AI System Hardening |
| **Description** | AI system infrastructure shall be hardened according to security best practices and organizational standards. |
| **Implementation Guidance** | Apply standard system hardening: patch management, secure configurations, unnecessary services disabled, network segmentation, encryption in transit and at rest. AI-specific hardening: secure model serving configurations, API security, rate limiting, input size limits. Conduct vulnerability scanning. Address findings per organizational vulnerability management process. For HIGH risk systems, conduct penetration testing. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.2 \| ISO 42001: A.5.6 \| NIST CSF: PR.IP-1 |

---

## 7. Supply Chain Controls (SUPPLY)

Supply chain controls address risks from third-party AI vendors, models, components, and data.

### SUPPLY-01: AI Vendor Assessment

| | |
|---|---|
| **Control ID** | SUPPLY-01 |
| **Control Name** | AI Vendor Assessment |
| **Description** | Third-party AI vendors shall be assessed for security, privacy, and AI governance practices before procurement. |
| **Implementation Guidance** | Assess vendors for: security certifications (SOC 2, ISO 27001, HITRUST), AI governance practices and documentation, bias testing and fairness validation, data handling and privacy practices, incident response capabilities, business continuity, regulatory compliance. Use standardized vendor assessment questionnaire. Require evidence of claims. Reassess periodically and upon contract renewal. See **AI Implementation Playbook, Section 6** for vendor assessment procedures. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 6.1 \| ISO 42001: A.10.2 \| NIST CSF: ID.SC-2 |

### SUPPLY-02: AI Vendor Contracts

| | |
|---|---|
| **Control ID** | SUPPLY-02 |
| **Control Name** | AI Vendor Contracts |
| **Description** | Contracts with AI vendors shall include provisions addressing data protection, transparency, security, and accountability. |
| **Implementation Guidance** | Include contractual provisions for: data ownership and use restrictions, prohibition on using customer data for training without consent, transparency and explainability requirements, security requirements and incident notification, audit rights, model update notification, SLAs for availability and performance, liability and indemnification, exit provisions and data return. Engage Legal in contract review. Document approved vendor contracts. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 6.2 \| ISO 42001: A.10.3 \| NIST CSF: ID.SC-3 |

### SUPPLY-03: Third-Party Model Validation

| | |
|---|---|
| **Control ID** | SUPPLY-03 |
| **Control Name** | Third-Party Model Validation |
| **Description** | Third-party AI models shall be validated for performance and safety in the organization's operational context before deployment. |
| **Implementation Guidance** | Do not rely solely on vendor-reported performance. Conduct internal validation including: performance testing on representative organizational data, bias testing across relevant subgroups, validation that model meets use case requirements. For clinical AI, conduct clinical validation with clinical stakeholder involvement. Document validation results. Require re-validation when vendor updates models. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MEASURE 2.7 \| ISO 42001: A.10.4 |

### SUPPLY-04: AI Dependency Management

| | |
|---|---|
| **Control ID** | SUPPLY-04 |
| **Control Name** | AI Dependency Management |
| **Description** | Dependencies used in AI systems, including ML frameworks, libraries, and pre-trained models, shall be inventoried, assessed, and monitored for vulnerabilities. |
| **Implementation Guidance** | Maintain inventory of: ML frameworks (TensorFlow, PyTorch, etc.), supporting libraries, pre-trained models and weights, data processing tools. Use approved/vetted components. Scan dependencies for vulnerabilities. Monitor for security advisories. Update dependencies per vulnerability management process. Verify integrity of downloaded components (checksums, signatures). Restrict use of unvetted open-source models. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | NIST AI RMF: GOVERN 6.1 \| ISO 42001: A.10.5 \| NIST CSF: ID.SC-2 \| OWASP LLM: LLM05 |

### SUPPLY-05: Pre-trained Model Security

| | |
|---|---|
| **Control ID** | SUPPLY-05 |
| **Control Name** | Pre-trained Model Security |
| **Description** | Pre-trained models obtained from external sources shall be assessed for security risks, including potential backdoors or malicious behaviors. |
| **Implementation Guidance** | Assess pre-trained models for: source reputation and trustworthiness, documentation of training data and methodology, known vulnerabilities or issues, licensing and usage restrictions. For HIGH risk use cases, prefer models from vetted sources with transparency. Consider fine-tuning risks (backdoors can persist). Test model behavior for anomalies. Document model provenance in system records. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MAP 3.5 \| ISO 42001: A.10.5 \| OWASP LLM: LLM05 |

### SUPPLY-06: Vendor Update Management

| | |
|---|---|
| **Control ID** | SUPPLY-06 |
| **Control Name** | Vendor Update Management |
| **Description** | Updates to third-party AI systems shall be assessed and approved before deployment in accordance with change management requirements. |
| **Implementation Guidance** | Require vendor notification of model/system updates. Assess updates for: changes to model behavior, performance impact, security implications, regulatory impact. Test updates before production deployment. Maintain ability to defer updates if assessment identifies concerns. Document update decisions. For HIGH risk systems, require re-validation after vendor updates. Negotiate appropriate update notification timelines in contracts. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | NIST AI RMF: MANAGE 2.4 \| ISO 42001: A.10.4 |

---

## 8. LLM/GenAI Security Controls (LLM)

LLM-specific controls address risks unique to Large Language Models and Generative AI applications.

### LLM-01: Prompt Injection Prevention

| | |
|---|---|
| **Control ID** | LLM-01 |
| **Control Name** | Prompt Injection Prevention |
| **Description** | Controls shall be implemented to prevent prompt injection attacks that could manipulate LLM behavior or bypass safety controls. |
| **Implementation Guidance** | Implement defense-in-depth: input validation and sanitization, clear separation of system prompts and user inputs, output validation for signs of injection success, monitoring for injection attempts. Use prompt templates with parameterized inputs. Avoid passing raw user input directly to prompts. Test for prompt injection vulnerabilities. Consider specialized prompt injection detection tools. Document system prompts securely. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | OWASP LLM: LLM01 \| NIST AI RMF: MANAGE 2.2 |

### LLM-02: Sensitive Information Protection

| | |
|---|---|
| **Control ID** | LLM-02 |
| **Control Name** | Sensitive Information Protection |
| **Description** | Controls shall prevent LLMs from exposing sensitive information, including training data, system prompts, and organizational data. |
| **Implementation Guidance** | Implement: output filtering for PII/PHI, monitoring for training data leakage, system prompt protection, restrictions on queries about system configuration. Do not include sensitive information in system prompts. Implement data loss prevention for LLM outputs. For RAG systems, ensure retrieval respects access controls. Test for sensitive information disclosure. Train users on appropriate data input. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | OWASP LLM: LLM02, LLM06 \| NIST AI RMF: MANAGE 2.2 |

### LLM-03: Output Content Filtering

| | |
|---|---|
| **Control ID** | LLM-03 |
| **Control Name** | Output Content Filtering |
| **Description** | LLM outputs shall be filtered to prevent generation of harmful, inappropriate, or policy-violating content. |
| **Implementation Guidance** | Implement output filtering for: harmful content (violence, self-harm, illegal activities), inappropriate content for organizational context, hallucinated medical advice (for healthcare), policy violations. Use content moderation APIs or models. Implement domain-specific filters for healthcare context. Log filtered content for review. Balance filtering with usability. Test filter effectiveness. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | OWASP LLM: LLM02 \| NIST AI RMF: MANAGE 2.1 |

### LLM-04: Hallucination Mitigation

| | |
|---|---|
| **Control ID** | LLM-04 |
| **Control Name** | Hallucination Mitigation |
| **Description** | Controls shall be implemented to detect and mitigate LLM hallucinations, particularly for factual or clinical content. |
| **Implementation Guidance** | Implement mitigation strategies: RAG (Retrieval Augmented Generation) to ground responses in source documents, confidence scoring, citation requirements, fact-checking for critical content, user warnings about potential inaccuracy. For clinical content, require verification against authoritative sources. Train users to verify LLM outputs. Monitor for hallucination patterns. Do not use LLM outputs for clinical decisions without verification. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | OWASP LLM: LLM03 \| NIST AI RMF: MEASURE 2.3 |

### LLM-05: Rate Limiting and Abuse Prevention

| | |
|---|---|
| **Control ID** | LLM-05 |
| **Control Name** | Rate Limiting and Abuse Prevention |
| **Description** | LLM systems shall implement rate limiting and abuse detection to prevent resource exhaustion and misuse. |
| **Implementation Guidance** | Implement: per-user rate limits, token/cost limits, abuse detection for anomalous usage patterns, blocking mechanisms for abusive users. Monitor usage patterns. Set appropriate limits based on legitimate use cases. Implement cost controls for API-based LLMs. Alert on unusual usage spikes. Document rate limit configurations. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | OWASP LLM: LLM04 \| NIST AI RMF: MANAGE 2.2 |

### LLM-06: RAG Security

| | |
|---|---|
| **Control ID** | LLM-06 |
| **Control Name** | RAG Security |
| **Description** | Retrieval Augmented Generation (RAG) implementations shall include security controls for document ingestion, storage, and retrieval. |
| **Implementation Guidance** | Implement RAG security controls: validate and sanitize ingested documents, maintain access controls on source documents, implement retrieval authorization (users should only retrieve documents they're authorized to see), protect vector database, prevent injection via retrieved content. Monitor for attempts to access unauthorized documents. Document RAG architecture and security controls. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | OWASP LLM: LLM08 \| NIST AI RMF: MANAGE 2.2 |

### LLM-07: Plugin and Tool Security

| | |
|---|---|
| **Control ID** | LLM-07 |
| **Control Name** | Plugin and Tool Security |
| **Description** | LLM plugins, tools, and integrations shall be assessed and controlled to prevent unauthorized actions or data access. |
| **Implementation Guidance** | For LLMs with tool/plugin capabilities: inventory all plugins and integrations, assess security of each plugin, implement least privilege for plugin permissions, validate plugin inputs and outputs, monitor plugin usage, require approval for new plugins. Disable unnecessary plugins. Test for plugin-based attacks. Document approved plugins and their permissions. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | OWASP LLM: LLM07 \| NIST AI RMF: GOVERN 6.1 |

### LLM-08: Model Context Protocol Security

| | |
|---|---|
| **Control ID** | LLM-08 |
| **Control Name** | Model Context Protocol Security |
| **Description** | System prompts and model context shall be protected from disclosure and manipulation. |
| **Implementation Guidance** | Protect system prompts: store securely, version control, restrict access, monitor for disclosure. Implement defenses against prompt extraction attacks. Do not include secrets or sensitive information in system prompts. Test for prompt leakage vulnerabilities. Document system prompt management procedures. Review and update system prompts through change management. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: r |
| **Framework Mapping** | OWASP LLM: LLM01 \| NIST AI RMF: MANAGE 2.2 |

### LLM-09: Training Data Poisoning Prevention

| | |
|---|---|
| **Control ID** | LLM-09 |
| **Control Name** | Training Data Poisoning Prevention |
| **Description** | Controls shall prevent poisoning of training data used for fine-tuning or customizing LLMs. |
| **Implementation Guidance** | For fine-tuned LLMs: validate training data sources, implement data quality checks, restrict who can add training data, monitor for anomalous training data, implement rollback capability if poisoning detected. For third-party LLMs: understand vendor's training data practices, assess poisoning risks. Document training data sources and validation procedures. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: r, LOW: — |
| **Framework Mapping** | OWASP LLM: LLM03 \| NIST AI RMF: MAP 2.3 |

### LLM-10: LLM-Specific Monitoring

| | |
|---|---|
| **Control ID** | LLM-10 |
| **Control Name** | LLM-Specific Monitoring |
| **Description** | LLM systems shall be monitored for security events, abuse patterns, and operational anomalies specific to generative AI. |
| **Implementation Guidance** | Monitor for: prompt injection attempts, jailbreak attempts, unusual query patterns, sensitive data in inputs/outputs, content policy violations, cost/usage anomalies, performance degradation. Implement alerting for security events. Retain logs for investigation. Review monitoring data regularly. Integrate with security operations. Document monitoring configuration and thresholds. |
| **Risk Tier Applicability** | HIGH: R, MODERATE: R, LOW: R |
| **Framework Mapping** | OWASP LLM: LLM09 \| NIST AI RMF: MANAGE 3.1 |

---

## Appendix A: Control Applicability Matrix

| Control ID | Control Name | HIGH | MOD | LOW |
|------------|--------------|------|-----|-----|
| **GOV-01** | AI System Inventory | R | R | R |
| **GOV-02** | AI System Ownership | R | R | R |
| **GOV-03** | AI Governance Board Oversight | R | R | r |
| **GOV-04** | AI Risk Assessment Process | R | R | R |
| **GOV-05** | AI System Documentation | R | R | R |
| **GOV-06** | AI Training and Awareness | R | R | r |
| **GOV-07** | AI Ethics and Responsible Use | R | R | r |
| **GOV-08** | Regulatory Compliance Management | R | R | r |
| **DATA-01** | Training Data Provenance | R | R | r |
| **DATA-02** | Data Quality Assessment | R | R | r |
| **DATA-03** | Data Privacy and Consent | R | R | R |
| **DATA-04** | Data Classification and Handling | R | R | R |
| **DATA-05** | Data Retention and Disposal | R | R | r |
| **DATA-06** | Data Integrity Protection | R | R | R |
| **DATA-07** | Synthetic Data Governance | R | R | r |
| **DATA-08** | Data Bias Assessment | R | R | r |
| **MODEL-01** | Secure Model Development | R | R | r |
| **MODEL-02** | Model Documentation (Model Cards) | R | R | R |
| **MODEL-03** | Model Validation | R | R | R |
| **MODEL-04** | Bias and Fairness Testing | R | R | r |
| **MODEL-05** | Adversarial Robustness Testing | R | r | — |
| **MODEL-06** | Model Version Control | R | R | R |
| **MODEL-07** | Model Change Management | R | R | r |
| **MODEL-08** | Model Explainability | R | R | r |
| **MODEL-09** | Model Reproducibility | R | r | — |
| **MODEL-10** | Model Retirement | R | R | r |
| **OPS-01** | AI System Access Control | R | R | R |
| **OPS-02** | AI System Logging and Monitoring | R | R | R |
| **OPS-03** | Model Performance Monitoring | R | R | r |
| **OPS-04** | AI Incident Response | R | R | R |
| **OPS-05** | Human Override Capability | R | R | R |
| **OPS-06** | AI System Availability | R | R | r |
| **OPS-07** | AI Output Validation | R | R | r |
| **OPS-08** | AI System Hardening | R | R | R |
| **SUPPLY-01** | AI Vendor Assessment | R | R | R |
| **SUPPLY-02** | AI Vendor Contracts | R | R | R |
| **SUPPLY-03** | Third-Party Model Validation | R | R | r |
| **SUPPLY-04** | AI Dependency Management | R | R | R |
| **SUPPLY-05** | Pre-trained Model Security | R | R | r |
| **SUPPLY-06** | Vendor Update Management | R | R | r |
| **LLM-01** | Prompt Injection Prevention | R | R | R |
| **LLM-02** | Sensitive Information Protection | R | R | R |
| **LLM-03** | Output Content Filtering | R | R | R |
| **LLM-04** | Hallucination Mitigation | R | R | r |
| **LLM-05** | Rate Limiting and Abuse Prevention | R | R | R |
| **LLM-06** | RAG Security | R | R | r |
| **LLM-07** | Plugin and Tool Security | R | R | r |
| **LLM-08** | Model Context Protocol Security | R | R | r |
| **LLM-09** | Training Data Poisoning Prevention | R | r | — |
| **LLM-10** | LLM-Specific Monitoring | R | R | R |

**Legend:** R = Required, r = Recommended, — = Not Applicable

**Totals:** HIGH: 50 Required | MODERATE: 44 Required, 6 Recommended | LOW: 25 Required, 18 Recommended

---

## Appendix B: Framework Mapping

| Source Framework | Controls Mapped |
|------------------|-----------------|
| NIST AI RMF 1.0 | All 50 controls mapped to GOVERN, MAP, MEASURE, and MANAGE functions |
| ISO/IEC 42001:2023 | 45 controls mapped to Annex A control areas |
| OWASP LLM Top 10 (2025) | 10 LLM controls plus relevant controls in other domains |
| NIST CSF 2.0 | 35 controls mapped to CSF categories |

---

## Appendix C: Related Documents

| Document | Relationship |
|----------|--------------|
| Enterprise AI Governance Policy | Parent policy establishing governance requirements |
| AI Risk Assessment Framework | Risk tier determination for control applicability |
| AI System Documentation Standards | Documentation requirements for control evidence |
| AI Implementation Playbook | Step-by-step control implementation guidance (Section 4) |

---
