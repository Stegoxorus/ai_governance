# AI Implementation Playbook

**[Organization Name]**

**Practical Guidance for AI Governance Execution**

**Version 1.1**

**[Effective Date]**

---

| Field | Value |
|-------|-------|
| Document Owner | Chief Information Security Officer (CISO) |
| Classification | Internal Use - Confidential |
| Review Cycle | Annual or upon significant regulatory/organizational change |
| Parent Documents | Enterprise AI Governance Policy; AI Risk Assessment Framework; AI Security Controls Catalog; AI System Documentation Standards |
| Target Audience | Project Managers, System Owners, Developers, Security Teams, Clinical Informatics, Procurement |

---

## Table of Contents

1. Introduction
2. AI System Intake Process
3. Risk Assessment Execution Guide
4. Control Implementation Guides
5. Approval Workflow Procedures
6. Third-Party AI Procurement Guide
7. LLM/GenAI Deployment Guide
8. Clinical AI Implementation
9. Monitoring and Operations Runbook
10. AI Incident Response Playbook
11. Templates and Tools

---

## 1. Introduction

### 1.1 Purpose

This AI Implementation Playbook provides practical, step-by-step guidance for executing the organization's AI governance program. While the Enterprise AI Governance Policy establishes requirements, the AI Risk Assessment Framework defines methodology, the AI Security Controls Catalog specifies controls, and the AI System Documentation Standards defines what to document, this playbook translates those documents into actionable procedures for day-to-day use.

### 1.2 Target Audience

| Role | Primary Use Cases |
|------|-------------------|
| Project Managers | AI system intake, approval workflows, timeline planning |
| System Owners | Risk assessment, control implementation, ongoing compliance |
| Developers | Technical control implementation, LLM deployment, security requirements |
| Security Teams | Risk assessments, security reviews, incident response, monitoring |
| Clinical Informatics | Clinical AI implementation, FDA pathways, clinical validation |
| Procurement | Vendor assessment, contract requirements, third-party AI |

### 1.3 Document Relationships

This playbook operationalizes four parent governance documents:

| Document | Purpose |
|----------|---------|
| **Enterprise AI Governance Policy** | Establishes WHAT is required (requirements, roles, principles) |
| **AI Risk Assessment Framework** | Defines HOW to assess risk (methodology, scoring, classification) |
| **AI Security Controls Catalog** | Specifies WHAT controls to implement (50 controls across 6 domains) |
| **AI System Documentation Standards** | Specifies WHAT to document (model cards, data docs, validation, operations) |
| **This Playbook** | Provides step-by-step HOW-TO guidance for executing all of the above |

### 1.4 Quick-Start Guide

Start here based on what you need to do:

| If you need to... | Go to Section |
|-------------------|---------------|
| Register a new AI system | Section 2: AI System Intake Process |
| Conduct a risk assessment | Section 3: Risk Assessment Execution |
| Implement security controls | Section 4: Control Implementation |
| Get approval to deploy | Section 5: Approval Workflows |
| Evaluate an AI vendor | Section 6: Third-Party Procurement |
| Deploy an LLM or GenAI application | Section 7: LLM/GenAI Deployment |
| Implement clinical AI | Section 8: Clinical AI Implementation |
| Set up monitoring or handle operations | Section 9: Monitoring & Operations |
| Respond to an AI incident | Section 10: Incident Response |
| Find templates or quick references | Section 11: Templates & Tools |

---

## 2. AI System Intake Process

This section guides you through registering AI systems in the organization's AI inventory and initiating the governance process.

### 2.1 What Qualifies as an AI System?

#### 2.1.1 In Scope (Requires Registration)

- Machine learning models (supervised, unsupervised, reinforcement learning)
- Deep learning and neural networks
- Large Language Models (LLMs) and generative AI
- Natural language processing (NLP) systems
- Computer vision and image analysis
- Predictive analytics using ML algorithms
- Clinical decision support with ML components
- Robotic Process Automation (RPA) with cognitive/learning capabilities
- Third-party SaaS applications with AI features
- Embedded AI components within larger systems

#### 2.1.2 Out of Scope

- Rule-based systems without learning capability
- Standard statistical analysis (regression, t-tests)
- Basic automation without AI/ML
- Spreadsheet formulas and macros
- Simple keyword search

#### 2.1.3 Decision Flowchart

If you answer **YES** to any of these questions, the system likely requires AI governance:

| # | Question | If YES |
|---|----------|--------|
| 1 | Does the system learn from data or improve over time? | → Register |
| 2 | Does it make predictions, recommendations, or classifications? | → Register |
| 3 | Does it generate content (text, images, code, audio)? | → Register |
| 4 | Does the vendor describe it as AI, ML, or "intelligent"? | → Investigate |
| 5 | Does it use neural networks, LLMs, or deep learning? | → Register |

### 2.2 Intake Workflow

| Step | Action | Details | Responsible |
|------|--------|---------|-------------|
| 1 | Submit Intake Request | Complete AI System Intake Form with use case, data types, deployment scope | Requestor |
| 2 | Initial Triage | Confirm AI governance applies; preliminary risk assessment; identify stakeholders | Security Team |
| 3 | Assign System Owner | Designate accountable individual; document in inventory | Dept Leadership |
| 4 | Register in Inventory | Create AI inventory record with unique ID; link to intake documentation | Security Team |
| 5 | Route for Assessment | Initiate full risk assessment process (Section 3) | Security Team |

### 2.3 Shadow AI Identification

Proactively identify unauthorized AI use through these detection methods:

- **Network Monitoring:** Monitor for connections to AI service providers (OpenAI, Anthropic, Google AI, Azure OpenAI, AWS Bedrock)
- **Expense Review:** Review P-card and expense reports for AI service subscriptions
- **Software Inventory:** Scan endpoints for AI application installations
- **Contract Review:** Audit vendor contracts for embedded AI capabilities
- **Self-Reporting Campaigns:** Periodic amnesty campaigns encouraging voluntary disclosure

