# AI Risk Assessment Framework

**[Organization Name]**

**Version 1.1**

**[Effective Date]**

---

| Field | Value |
|-------|-------|
| Document Owner | [Chief Information Security Officer] |
| Parent Policy | Enterprise AI Governance Policy |
| Review Cycle | Annual |

---

## Table of Contents

1. Introduction
2. Risk Assessment Process Overview
3. Risk Factor Definitions
4. Risk Tier Classification
5. Healthcare-Specific Considerations
6. AI Impact Assessment
7. Assessment Documentation
8. Appendices

---

## 1. Introduction

### 1.1 Purpose

This framework establishes the methodology for assessing and classifying risks associated with AI systems at [Organization Name]. It provides a structured, repeatable process for evaluating AI use cases against defined risk factors to determine appropriate governance controls, approval requirements, and ongoing monitoring obligations.

*For step-by-step guidance on executing risk assessments, including worked examples and common pitfalls, refer to the AI Implementation Playbook, Section 3: Risk Assessment Execution Guide.*

### 1.2 Scope

This framework applies to all AI systems subject to the Enterprise AI Governance Policy, including:

- Internally developed AI/ML models and applications
- Third-party AI products and services
- AI features embedded in enterprise software platforms
- Generative AI and large language model applications
- AI-enabled automation and decision support systems

### 1.3 Framework Alignment

This risk assessment methodology aligns with:

- **NIST AI Risk Management Framework (AI RMF)** – Map function
- **ISO/IEC 42001 Annex C** – Risk sources
- **EU AI Act** – Risk classification principles

The approach enables proportionate control application while maintaining flexibility for healthcare-specific considerations.

---

## 2. Risk Assessment Process Overview

### 2.1 Process Stages

The AI risk assessment process consists of five sequential stages:

| Stage | Activity | Description |
|-------|----------|-------------|
| 1 | Intake | AI system registration and initial use case documentation |
| 2 | Factor Assessment | Evaluation of the AI system against defined risk factors |
| 3 | Risk Scoring | Calculation of composite risk score and tier assignment |
| 4 | Control Mapping | Identification of applicable security and governance controls |
| 5 | Approval | Review and approval per risk tier requirements |

Control mapping is performed using the **AI Security Controls Catalog**, which defines 50 controls across six domains with risk-tier applicability designations.

### 2.2 Assessment Triggers

A formal AI risk assessment is required when:

- A new AI system is proposed for development or acquisition
- An existing AI system's intended use significantly changes
- An AI system is retrained with substantially different data
- A third-party AI vendor makes material changes to their system
- Regulatory requirements change affecting AI system classification
- An AI incident occurs that warrants reassessment

### 2.3 Roles in the Assessment Process

| Role | Responsibility |
|------|---------------|
| Requestor | Initiates assessment request; provides use case documentation and business justification |
| AI System Owner | Accountable for assessment accuracy; coordinates with stakeholders; implements required controls |
| Security Reviewer | Validates risk factor scoring; identifies security control requirements |
| Privacy Officer | Assesses data sensitivity factors; ensures privacy compliance |
| Clinical Reviewer | Evaluates clinical impact factors for patient care AI applications |
| AI Governance Board | Final approval authority for HIGH risk AI systems; reviews escalated assessments |

---

## 3. Risk Factor Definitions

Each AI system shall be evaluated against six risk factors. Each factor is scored on a scale of 1 (Low) to 3 (High). The weighted composite score determines the overall risk tier classification.

### 3.1 Factor 1: Patient/Clinical Impact (Weight: 25%)

Evaluates the potential for the AI system to affect patient health, safety, or clinical outcomes.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | No Clinical Impact | System has no direct or indirect effect on patient care, clinical decisions, or health outcomes |
| 2 | Indirect Clinical Impact | System supports clinical workflows but does not directly influence clinical decisions; errors could cause delays or inefficiencies |
| 3 | Direct Clinical Impact | System directly influences diagnosis, treatment, or clinical decisions; errors could result in patient harm |

### 3.2 Factor 2: Data Sensitivity (Weight: 20%)

Evaluates the sensitivity and regulatory classification of data processed by the AI system.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | Non-Sensitive | Public or non-confidential data only; no PII, PHI, or proprietary information |
| 2 | Confidential/PII | Internal confidential data, limited PII, or de-identified health information |
| 3 | PHI/Highly Sensitive | Protected Health Information (PHI), sensitive PII, mental health, substance abuse, or genetic data |

### 3.3 Factor 3: Autonomy Level (Weight: 20%)

