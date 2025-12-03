# AI System Documentation Standards

**[Organization Name]**

**Requirements for AI System Documentation Throughout the Lifecycle**

**Version 1.1**

**[Effective Date]**

---

| Field | Value |
|-------|-------|
| Document Owner | Chief Information Security Officer (CISO) |
| Classification | Internal Use - Confidential |
| Review Cycle | Annual |
| Parent Document | Enterprise AI Governance Policy |

---

## Table of Contents

1. Introduction
2. AI System Registration
3. Model Card / System Card Standards
4. Data Documentation Standards
5. Validation Documentation Standards
6. Security Documentation Standards
7. Operational Documentation Standards
8. Document Management and Version Control

---

## 1. Introduction

### 1.1 Purpose

This document establishes the minimum documentation requirements for AI systems throughout their lifecycle. Consistent, comprehensive documentation enables effective governance, supports regulatory compliance, facilitates knowledge transfer, and ensures AI systems can be properly monitored, maintained, and audited.

*For step-by-step procedures on how to complete governance activities that generate this documentation, refer to the AI Implementation Playbook.*

### 1.2 Scope

These standards apply to all AI systems subject to the Enterprise AI Governance Policy, including:

- Internally developed AI/ML models and applications
- Third-party AI systems and services
- LLM and generative AI applications
- AI components embedded in larger systems
- Clinical and non-clinical AI applications

### 1.3 Documentation Principles

| Principle | Description |
|-----------|-------------|
| **Completeness** | Documentation must cover all required elements for the system's risk tier |
| **Accuracy** | Documentation must reflect the current state of the system |
| **Accessibility** | Documentation must be stored in approved repositories and accessible to authorized stakeholders |
| **Traceability** | Changes must be versioned and traceable to specific system changes |
| **Proportionality** | Documentation depth should be proportionate to system risk |

### 1.4 Documentation Requirements by Risk Tier

| Documentation Type | HIGH | MODERATE | LOW |
|-------------------|------|----------|-----|
| AI System Registration | Required | Required | Required |
| Risk Assessment Report | Full | Full | Worksheet |
| Model Card / System Card | Full | Standard | Basic |
| Data Documentation | Full | Standard | Basic |
| Validation Report | Full | Summary | Checklist |
| Bias & Fairness Assessment | Required | Required | If applicable |
| Security Assessment | Full | Standard | Checklist |
| Operational Runbook | Full | Standard | Basic |
| Change Log | Required | Required | Required |

*Risk tier classification is determined using the AI Risk Assessment Framework. See that document for factor definitions, scoring methodology, and tier thresholds.*

---

## 2. AI System Registration

Every AI system must be registered in the organization's AI inventory. The registration record serves as the authoritative source for basic system information and links to all other documentation.

### 2.1 Required Registration Fields

| Field | Description | All Tiers |
|-------|-------------|-----------|
| System ID | Unique identifier (auto-generated) | Required |
| System Name | Descriptive name for the AI system | Required |
| System Owner | Accountable individual (name, title, department) | Required |
| Business Unit | Owning department or business unit | Required |
| Use Case Description | Brief description of what the system does | Required |
| AI Type | ML Model, LLM, GenAI, NLP, Computer Vision, etc. | Required |
| Deployment Type | Internal, Third-Party, Hybrid | Required |
| Risk Tier | HIGH, MODERATE, or LOW | Required |
| Status | Development, Testing, Production, Retired | Required |
| Production Date | Date deployed to production (if applicable) | Required |
| Data Classification | Highest data sensitivity level processed | Required |
| Clinical Use | Yes/No - Does system impact patient care? | Required |
| FDA Regulated | Yes/No/Under Review - SaMD determination | Required |
| Vendor Name | For third-party systems | If applicable |
| Next Review Date | Scheduled date for next risk reassessment | Required |

### 2.2 Documentation Links

The registration record must include links to all associated documentation:

- Risk Assessment Report
- Model Card / System Card
- Data Documentation
- Validation Report
- Security Assessment
- Operational Runbook
- Vendor Documentation (if third-party)
- Approval Records