#### 2.3.1 Shadow AI Remediation

1. Document current usage and data exposure
2. Assess immediate risk (PHI involved? Clinical use?)
3. If HIGH immediate risk: Suspend use pending review
4. Initiate expedited intake process
5. Identify approved alternatives if available
6. Address root cause (training, tool availability)

### 2.4 Intake Service Levels

| Activity | Target SLA |
|----------|------------|
| Intake request acknowledgment | 2 business days |
| Triage completion (in-scope determination) | 3 business days |
| Inventory registration | Same day as triage completion |
| Assessment kickoff | 5 business days from registration |

---

## 3. Risk Assessment Execution Guide

This section provides detailed guidance for executing AI risk assessments using the methodology defined in the AI Risk Assessment Framework.

### 3.1 Assessment Preparation

Gather this information before beginning the assessment:

| Information Needed | Source | Key Documents |
|-------------------|--------|---------------|
| Use case description | Intake form, System Owner interview | Business requirements |
| Data types processed | Technical documentation, data flows | Data flow diagrams |
| User population | System Owner, project documentation | Deployment plan |
| Integration points | Architecture diagrams | Technical architecture |
| Vendor documentation | Procurement, vendor | SOC 2, model cards |
| Clinical context (if applicable) | Clinical sponsor, CMIO | Clinical workflow docs |

### 3.2 Factor-by-Factor Scoring Guide

#### 3.2.1 Factor 1: Patient/Clinical Impact (Weight: 25%)

| Score | Level | Description & Examples |
|-------|-------|------------------------|
| 1 | No Clinical Impact | AI output never reaches patients or clinicians. Examples: IT helpdesk chatbot, facilities scheduling, financial reporting, HR analytics |
| 2 | Indirect Clinical Impact | Supports clinical workflows but doesn't drive decisions. Errors cause inefficiency, not direct harm. Examples: appointment optimization, clinical documentation assistance with review, medical supply chain |
| 3 | Direct Clinical Impact | Directly influences diagnosis, treatment, or clinical decisions. Errors could cause patient harm. Examples: diagnostic imaging AI, sepsis prediction alerts, drug interaction warnings, treatment recommendations |

**Key Question:** If the AI produced incorrect output, could it directly lead to patient harm?

#### 3.2.2 Factor 2: Data Sensitivity (Weight: 20%)

| Score | Level | Description & Examples |
|-------|-------|------------------------|
| 1 | Non-Sensitive | Public information, no PII/PHI/confidential data. Examples: public research data, facility hours, general policies |
| 2 | Confidential / PII | Internal confidential, limited PII (names, contact info), de-identified health data, workforce data. Examples: employee scheduling, de-identified analytics |
| 3 | PHI / Highly Sensitive | Protected Health Information, sensitive PII (SSN, financial), mental health/substance abuse/HIV/genetic data, minors' data. Examples: patient records, clinical notes, lab results |

**Key Question:** What is the most sensitive data type the AI will process, store, or transmit?

#### 3.2.3 Factor 3: Autonomy Level (Weight: 20%)

| Score | Level | Description & Examples |
|-------|-------|------------------------|
| 1 | Human-in-the-Loop | Human reviews and approves every AI output before action. AI provides recommendations only. Examples: AI drafts email for review, AI suggests diagnosis for physician confirmation |
| 2 | Human-on-the-Loop | AI operates with human oversight; humans can intervene but don't approve each action. Examples: AI auto-routes tickets with escalation path, scheduling with override capability |
| 3 | Autonomous | AI operates independently; human intervention is reactive. Examples: automated clinical alerts triggering workflows, real-time fraud blocking, autonomous monitoring |

**Key Question:** Does a human review and approve AI outputs before they result in action?

#### 3.2.4 Factors 4-6: Quick Reference

| Factor | Weight | Score 1 | Score 2 | Score 3 |
|--------|--------|---------|---------|---------|
| Scale and Scope | 15% | <100 affected | 100-10,000 | >10,000 |
| Reversibility | 10% | Easily undone | Effort to reverse | Permanent |
| Regulatory Exposure | 10% | Standard IT | HIPAA/Privacy | FDA/Medical |

### 3.3 Scoring Calculation

**Formula:** Composite Score = Σ (Factor Weight × Factor Score)

**Risk Tiers:**
- **HIGH** = 2.20-3.00
- **MODERATE** = 1.50-2.19
- **LOW** = 1.00-1.49

**Automatic Escalation to HIGH:**
- Clinical Impact = 3, OR
- Autonomy = 3 with PHI, OR
- Regulatory = 3 (FDA)

### 3.4 Common Scoring Pitfalls

| Pitfall | Correct Approach |
|---------|------------------|
| Scoring based on intended use only | Consider potential misuse and unintended consequences |
| Underestimating 'de-identified' data | Assess re-identification risk; may still require Score 2 |
| Assuming human review when not enforced | Verify review is mandatory in workflow, not just possible |
| Scoring pilot instead of full rollout | Score based on planned full deployment scope |
| Trusting vendor claims as evidence | Independently verify; 'AI-powered' ≠ low risk |
| Ignoring downstream uses | Trace how outputs are used; indirect impact may exist |

### 3.5 Worked Examples

#### 3.5.1 Example: Diagnostic Imaging AI (HIGH Risk)

**Use Case:** AI analyzes chest X-rays to flag potential pneumonia for radiologist review

| Factor | Score | Rationale |
|--------|-------|-----------|
| Clinical Impact (25%) | 3 | Direct diagnostic impact; missed findings could delay treatment |
| Data Sensitivity (20%) | 3 | PHI - medical images linked to patient records |
| Autonomy Level (20%) | 1 | Radiologist reviews all images; AI flags for attention |
| Scale and Scope (15%) | 3 | Enterprise deployment; 50K+ patients per year |
| Reversibility (10%) | 2 | Missed diagnosis caught later but may delay treatment |
| Regulatory Exposure (10%) | 3 | FDA-regulated Software as Medical Device (SaMD) |