Evaluates the degree of human oversight and intervention in AI system operations and decisions.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | Human-in-the-Loop | Human review and approval required for all AI outputs before action is taken |
| 2 | Human-on-the-Loop | AI operates with human oversight; humans can intervene but do not approve each action |
| 3 | Autonomous | AI operates independently; human intervention is reactive or after-the-fact only |

### 3.4 Factor 4: Scale and Scope (Weight: 15%)

Evaluates the breadth of impact based on the number of users, patients, or decisions affected.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | Limited | Single department or function; fewer than 100 users or patients affected |
| 2 | Moderate | Multiple departments or facilities; 100-10,000 users or patients affected |
| 3 | Enterprise-Wide | Organization-wide deployment; more than 10,000 users or patients affected |

### 3.5 Factor 5: Reversibility (Weight: 10%)

Evaluates whether decisions or actions taken based on AI outputs can be reversed or corrected.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | Easily Reversible | Actions can be easily undone with minimal impact; no lasting consequences |
| 2 | Partially Reversible | Reversal possible but requires effort, cost, or time; some residual impact may remain |
| 3 | Irreversible | Actions cannot be undone; permanent consequences including potential patient harm |

### 3.6 Factor 6: Regulatory Exposure (Weight: 10%)

Evaluates the regulatory and compliance implications of the AI system.

| Score | Level | Criteria |
|-------|-------|----------|
| 1 | Minimal | No specific regulatory requirements apply; standard IT governance sufficient |
| 2 | Moderate | Subject to HIPAA, state privacy laws, or industry standards; documentation requirements apply |
| 3 | High | FDA-regulated, clinical trial implications, or potential medical device classification; significant penalties for non-compliance |

### 3.7 Risk Factor Weighting Summary

| Risk Factor | Weight | Max Contribution |
|-------------|--------|------------------|
| Patient/Clinical Impact | 25% | 0.75 |
| Data Sensitivity | 20% | 0.60 |
| Autonomy Level | 20% | 0.60 |
| Scale and Scope | 15% | 0.45 |
| Reversibility | 10% | 0.30 |
| Regulatory Exposure | 10% | 0.30 |
| **Total** | **100%** | **3.00** |

---

## 4. Risk Tier Classification

### 4.1 Scoring Methodology

The composite risk score is calculated by multiplying each factor's raw score (1-3) by its weight, then summing the weighted scores:

**Composite Score = Σ (Factor Score × Factor Weight)**

The minimum possible score is 1.00 (all factors scored as 1), and the maximum possible score is 3.00 (all factors scored as 3).

#### 4.1.1 Scoring Example

**Example:** Clinical documentation AI assistant that summarizes patient notes for physician review.

| Factor | Score | Weight | Weighted Score |
|--------|-------|--------|----------------|
| Patient/Clinical Impact | 2 | 25% | 0.50 |
| Data Sensitivity | 3 | 20% | 0.60 |
| Autonomy Level | 1 | 20% | 0.20 |
| Scale and Scope | 2 | 15% | 0.30 |
| Reversibility | 1 | 10% | 0.10 |
| Regulatory Exposure | 2 | 10% | 0.20 |
| **Composite Score** | | | **1.90 (MODERATE)** |

### 4.2 Risk Tier Thresholds

Based on the composite score, AI systems are classified into one of three risk tiers:

| Risk Tier | Score Range | Description |
|-----------|-------------|-------------|
| **HIGH** | 2.20 - 3.00 | Significant potential for patient harm, regulatory exposure, or organizational risk; requires full governance review and ongoing monitoring |
| **MODERATE** | 1.50 - 2.19 | Moderate risk requiring documented controls and periodic review; standard security and compliance measures with enhanced documentation |
| **LOW** | 1.00 - 1.49 | Minimal risk; standard IT governance applies; streamlined approval process with basic documentation requirements |

#### 4.2.1 Automatic Escalation Rules

Regardless of composite score, an AI system is **automatically classified as HIGH risk** if any of the following conditions exist:

- Patient/Clinical Impact factor is scored as 3 (Direct Clinical Impact)
- Autonomy Level factor is scored as 3 (Autonomous) AND the system processes PHI
- Regulatory Exposure factor is scored as 3 (FDA-regulated or medical device)
- The AI system is used for clinical diagnosis, treatment recommendations, or patient risk prediction

### 4.3 Tier-Specific Requirements

#### 4.3.1 HIGH Risk AI Systems