### 2.3 Registration Maintenance

- Registration must be updated within 5 business days of any material change
- System Owner is responsible for maintaining accurate registration
- Security team audits registration accuracy quarterly
- Retired systems remain in inventory with 'Retired' status for audit purposes

---

## 3. Model Card / System Card Standards

A Model Card (for ML models) or System Card (for AI applications/services) provides standardized documentation of the AI system's purpose, capabilities, limitations, and performance characteristics. This is the primary technical documentation artifact for any AI system.

*For guidance on completing Model Cards as part of the AI system intake and approval process, see AI Implementation Playbook, Section 4 (MODEL domain controls).*

### 3.1 When to Use Model Card vs. System Card

| Document Type | Use When | Examples |
|---------------|----------|----------|
| **Model Card** | Documenting a specific ML model that you developed or have detailed technical knowledge of | Internally trained prediction model, custom NLP classifier, fine-tuned LLM |
| **System Card** | Documenting an AI application, service, or third-party system where you may not have full model details | Vendor AI application, LLM API integration, AI-enabled SaaS, multi-model system |

### 3.2 Model Card Template

The following sections are required for Model Cards. Depth of documentation varies by risk tier.

#### 3.2.1 Model Overview

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Model Name & Version | Unique identifier and version number | Req | Req |
| Model Type | Architecture (e.g., Random Forest, CNN, Transformer) | Req | Req |
| Development Date | When model was trained/developed | Req | Req |
| Developer/Team | Team or individuals who developed the model | Req | Req |
| Framework/Platform | ML framework used (TensorFlow, PyTorch, scikit-learn) | Req | Opt |

#### 3.2.2 Intended Use

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Primary Use Case | What the model is designed to do | Req | Req |
| Intended Users | Who will use the model outputs (e.g., clinicians, analysts) | Req | Req |
| Intended Population | Target population for predictions (if applicable) | Req | Req |
| Out-of-Scope Uses | Uses the model is NOT designed or validated for | Req | Req |
| Clinical Context | Clinical workflow integration (for clinical AI) | Req | If clinical |

#### 3.2.3 Training Data

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Data Sources | Where training data came from | Req | Req |
| Dataset Size | Number of samples, records, or data points | Req | Req |
| Date Range | Time period covered by training data | Req | Req |
| Demographics | Demographic breakdown of training population | Req | Req |
| Label Methodology | How ground truth labels were determined | Req | Opt |
| Data Preprocessing | Cleaning, transformation, feature engineering | Req | Opt |
| Known Limitations | Data gaps, biases, quality issues | Req | Req |

#### 3.2.4 Performance Metrics

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Primary Metrics | Key performance measures (accuracy, AUC, F1, etc.) | Req | Req |
| Confidence Intervals | Statistical confidence bounds for metrics | Req | Opt |
| Subgroup Performance | Performance broken down by demographic groups | Req | Req |
| Validation Dataset | Description of held-out validation data | Req | Req |
| Performance Thresholds | Minimum acceptable performance levels | Req | Opt |
| Failure Mode Analysis | When and how the model fails | Req | Opt |

#### 3.2.5 Ethical Considerations

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Bias Assessment | Bias testing methodology and results | Req | Req |
| Fairness Metrics | Quantitative fairness measures used | Req | Opt |
| Mitigation Steps | Actions taken to address identified biases | Req | If issues found |
| Residual Risks | Known ethical risks that remain | Req | Opt |

#### 3.2.6 Limitations and Caveats

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Technical Limitations | Known technical constraints or weaknesses | Req | Req |
| Generalization Limits | Populations or contexts where model may not generalize | Req | Req |
| Environmental Factors | External factors that may affect performance | Req | Opt |
| User Guidance | Recommendations for appropriate use | Req | Req |

### 3.3 System Card Template (for Third-Party / Multi-Component Systems)

System Cards include all applicable Model Card elements plus additional system-level documentation:

| Element | Description |
|---------|-------------|
| **Vendor Information** | Vendor name, contract reference, support contacts |
| **Product Version** | Current version deployed; version history |
| **Architecture Overview** | How AI components integrate with other system elements |
| **Data Flows** | What data goes to the AI system; what comes back |
| **Integration Points** | APIs, interfaces, dependencies on other systems |
| **Vendor Documentation** | Links to vendor-provided model cards, SOC 2 reports, certifications |
| **SLA/Support** | Availability SLAs, support tiers, escalation paths |
| **Update Notifications** | How vendor communicates model/system updates |

---

## 4. Data Documentation Standards

Comprehensive data documentation is essential for AI governance, enabling data quality assurance, bias detection, regulatory compliance, and reproducibility. This section defines requirements for documenting data used in AI systems.

### 4.1 Data Documentation Types

| Document Type | Purpose | When Required |
|---------------|---------|---------------|
| **Datasheet** | Comprehensive dataset documentation (similar to model card for data) | HIGH risk; internally developed models; clinical AI |
| **Data Dictionary** | Field-level documentation of data elements | All risk tiers with structured data |
| **Data Flow Diagram** | Visual representation of data movement | HIGH and MODERATE risk |
| **Data Lineage** | Traceability from source to model input | HIGH risk; regulated systems |
| **Privacy Impact Assessment** | Privacy risk analysis for data processing | Systems processing PII or PHI |

### 4.2 Datasheet Template

For HIGH risk systems and internally developed models, complete Datasheets following this structure:

#### 4.2.1 Dataset Identity

| Element | Description |
|---------|-------------|
| Dataset Name | Unique, descriptive name for the dataset |
| Version | Dataset version (use semantic versioning: MAJOR.MINOR.PATCH) |
| Creation Date | When the dataset was created or extracted |
| Data Owner | Individual or team responsible for the dataset |
| Data Steward | Individual responsible for data quality and maintenance |
| Associated AI Systems | List of AI systems that use this dataset |

#### 4.2.2 Dataset Composition

| Element | Description |
|---------|-------------|
| Instance Description | What does each record/row represent? (e.g., patient encounter, image, transaction) |
| Total Instances | Number of records/samples in the dataset |
| Feature Count | Number of variables/columns |
| Label/Target Variable | What is being predicted (for supervised learning) |
| Class Distribution | Distribution of target classes (for classification problems) |
| Missing Data | Percentage and pattern of missing values |
| Data Types | Types of data included (structured, text, images, time series) |

#### 4.2.3 Collection Process

| Element | Description |
|---------|-------------|
| Data Sources | Source systems, databases, or external providers |
| Collection Mechanism | How data was collected (API, manual entry, sensors, extraction) |
| Time Period | Date range of collected data |
| Sampling Strategy | How samples were selected (random, stratified, convenience) |
| Inclusion/Exclusion | Criteria for including or excluding records |
| Consent/Authorization | Legal basis for data use (consent, HIPAA authorization, legitimate interest) |

#### 4.2.4 Demographics and Representativeness

Document the demographic composition to enable bias assessment:

| Demographic Factor | Documentation Required |
|-------------------|----------------------|
| Age Distribution | Age ranges and percentages; note any underrepresented groups |
| Sex/Gender | Distribution by sex/gender categories |
| Race/Ethnicity | Distribution by race/ethnicity; note collection methodology |
| Geographic Distribution | Geographic regions represented; urban/rural mix |
| Socioeconomic Factors | Insurance type, income proxies if available and relevant |
| Clinical Factors | Disease severity, comorbidities, care settings (for clinical data) |
| Known Gaps | Populations known to be underrepresented or excluded |

### 4.3 Data Dictionary Requirements

All AI systems must maintain a data dictionary with the following fields for each variable:

| Field | Description |
|-------|-------------|
| **Variable Name** | Technical name as used in the system |
| **Business Name** | Human-readable descriptive name |
| **Definition** | Clear definition of what the variable represents |
| **Data Type** | Integer, float, string, boolean, date, etc. |
| **Valid Values** | Range, enumerated values, or format constraints |
| **Source** | Where the data originates |
| **Sensitivity** | Data classification (PHI, PII, Confidential, Public) |
| **Transformations** | Any transformations applied (encoding, normalization, derivation logic) |