**Composite Score:** (0.25×3)+(0.20×3)+(0.20×1)+(0.15×3)+(0.10×2)+(0.10×3) = **2.55 → HIGH RISK**

*Also auto-escalated: Clinical=3, Regulatory=3*

#### 3.5.2 Example: Meeting Transcription AI (LOW Risk)

**Use Case:** AI transcribes administrative meetings and generates summaries

| Factor                    | Score | Rationale                                              |
| ------------------------- | ----- | ------------------------------------------------------ |
| Clinical Impact (25%)     | 1     | Administrative meetings only; no clinical content      |
| Data Sensitivity (20%)    | 2     | Internal confidential - employee names, business plans |
| Autonomy Level (20%)      | 1     | Transcripts reviewed by organizer before distribution  |
| Scale and Scope (15%)     | 1     | Single department pilot; ~50 users                     |
| Reversibility (10%)       | 1     | Transcripts can be corrected or deleted easily         |
| Regulatory Exposure (10%) | 1     | Standard IT governance only                            |

**Composite Score:** (0.25×1)+(0.20×2)+(0.20×1)+(0.15×1)+(0.10×1)+(0.10×1) = **1.20 → LOW RISK**

---

## 4. Control Implementation Guides

This section provides practical guidance for implementing controls from the AI Security Controls Catalog.

*Documentation requirements for each control implementation are specified in the AI System Documentation Standards, Section 6: Security Documentation Standards.*

### 4.1 Implementation Approach

Control implementation should follow a risk-based, phased approach:

1. **Phase 1 - Foundation:** Implement governance controls (GOV) that establish accountability and processes
2. **Phase 2 - Data Protection:** Implement data governance controls (DATA) to protect sensitive information
3. **Phase 3 - Technical Security:** Implement model and operational controls (MODEL, OPS) for technical safeguards
4. **Phase 4 - Specialized:** Implement supply chain and LLM-specific controls (SUPPLY, LLM) as applicable

### 4.2 Implementation Sequencing by Risk Tier

#### 4.2.1 HIGH Risk Systems - Implementation Sequence

All 50 controls required. Implement in this sequence before deployment:

| Week | Domain | Priority Controls | Milestone |
|------|--------|-------------------|-----------|
| 1-2 | GOV | GOV-01 (Inventory), GOV-02 (Ownership), GOV-04 (Risk Assessment), GOV-05 (Documentation) | Governance Foundation |
| 3-4 | DATA | DATA-03 (Privacy), DATA-04 (Classification), DATA-06 (Integrity), DATA-01 (Provenance) | Data Protection |
| 5-6 | MODEL | MODEL-03 (Validation), MODEL-04 (Bias Testing), MODEL-06 (Version Control), MODEL-02 (Model Cards) | Model Readiness |
| 7-8 | OPS | OPS-01 (Access), OPS-02 (Logging), OPS-04 (Incident Response), OPS-05 (Human Override) | Operational Security |
| 9-10 | LLM/SUPPLY | LLM-01 (Prompt Injection), LLM-02 (Sensitive Info), SUPPLY-01 (Vendor), SUPPLY-04 (Dependencies) | Specialized Controls |
| 11-12 | ALL | Remaining controls, validation testing, documentation completion | Deployment Ready |

#### 4.2.2 MODERATE Risk Systems - Implementation Sequence

~35 controls required. Target 4-6 weeks implementation:

| Week | Domain | Priority Controls | Milestone |
|------|--------|-------------------|-----------|
| 1 | GOV | GOV-01, GOV-02, GOV-04, GOV-05 | Governance Complete |
| 2 | DATA | DATA-03, DATA-04, DATA-06 | Data Protection |
| 3-4 | MODEL/OPS | MODEL-03, MODEL-06, MODEL-08, OPS-01, OPS-02, OPS-04 | Technical Controls |
| 5-6 | LLM/ALL | LLM controls (if applicable), remaining required controls, validation | Deployment Ready |

#### 4.2.3 LOW Risk Systems - Implementation Sequence

25 controls required. Target 1-2 weeks implementation:

| Week | Domain | Priority Controls | Milestone |
|------|--------|-------------------|-----------|
| 1 | GOV/DATA/OPS | GOV-01, GOV-02, GOV-05, DATA-03, DATA-04, OPS-01, OPS-02 | Core Controls |
| 2 | ALL | Remaining required controls, documentation, LLM basics if applicable | Deployment Ready |

### 4.3 Domain Implementation Checklists

#### 4.3.1 Governance (GOV) - Quick Implementation Guide

| Control | Quick Win | Implementation Steps |
|---------|-----------|---------------------|
| GOV-01 | Spreadsheet inventory | Create AI inventory spreadsheet with required fields; integrate with CMDB later |
| GOV-02 | Assignment memo | Document System Owner in inventory; send formal assignment email/memo |
| GOV-04 | Complete assessment | Use Section 3 of this playbook; document in standard template |
| GOV-05 | Folder structure | Create standard documentation folder; populate with templates from Section 11 |

#### 4.3.2 Data Governance (DATA) - Quick Implementation Guide

| Control | Quick Win | Implementation Steps |
|---------|-----------|---------------------|
| DATA-03 | PIA coordination | Engage Privacy Officer; complete PIA using existing template; document legal basis |
| DATA-04 | Data inventory | List all data elements; apply existing classification scheme; document in system record |
| DATA-06 | Access controls | Implement RBAC; enable audit logging; configure encryption at rest/transit |

#### 4.3.3 Model Lifecycle (MODEL) - Quick Implementation Guide

| Control | Quick Win | Implementation Steps |
|---------|-----------|---------------------|
| MODEL-02 | Model card template | Complete model card using template from Section 11; see AI System Documentation Standards Section 3 |
| MODEL-03 | Validation report | Document validation methodology and results; see AI System Documentation Standards Section 5 |
| MODEL-06 | Git repository | Store model artifacts in version control; tag releases; document versioning scheme |

#### 4.3.4 Operational Security (OPS) - Quick Implementation Guide