| Requirement Category | Requirements |
|---------------------|--------------|
| Approval Authority | AI Governance Board approval required |
| Documentation | Full AI system documentation per **AI System Documentation Standards**, including model cards, training data provenance, validation results, and bias assessment |
| Security Controls | Full **AI Security Controls Catalog** implementation; penetration testing; adversarial robustness testing |
| Clinical Validation | Clinical review and validation required for patient-care applications; CMO or designee sign-off |
| Monitoring | Continuous performance monitoring; monthly drift analysis; quarterly bias reassessment |
| Review Cycle | Full reassessment every 6 months or upon significant change |
| Incident Response | Dedicated incident response procedures; immediate escalation path; 24-hour notification requirement |

#### 4.3.2 MODERATE Risk AI Systems

| Requirement Category | Requirements |
|---------------------|--------------|
| Approval Authority | CISO and System Owner approval; Privacy Officer review if PHI involved |
| Documentation | Standard AI documentation package per **AI System Documentation Standards**; use case description; data flow diagrams; control implementation evidence |
| Security Controls | Core **AI Security Controls Catalog** implementation; vulnerability scanning; access control verification |
| Monitoring | Performance monitoring; quarterly drift analysis; annual bias reassessment |
| Review Cycle | Annual reassessment or upon significant change |

#### 4.3.3 LOW Risk AI Systems

| Requirement Category | Requirements |
|---------------------|--------------|
| Approval Authority | System Owner approval with notification to AI Governance Board |
| Documentation | Basic use case registration per **AI System Documentation Standards**; system description; data classification confirmation |
| Security Controls | Standard IT security controls; baseline access management |
| Monitoring | Standard application monitoring; annual performance review |
| Review Cycle | Reassessment every 2 years or upon significant change |

---

## 5. Healthcare-Specific Considerations

Given the organization's focus on patient care, AI systems in healthcare contexts require additional evaluation criteria beyond the standard risk factors.

### 5.1 Clinical AI Categories

AI systems used in clinical contexts are further categorized based on their role in patient care:

| Category | Description | Examples |
|----------|-------------|----------|
| **Diagnostic AI** | AI that identifies, detects, or predicts medical conditions | Radiology image analysis; pathology detection; sepsis prediction; deterioration alerts |
| **Treatment AI** | AI that recommends or guides therapeutic interventions | Drug dosing recommendations; treatment protocol suggestions; care pathway optimization |
| **Clinical Workflow AI** | AI that supports clinical operations without direct patient decisions | Clinical documentation; scheduling optimization; order set suggestions; chart abstraction |
| **Administrative AI** | AI supporting non-clinical healthcare operations | Revenue cycle; claims processing; supply chain; facility management |

### 5.2 Patient Safety Considerations

For **Diagnostic AI** and **Treatment AI** categories, the following additional safety considerations must be evaluated:

- **Clinical Validation Evidence:** Has the AI system been validated on patient populations similar to those it will serve? Are validation results published or available for review?
- **Failure Mode Analysis:** What happens when the AI system fails or produces incorrect outputs? Are there safeguards to prevent patient harm from AI errors?
- **Alert Fatigue Risk:** Could the AI system generate excessive alerts that lead clinicians to ignore important warnings?
- **Automation Bias:** Is there risk that clinicians will over-rely on AI recommendations and fail to apply independent clinical judgment?
- **Health Equity Impact:** Has the AI been tested for performance disparities across demographic groups, including race, ethnicity, age, and socioeconomic status?
- **Clinical Workflow Integration:** How does the AI integrate into existing clinical workflows? Does it create friction or enable appropriate human oversight?

### 5.3 Regulatory Considerations for Clinical AI

Clinical AI systems may be subject to additional regulatory requirements:

| Regulatory Area | Considerations |
|----------------|----------------|
| **FDA Regulation** | AI/ML-based Software as a Medical Device (SaMD) may require FDA clearance or approval. Consult with Regulatory Affairs for AI systems that diagnose, treat, or prevent disease. |
| **CDS Exclusion Criteria** | Clinical Decision Support may be exempt from FDA regulation if it meets specific criteria (displays source, presents basis, allows clinician to review). Document CDS exclusion analysis. |
| **HIPAA Compliance** | AI systems processing PHI must comply with HIPAA Security Rule requirements. Business Associate Agreements required for third-party AI vendors. |
| **State Regulations** | Some states have enacted AI-specific healthcare regulations. Review applicable state requirements for AI in clinical settings. |
| **Accreditation Standards** | Joint Commission and other accrediting bodies may have standards applicable to AI use in clinical settings. Review current accreditation requirements. |

*For detailed guidance on clinical AI implementation and FDA pathways, refer to the AI Implementation Playbook, Section 8: Clinical AI Implementation.*