---

## 5. Validation Documentation Standards

Validation documentation provides evidence that an AI system performs as intended and meets quality standards. The depth of validation documentation scales with risk tier.

*Validation activities are conducted as part of the implementation process. See AI Implementation Playbook, Section 3 for risk assessment execution and Section 4 for MODEL domain control implementation.*

### 5.1 Validation Report Structure

#### 5.1.1 Executive Summary

- System identification and version
- Validation scope and objectives
- Overall pass/fail determination
- Key findings and recommendations
- Approval signatures

#### 5.1.2 Validation Methodology

| Element | Description |
|---------|-------------|
| Validation Approach | Retrospective, prospective, or hybrid validation |
| Validation Dataset | Description of held-out test data; how it was isolated from training |
| Performance Metrics | Metrics used to evaluate performance (with justification) |
| Success Criteria | Pre-defined thresholds for acceptable performance |
| Statistical Methods | Statistical tests and confidence level used |
| Validation Environment | Environment where validation was conducted |

#### 5.1.3 Results Documentation

| Element | Description | HIGH | MOD |
|---------|-------------|------|-----|
| Overall Metrics | Primary performance metrics with confidence intervals | Req | Req |
| Confusion Matrix | For classification: TP, TN, FP, FN | Req | Req |
| ROC/AUC Analysis | ROC curve and AUC with threshold analysis | Req | Opt |
| Subgroup Analysis | Performance by demographic subgroups | Req | Req |
| Error Analysis | Characterization of failure cases | Req | Opt |
| Calibration Analysis | How well predicted probabilities match observed rates | Req | Opt |

### 5.2 Bias and Fairness Testing Documentation

| Element | Documentation Required |
|---------|----------------------|
| **Protected Attributes** | Which protected characteristics were tested (age, sex, race, etc.) |
| **Fairness Metrics** | Metrics used (demographic parity, equalized odds, predictive parity) |
| **Disparity Thresholds** | Acceptable disparity levels (e.g., 80% rule, statistical significance) |
| **Test Results** | Performance metrics for each subgroup; identified disparities |
| **Mitigation Actions** | Steps taken to address identified disparities |
| **Residual Disparities** | Disparities that remain after mitigation; justification for acceptance |
| **Monitoring Plan** | How fairness will be monitored in production |

### 5.3 Clinical Validation Requirements

Clinical AI systems require additional validation documentation:

| Element | Description |
|---------|-------------|
| **Clinical Study Protocol** | Formal protocol for clinical validation study (for HIGH risk) |
| **IRB Approval** | IRB determination or approval documentation (if research) |
| **Reference Standard** | Gold standard used for comparison; how it was determined |
| **Clinical Endpoints** | Clinical outcomes measured; follow-up period |
| **Expert Review** | Clinical SME review and sign-off; adjudication process |
| **External Validation** | Validation at external site(s) for HIGH risk clinical AI |
| **Clinical Champion Sign-off** | Attestation from clinical champion that system is fit for clinical use |

### 5.4 Validation Documentation by Risk Tier

| Validation Element | HIGH | MODERATE | LOW |
|-------------------|------|----------|-----|
| Formal validation report | Full report | Summary report | Checklist |
| Independent validation dataset | Required | Required | Recommended |
| Subgroup performance analysis | Required | Required | If applicable |
| External site validation | Clinical AI: Req | Not required | Not required |
| Prospective pilot | Required | Recommended | Optional |
| Clinical champion sign-off | Required | If clinical | Not required |

---

## 6. Security Documentation Standards

Security documentation provides evidence of control implementation and enables ongoing security management. This section defines documentation requirements for AI-specific security controls.

*See AI Security Controls Catalog for complete control definitions and risk-tier applicability.*

### 6.1 Security Assessment Report

All AI systems require a security assessment. Report depth varies by risk tier:

#### 6.1.1 Report Structure