| Control | Quick Win | Implementation Steps |
|---------|-----------|---------------------|
| OPS-01 | RBAC setup | Define roles (admin/operator/user); configure authentication; enable MFA for admin |
| OPS-02 | Enable logging | Configure application and access logging; forward to SIEM; set retention |
| OPS-04 | Incident runbook | Document AI-specific incident procedures; integrate with org IR process |
| OPS-05 | Kill switch | Implement disable capability; document procedure; test quarterly |

---

## 5. Approval Workflow Procedures

This section details the approval process for AI system deployment based on risk tier.

### 5.1 Approval Authority Matrix

| Risk Tier | Approval Authority | Required Reviews | Typical Timeline |
|-----------|-------------------|------------------|------------------|
| **HIGH** | AI Governance Board | Security, Privacy, Clinical (if applicable), Legal | 10-14 weeks |
| **MODERATE** | CISO + System Owner | Security, Privacy (if PHI) | 4-6 weeks |
| **LOW** | System Owner (self-attestation) | Security notification | 1-2 weeks |

### 5.2 Approval Package Requirements

#### 5.2.1 HIGH Risk Approval Package

Required documentation for AI Governance Board review:

- [ ] Completed Risk Assessment with scoring rationale
- [ ] AI Impact Assessment (AIIA)
- [ ] Model Card / System Card
- [ ] Data documentation (Datasheet, Data Dictionary)
- [ ] Validation Report with bias/fairness results
- [ ] Security Assessment Report
- [ ] Control implementation evidence (all 50 controls)
- [ ] Operational Runbook
- [ ] Clinical validation and champion sign-off (if clinical)
- [ ] Privacy Impact Assessment
- [ ] Vendor assessment (if third-party)
- [ ] Documentation completeness verification per AI System Documentation Standards, Section 8.6

#### 5.2.2 MODERATE Risk Approval Package

Required documentation for CISO approval:

- [ ] Completed Risk Assessment
- [ ] System Card / Model Card (standard depth)
- [ ] Validation Summary
- [ ] Security Assessment (standard)
- [ ] Control implementation evidence (~35 controls)
- [ ] Operational Runbook (standard)
- [ ] Privacy Impact Assessment (if PHI)

#### 5.2.3 LOW Risk Approval Package

Required for System Owner self-attestation:

- [ ] Completed Risk Assessment Worksheet
- [ ] Basic System Registration
- [ ] Control checklist (25 controls)
- [ ] Acknowledgment of governance requirements

### 5.3 Approval Workflow Steps

#### 5.3.1 HIGH Risk Workflow

```
1. System Owner assembles approval package
   ↓
2. Security Team validates completeness and conducts security review
   ↓
3. Privacy Officer reviews PIA and data handling
   ↓
4. Clinical review (if applicable) - Clinical Champion sign-off
   ↓
5. Legal review (if significant regulatory or contract implications)
   ↓
6. Package submitted to AI Governance Board
   ↓
7. Board review at scheduled meeting (or emergency session)
   ↓
8. Board decision: Approve / Approve with Conditions / Deny / Defer
   ↓
9. If approved: Document approval; proceed to deployment
   If conditions: Address conditions; return to appropriate step
   If denied: Document reasons; determine path forward
```

#### 5.3.2 MODERATE Risk Workflow

```
1. System Owner assembles approval package
   ↓
2. Security Team validates and conducts review
   ↓
3. Privacy Officer review (if PHI involved)
   ↓
4. CISO reviews and approves/denies
   ↓
5. System Owner confirms approval; proceed to deployment
   ↓
6. Notify AI Governance Board (informational)
```

#### 5.3.3 LOW Risk Workflow

```
1. System Owner completes Risk Assessment Worksheet
   ↓
2. System Owner completes control checklist (self-attestation)
   ↓
3. System Owner registers system in AI inventory
   ↓
4. Notify Security Team and AI Governance Board (informational)
   ↓
5. Proceed to deployment
```

### 5.4 Escalation Procedures

| Situation | Escalation Path |
|-----------|-----------------|
| Disagreement on risk tier | Security Team → CISO → AI Governance Board |
| Urgent deployment need | System Owner → CISO → Emergency Board review |
| Approval conditions not met | Back to approval authority for re-review |
| Post-deployment risk increase | Re-assessment; may require higher-level approval |

### 5.5 Approval Documentation

All approvals must be documented with:

- Approval date
- Approving authority/individual
- Version of system approved
- Any conditions or restrictions
- Expiration/review date
- Link to approval package

---

## 6. Third-Party AI Procurement Guide

This section provides guidance for evaluating, procuring, and managing third-party AI systems and services.

### 6.1 Pre-Procurement Assessment

Before engaging with vendors:

1. **Define Requirements**
   - Specific use case and business need
   - Data types that will be processed
   - Integration requirements
   - Performance expectations
   - Compliance requirements (HIPAA, FDA, etc.)

2. **Preliminary Risk Assessment**
   - Estimate risk tier based on intended use
   - Identify deal-breaker requirements
   - Determine budget for security/compliance review

### 6.2 Vendor Assessment Process

#### 6.2.1 Security and Compliance Assessment

| Assessment Area         | Key Questions                                 | Evidence Required            |
| ----------------------- | --------------------------------------------- | ---------------------------- |
| Security Certifications | SOC 2 Type II? ISO 27001? HITRUST?            | Current certificates/reports |
| Data Handling           | Where is data stored? Who can access?         | Data flow documentation      |
| Encryption              | At rest? In transit? Key management?          | Technical documentation      |
| Access Controls         | Authentication? Authorization? Audit logging? | Security documentation       |
| Incident Response       | Notification timeline? Process?               | IR policy/procedures         |
| Business Continuity     | Availability SLA? DR capabilities?            | BC/DR documentation          |

#### 6.2.2 AI-Specific Assessment