---

## 6. AI Impact Assessment

For HIGH risk AI systems and any AI system that may significantly affect individuals or groups, an AI Impact Assessment (AIIA) shall be conducted in addition to the standard risk assessment.

### 6.1 When an AI Impact Assessment is Required

An AIIA is required when any of the following conditions apply:

- The AI system is classified as HIGH risk
- The AI system makes or materially influences decisions about individuals
- The AI system processes sensitive categories of data (health, biometric, genetic)
- The AI system may have differential impacts on protected groups
- The AI Governance Board requests an AIIA based on specific concerns

### 6.2 AI Impact Assessment Components

The AIIA shall address the following areas:

#### 6.2.1 Purpose and Necessity

- What problem is the AI system intended to solve?
- Why is AI the appropriate solution compared to alternatives?
- What are the expected benefits and for whom?

#### 6.2.2 Data and Model Assessment

- What data was used to train or develop the AI system?
- Is the training data representative of the population the AI will serve?
- What are the known limitations of the model?
- How was the model validated and what were the results?

#### 6.2.3 Fairness and Bias Evaluation

- Has the AI been tested for bias across demographic groups?
- What fairness metrics were used and what were the results?
- Are there known performance disparities and how are they addressed?
- What ongoing bias monitoring is planned?

#### 6.2.4 Human Rights and Dignity

- Could the AI system affect individual rights or dignity?
- Are there adequate mechanisms for individuals to contest AI decisions?
- How is informed consent addressed where applicable?

#### 6.2.5 Transparency and Explainability

- Can the AI system's decisions be explained to affected individuals?
- What level of explainability is appropriate for this use case?
- How will users be informed that AI is being used?

#### 6.2.6 Risk Mitigation Measures

- What safeguards are in place to prevent or mitigate identified risks?
- What human oversight mechanisms exist?
- What is the process for handling AI errors or failures?
- Are there residual risks that must be accepted?

### 6.3 AIIA Review and Approval

Completed AI Impact Assessments shall be reviewed by:

- Privacy Officer (for privacy-related impacts)
- Clinical Leadership (for patient care impacts)
- Legal (for regulatory and liability considerations)
- AI Governance Board (for HIGH risk systems)

---

## 7. Assessment Documentation

### 7.1 Required Documentation

All risk assessments shall be documented using the standard AI Risk Assessment template, which includes:

- System identification and description
- Assessment date and assessor information
- Factor-by-factor scoring with rationale
- Composite score calculation
- Risk tier assignment
- Applicable controls from the AI Security Controls Catalog
- Approval signatures

*Documentation requirements for risk assessments are specified in the AI System Documentation Standards.*

### 7.2 Documentation Retention

Risk assessment documentation shall be retained for:

- The operational life of the AI system, plus
- Seven (7) years following system retirement

### 7.3 Assessment Updates

Risk assessments shall be updated:

| Risk Tier | Regular Review Cycle | Additional Triggers |
|-----------|---------------------|---------------------|
| HIGH | Every 6 months | Any material change; incident; regulatory change |
| MODERATE | Annually | Significant change; incident |
| LOW | Every 2 years | Major change |

---

## 8. Appendices

### Appendix A: Risk Assessment Worksheet

*See AI Implementation Playbook, Section 11: Templates and Tools for the fillable Risk Assessment Worksheet.*

### Appendix B: Scoring Quick Reference

| Factor | Weight | Score 1 | Score 2 | Score 3 |
|--------|--------|---------|---------|---------|
| Patient/Clinical Impact | 25% | No clinical impact | Indirect clinical impact | Direct clinical impact |
| Data Sensitivity | 20% | Non-sensitive | Confidential/PII | PHI/Highly sensitive |
| Autonomy Level | 20% | Human-in-the-loop | Human-on-the-loop | Autonomous |
| Scale and Scope | 15% | <100 affected | 100-10,000 | >10,000 |
| Reversibility | 10% | Easily reversible | Partial | Irreversible |
| Regulatory Exposure | 10% | Standard IT | HIPAA/Privacy | FDA/Medical device |

**Tier Thresholds:** HIGH = 2.20-3.00 | MODERATE = 1.50-2.19 | LOW = 1.00-1.49

### Appendix C: Related Documents

| Document | Relationship |
|----------|--------------|
| Enterprise AI Governance Policy | Parent policy establishing governance requirements |
| AI Security Controls Catalog | Control selection based on risk tier |
| AI System Documentation Standards | Documentation requirements by risk tier |
| AI Implementation Playbook | Step-by-step execution guidance |

---