| Section | Content | HIGH | MOD |
|---------|---------|------|-----|
| Executive Summary | Overall risk posture, key findings, recommendations | Req | Req |
| System Description | Architecture, components, data flows, integrations | Req | Req |
| Threat Assessment | AI-specific threats identified and assessed | Req | Req |
| Control Assessment | Status of each applicable control from AI Security Controls Catalog | Req | Req |
| Vulnerability Assessment | Results of vulnerability scanning and testing | Req | Opt |
| Penetration Testing | Results of adversarial/penetration testing | Req | Opt |
| Risk Register | Identified risks with ratings and mitigation status | Req | Req |
| Remediation Plan | Plan to address identified gaps with timelines | Req | If gaps |

### 6.2 AI-Specific Threat Documentation

Document assessment of the following AI-specific threat categories:

| Threat Category | Examples | Document |
|-----------------|----------|----------|
| **Data Poisoning** | Malicious training data, label manipulation | Risk level, controls in place |
| **Model Extraction** | Model stealing via API queries | Risk level, controls in place |
| **Model Inversion** | Inferring training data from model outputs | Risk level, controls in place |
| **Adversarial Inputs** | Crafted inputs to cause misclassification | Risk level, controls in place |
| **Prompt Injection** | Malicious prompts to manipulate LLM behavior | Risk level, controls in place |
| **Supply Chain** | Compromised pre-trained models, libraries | Risk level, controls in place |

### 6.3 Control Implementation Evidence

For each implemented control, document:

| Element | Description |
|---------|-------------|
| **Control ID** | Reference to AI Security Controls Catalog control identifier (e.g., GOV-01, DATA-03). See AI Security Controls Catalog for complete control definitions and risk-tier applicability. |
| **Implementation Status** | Implemented, Partially Implemented, Planned, Not Applicable |
| **Implementation Description** | How the control is implemented for this specific system |
| **Evidence Reference** | Link to evidence (screenshots, configs, test results, policies) |
| **Control Owner** | Individual responsible for maintaining the control |
| **Last Validated** | Date control was last tested or validated |
| **Gaps/Exceptions** | Any gaps, exceptions, or compensating controls |

### 6.4 LLM-Specific Security Documentation

For LLM and generative AI systems, document additional security elements:

| Element | Documentation Required |
|---------|----------------------|
| **System Prompt** | Copy of system prompt (stored securely); change history |
| **Input Validation** | Input filtering rules, length limits, sanitization approach |
| **Output Filtering** | Output moderation rules, PII/PHI detection, content filtering |
| **Prompt Injection Defenses** | Specific defenses implemented; testing results |
| **RAG Security** | If RAG: document ingestion controls, vector DB security, retrieval permissions |
| **Rate Limiting** | Rate limits configured; abuse detection thresholds |
| **Logging Configuration** | What is logged (prompts, responses, metadata); retention period |

---

## 7. Operational Documentation Standards

Operational documentation enables effective day-to-day management, monitoring, and maintenance of AI systems. This section defines requirements for runbooks, monitoring specifications, and change documentation.

### 7.1 Operational Runbook

Every AI system in production requires an operational runbook containing:

#### 7.1.1 System Overview

- System name, ID, and current version
- Brief functional description
- Architecture diagram (simplified)
- Key dependencies and integration points
- Risk tier and clinical use status

#### 7.1.2 Contact Information

| Role | Responsibilities | Contact Info Required |
|------|------------------|----------------------|
| System Owner | Overall accountability; escalation point | Name, email, phone, backup contact |
| Technical Lead | Technical issues; model performance | Name, email, phone, backup contact |
| Operations Support | Day-to-day operations; first-line support | Team distribution list, on-call schedule |
| Clinical Champion | Clinical issues (for clinical AI) | Name, email, phone, backup contact |
| Vendor Support | Third-party system issues | Support portal, phone, SLA tier |

#### 7.1.3 Monitoring and Alerting

| Element | Documentation Required |
|---------|----------------------|
| **Monitoring Tools** | Tools used for monitoring; dashboard locations |
| **Key Metrics** | Metrics monitored (performance, drift, latency, errors) |
| **Alert Thresholds** | Warning and critical thresholds for each metric |
| **Alert Routing** | Who receives alerts; escalation paths |
| **Response Procedures** | What to do when each alert fires |