| Assessment Area        | Key Questions                                    | Evidence Required            |
| ---------------------- | ------------------------------------------------ | ---------------------------- |
| Model Documentation    | Model cards available? Training data documented? | Model documentation          |
| Bias Testing           | Tested for demographic bias? Results available?  | Bias assessment reports      |
| Explainability         | Can outputs be explained? How?                   | Explainability documentation |
| Performance Validation | Published performance metrics? On what data?     | Validation reports           |
| Update Process         | How are model updates communicated?              | Update policy                |
| Human Override         | Can outputs be overridden? Kill switch?          | Product documentation        |

### 6.3 Vendor Assessment Questionnaire (Summary)

The full vendor questionnaire should cover:

**Section A: Company Information**
- Company background and stability
- AI/ML experience and expertise
- Healthcare experience (if applicable)
- References

**Section B: Security Controls**
- Infrastructure security
- Application security
- Data protection
- Access management
- Incident response

**Section C: AI Governance**
- Model development practices
- Training data governance
- Bias testing and fairness
- Model monitoring and updates
- Transparency and explainability

**Section D: Privacy and Compliance**
- Data processing practices
- HIPAA compliance (BAA available?)
- Data subject rights
- Data retention and deletion
- Regulatory compliance

**Section E: Operational**
- SLAs and support
- Integration capabilities
- Customization options
- Exit provisions

### 6.4 Contract Requirements Checklist

Ensure contracts include:

- [ ] **Data Ownership:** Customer owns all data; vendor has limited use rights
- [ ] **Training Data Prohibition:** Vendor cannot use customer data for training without explicit consent
- [ ] **Security Requirements:** Specific security controls required; right to audit
- [ ] **Incident Notification:** Specific timeline for breach notification (e.g., 24-72 hours)
- [ ] **Model Update Notification:** Advance notice of model changes
- [ ] **SLAs:** Availability, performance, support response times
- [ ] **Compliance:** HIPAA BAA (if PHI), other applicable regulations
- [ ] **Liability:** Appropriate indemnification for AI-related harms
- [ ] **Audit Rights:** Right to assess vendor security and AI practices
- [ ] **Exit Provisions:** Data return, transition assistance, deletion confirmation

### 6.5 Ongoing Vendor Management

| Activity                    | Frequency   | Responsible             |
| --------------------------- | ----------- | ----------------------- |
| Performance monitoring      | Continuous  | System Owner            |
| Security posture review     | Annual      | Security Team           |
| Contract compliance review  | Annual      | Procurement/Legal       |
| Model update assessment     | As notified | System Owner + Security |
| Re-validation after updates | As needed   | System Owner            |

---

## 7. LLM/GenAI Deployment Guide

This section provides specific guidance for deploying Large Language Models and Generative AI applications.

### 7.1 LLM Deployment Decision Framework

#### 7.1.1 Deployment Model Options

| Model                 | Description                              | Security Considerations                            |
| --------------------- | ---------------------------------------- | -------------------------------------------------- |
| **API-based (Cloud)** | Use vendor API (OpenAI, Anthropic, etc.) | Data leaves organization; vendor access to prompts |
| **Managed Service**   | Vendor-hosted dedicated instance         | Better isolation; still external                   |
| **Self-hosted**       | Run model on own infrastructure          | Full control; significant resources required       |
| **Hybrid**            | Different models for different use cases | Complexity; need consistent governance             |

#### 7.1.2 Selection Criteria

| Factor           | Considerations                                              |
| ---------------- | ----------------------------------------------------------- |
| Data Sensitivity | PHI/PII → prefer self-hosted or strong contractual controls |
| Use Case         | Public-facing → stronger content controls needed            |
| Scale            | High volume → consider cost and rate limits                 |
| Customization    | Fine-tuning needed → limits options                         |
| Latency          | Real-time → consider hosting location                       |

### 7.2 LLM Security Implementation Checklist

#### 7.2.1 Input Security

- [ ] Input validation and sanitization implemented
- [ ] Maximum input length enforced
- [ ] Prompt injection defenses in place
- [ ] User input separated from system prompts
- [ ] Sensitive data detection on inputs (block PHI if not authorized)

#### 7.2.2 Output Security

- [ ] Output content filtering enabled
- [ ] PII/PHI detection on outputs
- [ ] Hallucination warnings for factual content
- [ ] Output length limits enforced
- [ ] Harmful content blocking

#### 7.2.3 System Prompt Security

- [ ] System prompts stored securely (not in client-side code)
- [ ] System prompts version controlled
- [ ] Access to system prompts restricted
- [ ] Defenses against prompt extraction

#### 7.2.4 Access and Rate Limiting

- [ ] Authentication required for all access
- [ ] Per-user rate limits configured
- [ ] Token/cost limits per user/session
- [ ] Abuse detection monitoring
- [ ] API key rotation procedures

#### 7.2.5 Monitoring

- [ ] All prompts and responses logged (with appropriate privacy controls)
- [ ] Security events monitored (injection attempts, jailbreaks)
- [ ] Usage patterns monitored for anomalies
- [ ] Cost monitoring and alerting
- [ ] Performance monitoring

### 7.3 RAG (Retrieval Augmented Generation) Security

If implementing RAG:

| Control Area        | Requirements                                                          |
| ------------------- | --------------------------------------------------------------------- |
| Document Ingestion  | Validate sources; scan for malicious content; respect access controls |
| Vector Database     | Secure storage; access controls; encryption                           |
| Retrieval           | Enforce user authorization on retrieved documents                     |
| Prompt Construction | Sanitize retrieved content before including in prompts                |
| Citation            | Provide sources for generated content                                 |

### 7.4 LLM-Specific Risk Considerations

| Risk                 | Mitigation                                                                        |
| -------------------- | --------------------------------------------------------------------------------- |
| **Hallucination**    | RAG for grounding; user warnings; verification requirements for critical content  |
| **Prompt Injection** | Input validation; prompt/response separation; monitoring                          |
| **Data Leakage**     | Output filtering; don't include sensitive data in prompts; training data controls |
| **Harmful Content**  | Content filtering; use case restrictions; monitoring                              |
| **Bias**             | Testing across demographics; monitoring for biased outputs                        |
| **Over-reliance**    | User training; appropriate disclaimers; human review requirements                 |