#### 7.1.4 Standard Operating Procedures

| Procedure | Content |
|-----------|---------|
| **Startup/Shutdown** | Steps to start and stop the system; order of operations |
| **Health Checks** | How to verify system is operating normally |
| **Backup/Recovery** | Backup schedule; recovery procedures; RTO/RPO |
| **Log Management** | Log locations; retention; how to access for troubleshooting |
| **Performance Tuning** | Adjustable parameters; tuning guidance |

#### 7.1.5 Incident Response Procedures

| Element | Documentation Required |
|---------|----------------------|
| **Kill Switch** | How to immediately disable AI functionality; who can authorize |
| **Fallback Process** | Manual/alternative process when AI is unavailable |
| **Escalation Path** | Escalation matrix by severity; contact information |
| **Communication Templates** | Templates for user notification during outages/issues |
| **Rollback Procedure** | How to revert to previous model version if needed |

### 7.2 Change Documentation

All changes to AI systems must be documented in the change log:

#### 7.2.1 Change Log Requirements

| Field | Description |
|-------|-------------|
| **Change ID** | Unique identifier; link to change ticket |
| **Date** | Date change was implemented |
| **Version** | New version number after change |
| **Change Type** | Model update, config change, retraining, bug fix, feature addition |
| **Description** | What was changed and why |
| **Impact Assessment** | Expected impact; any performance changes |
| **Testing Performed** | Validation/testing completed before deployment |
| **Approved By** | Approver name per approval authority requirements |
| **Implemented By** | Individual who implemented the change |

#### 7.2.2 Change Types Requiring Documentation

- Model retraining (any retraining, even on same data)
- Training data changes (new data sources, data refresh)
- Feature changes (new features, feature removal)
- Threshold adjustments (decision thresholds, alert thresholds)
- Configuration changes (parameters, settings)
- Infrastructure changes (platform, hosting, dependencies)
- Integration changes (new integrations, API changes)
- Vendor updates (for third-party AI systems)

### 7.3 Runbook Requirements by Risk Tier

| Runbook Element | HIGH | MODERATE | LOW |
|-----------------|------|----------|-----|
| System overview | Full | Full | Basic |
| Contact information | Full | Full | Owner only |
| Monitoring specification | Detailed | Standard | Basic |
| Standard operating procedures | Full | Key procedures | Basic |
| Incident response procedures | Detailed | Standard | Kill switch only |
| Change log | Required | Required | Required |

---

## 8. Document Management and Version Control

This section establishes requirements for managing AI documentation throughout the system lifecycle, including version control, storage, retention, and access management.

### 8.1 Version Control Requirements

#### 8.1.1 Versioning Scheme

All AI documentation must use semantic versioning (MAJOR.MINOR.PATCH):

| Component | When to Increment | Examples |
|-----------|-------------------|----------|
| **MAJOR** | Significant changes to system, retraining with new architecture, major scope changes | 1.0.0 → 2.0.0: Model architecture change, new use case |
| **MINOR** | Retraining with new data, feature additions, performance improvements | 1.0.0 → 1.1.0: New training data, added feature |
| **PATCH** | Bug fixes, documentation updates, configuration tweaks | 1.0.0 → 1.0.1: Threshold adjustment, typo fix |

#### 8.1.2 Document Version Tracking

Each document must include version control metadata:

| Field | Description |
|-------|-------------|
| **Version Number** | Current version using semantic versioning |
| **Effective Date** | Date this version became effective |
| **Author** | Individual who made the changes |
| **Reviewer** | Individual who reviewed the changes |
| **Approver** | Individual who approved the changes |
| **Change Summary** | Brief description of what changed |

### 8.2 Document Storage

#### 8.2.1 Approved Repositories

| Document Type | Primary Repository | Requirements |
|---------------|-------------------|--------------|
| AI System Registration | AI Inventory System / CMDB | Single source of truth; audit trail |
| Model Cards / System Cards | AI Governance SharePoint / Wiki | Version control; access controls |
| Code and Model Artifacts | Git Repository / MLflow | Git version control; CI/CD integration |
| Training Data Documentation | Data Catalog / SharePoint | Linked to data governance |
| Security Assessments | GRC Platform / Secure SharePoint | Restricted access; encryption |
| Operational Runbooks | IT Service Management / Wiki | Operations team access |
| Vendor Documentation | Vendor Management System | Linked to contract records |

#### 8.2.2 Storage Requirements

- All documentation must be stored in approved, organization-managed repositories
- Local copies on individual workstations are not acceptable as primary storage
- Repositories must support version history and audit trails
- Backup and disaster recovery must be in place per organizational standards
- Sensitive documentation (security assessments, PHI-related) requires encryption at rest

### 8.3 Document Retention

| Document Type | Retention Period | Notes |
|---------------|------------------|-------|
| AI System Registration | Life of system + 7 years | Retain for audit and legal purposes |
| Model Cards (all versions) | Life of system + 7 years | All versions retained; audit trail |
| Risk Assessments | Life of system + 7 years | All versions retained |
| Validation Reports | Life of system + 7 years | Evidence of validation |
| Training Data Documentation | Life of system + 7 years | Data provenance records |
| Security Assessments | Life of system + 7 years | Compliance evidence |
| Change Logs | Life of system + 7 years | Complete change history |
| Incident Reports | Life of system + 7 years | Legal and regulatory requirements |
| FDA-Regulated System Docs | Per FDA requirements | Consult Regulatory Affairs; typically life + 2 years |

### 8.4 Access Control

| Principle | Requirement |
|-----------|-------------|
| **Least Privilege** | Access granted based on role and need; not everyone needs access to all documentation |
| **Role-Based Access** | Define access by role (System Owner, Developer, Operations, Security, Auditor) |
| **Sensitive Documents** | Security assessments, vulnerability details restricted to Security team and System Owner |
| **External Access** | Third parties (auditors, regulators) granted time-limited, logged access as needed |
| **Access Reviews** | Quarterly review of access permissions; remove access when no longer needed |

### 8.5 Documentation Review Cycle

| Document Type | HIGH | MODERATE | LOW |
|---------------|------|----------|-----|
| Model Card / System Card | Semi-annual | Annual | Every 2 years |
| Risk Assessment | Semi-annual | Annual | Every 2 years |
| Security Assessment | Annual | Annual | Every 2 years |
| Operational Runbook | Annual | Annual | Annual |
| Data Documentation | Annual | Annual | Every 2 years |

**Note:** Documentation must also be updated whenever material changes occur to the system, regardless of review cycle.

### 8.6 Documentation Completeness Checklist

Use this checklist to verify documentation completeness before deployment approval:

| Documentation Item | HIGH | MOD | LOW |
|--------------------|------|-----|-----|
| AI System Registration complete | ☐ | ☐ | ☐ |
| Risk Assessment complete and approved | ☐ | ☐ | ☐ |
| Model Card / System Card complete | ☐ | ☐ | ☐ |
| Data documentation (Datasheet / Data Dictionary) | ☐ | ☐ | ☐ |
| Validation Report complete | ☐ | ☐ | ☐ |
| Bias and Fairness Assessment complete | ☐ | ☐ | N/A |
| Security Assessment complete | ☐ | ☐ | ☐ |
| Control Implementation Evidence documented | ☐ | ☐ | ☐ |
| Operational Runbook complete | ☐ | ☐ | ☐ |
| Clinical Champion sign-off (if clinical) | ☐ | ☐ | N/A |
| All documents stored in approved repositories | ☐ | ☐ | ☐ |
| Links updated in AI System Registration | ☐ | ☐ | ☐ |

---

## Appendix: Related Documents

| Document | Relationship |
|----------|--------------|
| Enterprise AI Governance Policy | Parent policy establishing governance requirements |
| AI Risk Assessment Framework | Risk tier determination methodology |
| AI Security Controls Catalog | Control definitions for security documentation |
| AI Implementation Playbook | Step-by-step procedures for governance activities |

---