### 7.5 LLM Acceptable Use Guidelines

Communicate these guidelines to LLM users:

**DO:**
- Use for approved use cases only
- Verify factual claims before acting on them
- Report concerning outputs
- Protect prompt confidentiality
- Follow data handling guidelines

**DON'T:**
- Input PHI unless specifically authorized
- Attempt to bypass safety controls
- Share API keys or access credentials
- Use for prohibited purposes (per policy)
- Trust outputs without verification for critical decisions

---

## 8. Clinical AI Implementation

This section provides additional guidance for AI systems used in clinical and patient care contexts.

### 8.1 Clinical AI Categories and Requirements

| Category | Examples | Additional Requirements |
|----------|----------|------------------------|
| **Diagnostic AI** | Radiology AI, pathology detection, sepsis prediction | FDA determination; clinical validation; physician oversight |
| **Treatment AI** | Drug dosing, treatment recommendations, care pathways | FDA determination; clinical validation; pharmacist/physician review |
| **Clinical Workflow AI** | Documentation, scheduling, order suggestions | Clinical champion; workflow integration review |
| **Administrative AI** | Revenue cycle, claims, supply chain | Standard governance (no additional clinical requirements) |

### 8.2 FDA Regulatory Pathway

#### 8.2.1 FDA Determination Flowchart

```
Does the AI system diagnose, treat, cure, mitigate, or prevent disease?
    ↓ YES                              ↓ NO
Is it Software as a Medical             → Standard IT governance
Device (SaMD)?
    ↓ YES
Does it meet CDS exclusion criteria?
(Displays source, presents basis, 
allows clinician review, not intended
to replace clinical judgment)
    ↓ YES                              ↓ NO
Document CDS exclusion                  → Consult Regulatory Affairs
analysis; standard governance              for FDA pathway
```

#### 8.2.2 When to Engage Regulatory Affairs

Engage Regulatory Affairs **before procurement or development** when:

- AI makes diagnostic or treatment recommendations
- AI is marketed as a medical device by vendor
- AI provides patient-specific clinical predictions
- Uncertain whether CDS exclusion applies
- Any FDA-regulated indication

### 8.3 Clinical Validation Requirements

| Risk/Category | Validation Requirements |
|---------------|------------------------|
| HIGH risk clinical | Formal clinical study protocol; IRB review; external validation site; clinical endpoints |
| MODERATE risk clinical | Internal validation on representative data; clinical SME review; pilot period |
| LOW risk / workflow | Functional validation; clinical champion review |

### 8.4 Clinical AI Implementation Checklist

#### 8.4.1 Pre-Implementation

- [ ] Clinical use case clearly defined
- [ ] Clinical champion identified and engaged
- [ ] FDA determination completed (document CDS exclusion or regulatory pathway)
- [ ] Risk assessment completed with clinical input
- [ ] Clinical validation plan developed
- [ ] EHR integration plan reviewed with Clinical Informatics

#### 8.4.2 Validation Phase

- [ ] Validation dataset identified (representative of target population)
- [ ] Performance metrics defined with clinical input
- [ ] Subgroup analysis planned (demographics, disease severity)
- [ ] Clinical SME review of validation results
- [ ] Pilot deployment plan (limited scope)
- [ ] Monitoring plan for pilot period

#### 8.4.3 Go-Live

- [ ] Clinical workflow integration tested
- [ ] Clinician training completed
- [ ] Override mechanism verified
- [ ] Fallback procedures documented
- [ ] Monitoring dashboards active
- [ ] Escalation path for clinical concerns established

#### 8.4.4 Ongoing Operations

- [ ] Performance monitoring per Section 9
- [ ] Clinician feedback collection
- [ ] Periodic bias reassessment
- [ ] Annual clinical validation review
- [ ] Adverse event reporting process

### 8.5 Clinical AI Governance Roles

| Role | Responsibilities |
|------|------------------|
| **Clinical Champion** | Clinical appropriateness; workflow integration; clinician liaison; sign-off |
| **Clinical Informatics** | EHR integration; alert configuration; clinical workflow design |
| **System Owner** | Overall accountability; governance compliance; operations |
| **CMO/Designee** | HIGH risk clinical approval; clinical safety oversight |

---

## 9. Monitoring and Operations Runbook

This section provides operational guidance for monitoring AI systems in production.

### 9.1 AI Monitoring Framework

| Monitoring Dimension | What to Monitor | Why It Matters |
|---------------------|-----------------|----------------|
| **Model Performance** | Accuracy, precision, recall vs. baseline | Detect degradation before harm |
| **Data Drift** | Input distribution changes | Early warning of model staleness |
| **Concept Drift** | Input-output relationship changes | Model may need retraining |
| **Operational Health** | Latency, throughput, errors, availability | Service quality |
| **Security** | Access patterns, anomalies, violations | Detect attacks/misuse |
| **Fairness** | Performance across demographics | Detect emerging bias |
| **Usage** | Adoption, user feedback, override rates | Effectiveness signals |

### 9.2 Monitoring Schedule by Risk Tier

| Activity | HIGH | MODERATE | LOW |
|----------|------|----------|-----|
| Automated performance monitoring | Continuous | Continuous | Daily |
| Data drift detection | Daily | Weekly | Monthly |
| Performance metric review | Weekly | Monthly | Quarterly |
| Fairness/bias assessment | Monthly | Quarterly | Annually |
| Security log review | Weekly | Monthly | Quarterly |
| Full risk reassessment | Semi-annually | Annually | Every 2 years |
| Control effectiveness review | Annually | Annually | Every 2 years |

### 9.3 Standard Alert Thresholds

| Metric | Warning Threshold | Critical Threshold |
|--------|-------------------|-------------------|
| Accuracy drop | >5% from baseline | >10% from baseline |
| Data drift score | >0.1 PSI | >0.25 PSI |
| Error rate | >2% | >5% |
| Latency (P95) | >3x baseline | >5x baseline |
| Fairness disparity | >10% gap between groups | >20% gap |
| Override rate change | >20% increase | >50% increase |
| Security anomaly | Unusual pattern | Attack indicator |

### 9.4 Drift Response Procedures

#### 9.4.1 Data Drift Response

```
1. Verify alert (rule out data quality issues)
   ↓
2. Identify root cause (source data change? Population shift?)
   ↓
3. Assess impact on model performance
   ↓
4. Decide response:
   - Minor drift: Document and monitor
   - Moderate drift: Accelerate revalidation
   - Severe drift: Consider model retraining or temporary suspension
   ↓
5. Document decision and rationale
```

#### 9.4.2 Performance Degradation Response

```
1. Confirm degradation (not measurement error)
   ↓
2. Assess severity and impact
   ↓
3. Immediate mitigation if needed (increase human review, restrict use)
   ↓
4. Root cause analysis
   ↓
5. Remediation (retraining, threshold adjustment, etc.)
   ↓
6. Validate fix
   ↓
7. Restore normal operations
   ↓
8. Post-incident review
```

### 9.5 Model Update and Retraining Procedures

#### 9.5.1 Update Triggers

| Trigger | Action |
|---------|--------|
| Scheduled retraining | Per maintenance schedule |
| Performance degradation | Accelerated retraining |
| Data drift | Assess need for retraining |
| New training data available | Evaluate incorporation |
| Security vulnerability | Patch/update as needed |
| Regulatory/guideline change | Assess impact; update if needed |

#### 9.5.2 Update Approval Requirements

| Update Type | Approval Required |
|-------------|-------------------|
| Minor config/threshold changes | System Owner |
| Retraining on same data structure | System Owner + Security review |
| Retraining with new data sources | System Owner + Security + Data governance |
| Architecture changes | Full re-approval per original risk tier |
| FDA-regulated system updates | Per PCCP or new submission |

### 9.6 Human Override Procedures

#### 9.6.1 Override Capability Requirements

- HIGH risk systems MUST have override capability
- Override must be accessible without special tools or permissions
- All overrides must be logged with user and reason
- Override rates must be monitored

#### 9.6.2 Kill Switch Procedure

```
1. Authorized personnel: System Owner, Security Team, Clinical Leadership (for clinical AI)
   ↓
2. Invoke kill switch via [documented method - system-specific]
   ↓
3. Activate fallback/manual process
   ↓
4. Notify stakeholders per communication plan
   ↓
5. Document action and reason
   ↓
6. Initiate investigation/restoration planning
```

### 9.7 Operational Reporting

| Report | Audience | Frequency |
|--------|----------|-----------|
| AI System Dashboard | Operations team | Continuous |
| Weekly Operations Summary | System Owner | Weekly |
| Monthly Performance Report | System Owner + Security | Monthly |
| Quarterly AI Portfolio Review | AI Governance Board | Quarterly |
| Annual AI Governance Report | Executive leadership | Annually |

*Operational documentation requirements, including runbook structure and change log formats, are specified in the AI System Documentation Standards, Section 7.*

---

## 10. AI Incident Response Playbook

This section provides procedures for responding to AI-specific security and safety incidents.

### 10.1 AI Incident Categories

| Category | Examples | Severity Factors |
|----------|----------|------------------|
| **Security Attack** | Prompt injection, model extraction, adversarial attack, unauthorized access | Data exposure, system compromise |
| **Data Breach** | PHI exposure via AI output, training data leak, prompt/response logging exposure | Volume, sensitivity of data |
| **Model Failure** | Severe performance degradation, systematic errors, unexpected outputs | Impact on decisions, patient harm potential |
| **Clinical Safety Event** | Patient harm linked to AI, missed diagnosis, incorrect recommendation acted upon | Severity of harm, number affected |
| **Bias/Fairness Event** | Discriminatory outputs, disparate impact discovered | Scope, protected group affected |
| **Misuse** | Policy violation, inappropriate use, shadow AI with sensitive data | Data involved, intent |

### 10.2 AI Incident Severity Classification

| Severity | Criteria | Response Time | Escalation |
|----------|----------|---------------|------------|
| **CRITICAL** | Patient harm actual or imminent; PHI breach >500 records; active attack; complete HIGH risk AI failure | <1 hour | 24/7 escalation; CISO notification |
| **HIGH** | Significant performance degradation; PHI breach <500 records; security vulnerability exploited; bias event with patient impact | 4 hours | Business hours escalation; System Owner notification |
| **MEDIUM** | Moderate performance issues; policy violation; near-miss safety event; attempted attack blocked | 24 hours | Standard escalation |
| **LOW** | Minor issues; user complaints; cosmetic errors; questions about AI behavior | 72 hours | Normal workflow |

### 10.3 Incident Response Procedures

#### 10.3.1 Initial Response (All Incidents)

```
1. DETECT & REPORT
   - Incident identified through monitoring, user report, or other means
   - Report to Security Team via [incident reporting channel]
   ↓
2. TRIAGE & CLASSIFY
   - Confirm AI system involved
   - Classify incident category and severity
   - Assign incident commander
   ↓
3. ASSEMBLE TEAM
   - CRITICAL/HIGH: Security, System Owner, Clinical (if clinical AI)
   - MEDIUM/LOW: Security + System Owner
   ↓
4. CONTAIN
   - Assess need for immediate containment
   - Options: Increase monitoring, restrict access, disable AI, activate kill switch
   ↓
5. PRESERVE EVIDENCE
   - Capture logs, inputs/outputs, system state
   - Document timeline
```

#### 10.3.2 Security Attack Response

| Attack Type | Immediate Actions |
|-------------|-------------------|
| **Prompt Injection** | Block attacker; review affected outputs; strengthen input filtering; analyze attack pattern |
| **Model Extraction** | Block source; analyze query patterns; assess IP exposure; review rate limiting |
| **Adversarial Attack** | Disable affected functionality; collect attack samples; engage ML security expertise |
| **Unauthorized Access** | Revoke access; reset credentials; review audit logs; assess data exposure |

#### 10.3.3 Clinical Safety Event Response

```
1. PATIENT FIRST
   - Ensure patient receives appropriate care
   - Notify treating clinicians
   ↓
2. NOTIFY CLINICAL LEADERSHIP
   - CMO/designee for HIGH risk events
   - Clinical champion for all clinical AI events
   ↓
3. DISABLE IF INDICATED
   - If AI output caused or contributed to harm, consider suspension
   ↓
4. PRESERVE CLINICAL RECORD
   - Document AI involvement in patient record
   - Preserve AI system logs
   ↓
5. ROOT CAUSE ANALYSIS
   - Was harm caused by AI error, misuse, or other factor?
   ↓
6. REGULATORY REPORTING
   - FDA (if regulated device)
   - State reporting (if required)
   - Risk Management/Legal notification
```

### 10.4 Incident Communication Templates

#### 10.4.1 Internal Notification (CRITICAL/HIGH)

```
AI INCIDENT NOTIFICATION

Incident ID: [ID]
Time Detected: [DateTime]
Affected System: [AI System Name]
Severity: [CRITICAL/HIGH]

Impact: [Brief description of impact]

Current Status: [Contained/Under Investigation/etc.]

Actions Taken:
- [Action 1]
- [Action 2]

Next Update: [DateTime]

Incident Commander: [Name]
Contact: [Phone/Email]
```

#### 10.4.2 User Communication (Service Disruption)

```
[AI System Name] is temporarily unavailable while we investigate a technical issue. 

Please use [alternative process] in the meantime.

Expected restoration: [Time/TBD]

For urgent needs, contact [support contact].

We apologize for any inconvenience.
```

### 10.5 Post-Incident Activities

| Activity | Timeline | Owner |
|----------|----------|-------|
| Post-Incident Review | Within 5 business days (CRITICAL/HIGH) | Incident Commander |
| Corrective Actions | Identify within 10 days; track to completion | System Owner |
| Control Updates | Assess and implement as needed | Security Team |
| Documentation | Update system docs, runbooks, IR procedures | System Owner |
| Reporting | Report significant incidents to AI Governance Board | Security Team |

---

## 11. Templates and Tools

### 11.1 Template Index

| Template | Purpose | Section Reference |
|----------|---------|-------------------|
| AI System Intake Form | Initial registration | Section 2 |
| Risk Assessment Worksheet | Scoring and classification | Section 3 |
| Control Implementation Checklist | Track control implementation | Section 4 |
| Approval Request Package | Compile approval documentation | Section 5 |
| Vendor Assessment Questionnaire | Third-party evaluation | Section 6 |
| LLM Deployment Checklist | LLM-specific controls | Section 7 |
| FDA Determination Worksheet | Regulatory pathway | Section 8 |
| Model Card Template | Model documentation | AI System Documentation Standards Section 3 |
| Incident Report Form | Document incidents | Section 10 |

### 11.2 Quick Reference: Risk Assessment Scoring

| Factor | Weight | Score 1 | Score 2 | Score 3 |
|--------|--------|---------|---------|---------|
| Patient/Clinical Impact | 25% | None | Indirect | Direct |
| Data Sensitivity | 20% | Public | Confidential/PII | PHI |
| Autonomy Level | 20% | Human-in-loop | Human-on-loop | Autonomous |
| Scale and Scope | 15% | <100 | 100-10K | >10K |
| Reversibility | 10% | Easy | Effort | Permanent |
| Regulatory Exposure | 10% | Standard IT | HIPAA | FDA |

**Risk Tiers:** HIGH = 2.20-3.00 | MODERATE = 1.50-2.19 | LOW = 1.00-1.49

### 11.3 Quick Reference: Approval Authority

| Risk Tier | Approval Authority | Required Controls | Timeline |
|-----------|-------------------|-------------------|----------|
| HIGH | AI Governance Board | All 50 | 10-14 weeks |
| MODERATE | CISO + System Owner | ~35 | 4-6 weeks |
| LOW | System Owner (self-attestation) | 25 | 1-2 weeks |

### 11.4 Quick Reference: Key Contacts

| Role | Responsibilities | Contact |
|------|------------------|---------|
| AI Governance Program | Intake, policy questions, general guidance | [Email/Phone] |
| Security Team | Risk assessments, security reviews | [Email/Phone] |
| Clinical Informatics | Clinical AI, EHR integration | [Email/Phone] |
| Privacy Office | PIA, HIPAA, data privacy | [Email/Phone] |
| Legal | Contracts, regulatory, liability | [Email/Phone] |
| Regulatory Affairs | FDA, SaMD, medical device | [Email/Phone] |
| Procurement | Vendor contracts, purchasing | [Email/Phone] |

### 11.5 Glossary of Key Terms

| Term | Definition |
|------|------------|
| **AI System** | System that uses machine learning, deep learning, or other AI techniques to make predictions, recommendations, or decisions |
| **LLM** | Large Language Model - AI model trained on large text datasets to generate human-like text |
| **SaMD** | Software as a Medical Device - software intended for medical purposes without being part of hardware device |
| **Data Drift** | Change in the statistical properties of input data over time |
| **Concept Drift** | Change in the relationship between inputs and outputs over time |
| **Prompt Injection** | Attack that manipulates AI behavior by inserting malicious instructions |
| **RAG** | Retrieval Augmented Generation - technique combining LLM with document retrieval |
| **Model Card** | Standardized documentation of an AI model's purpose, performance, and limitations |
| **Human-in-the-Loop** | Human reviews and approves all AI outputs before action |
| **Kill Switch** | Mechanism to immediately disable AI functionality |

---

## Appendix: Related Documents

| Document | Relationship |
|----------|--------------|
| Enterprise AI Governance Policy | Parent policy establishing requirements |
| AI Risk Assessment Framework | Methodology for risk classification |
| AI Security Controls Catalog | Control definitions and applicability |
| AI System Documentation Standards | Documentation requirements throughout lifecycle |

---
