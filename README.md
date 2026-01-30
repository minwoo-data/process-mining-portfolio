# Process Analytics Portfolio

## Overview

Process mining and analytics engagement for an enterprise client's internal procure-to-pay system. This multi-week engagement focused on evaluating process compliance and identifying optimization opportunities through data-driven analysis.

> **Note on Data:** All identifying details, exact metrics, and proprietary references have been generalized to protect client confidentiality. Comparative findings, severity levels, and order-of-magnitude impacts are preserved to reflect analytical validity.

---

## Table of Contents

- [Project Objectives](#project-objectives)
- [Technical Approach](#technical-approach)
  - [Tools & Technologies](#tools--technologies)
  - [Methodology](#methodology)
- [Key Findings](#key-findings)
  - [Process Conformance Analysis](#1-process-conformance-analysis)
  - [Workflow Optimization Impact](#2-workflow-optimization-impact)
  - [Performance Bottleneck Analysis](#3-performance-bottleneck-analysis)
  - [Data Infrastructure Gaps](#4-data-infrastructure-gaps)
- [Business Impact & Recommendations](#business-impact--recommendations)
  - [Immediate Operational Improvements](#immediate-operational-improvements)
  - [Strategic Process Mining Roadmap](#strategic-process-mining-roadmap)
  - [Data Governance Framework](#data-governance-framework)
- [Technical Skills Demonstrated](#technical-skills-demonstrated)
- [Documentation](#documentation)
- [Contact](#contact)

---

## Project Objectives

- Achieve end-to-end procurement process visibility
- Identify bottlenecks, inefficiencies, and compliance risks
- Validate effectiveness of simplified workflows for low-value purchases
- Uncover data quality issues affecting process management

---

## Technical Approach

### Tools & Technologies

| Category | Tools |
|----------|-------|
| **Data Processing** | Python (pandas, numpy) |
| **Process Mining** | ProDiscovery |
| **Data Visualization** | Matplotlib, Process Flow Diagrams |
| **Data Sources** | Procurement System, Workflow/Approval System, Financial Settlement System |

### Methodology

#### Phase 1: Data Integration (Week 1-2)

**Objective**: Transform disparate system data into unified event log

**Activities**:
- Standardized field names and timestamp formats across multiple source systems
- Implemented attribute-based mapping to connect procurement, approval, and payment records
- Generated missing timestamps to enable continuous process flow analysis
- Applied data quality filters and validation rules

**Output**:
- Filtered event log: hundreds of cases, 1,200+ events, 15+ distinct activities
- Event coverage: ~70% of target process steps
- Majority of cases met analysis criteria after quality filters; remainder excluded for completeness

#### Phase 2: Process Mining (Week 2-3)

**Objective**: Reconstruct and analyze actual process flows

**Activities**:
- Event log reconstruction from multi-system data
- Process conformance checking against standard workflow
- Process pattern identification and deviation analysis
- Lead time decomposition (processing time vs. waiting time)
- Dotted chart analysis for temporal pattern recognition

**Output**:
- Standard process model vs. actual process variants
- Conformance rate calculation
- Deviation pattern taxonomy (3 types identified)

#### Phase 3: Analytics & Insights (Week 3-4)

**Objective**: Generate actionable insights and recommendations

**Activities**:
- Statistical correlation analysis: transaction size vs. processing speed
- Root cause analysis for long-duration outlier cases
- Organizational-level approval delay investigation
- Simplified workflow effectiveness validation

**Output**:
- Multiple analytical scenarios completed
- Quantified business impact metrics
- Strategic roadmap for process mining expansion

---

## Key Findings

### 1. Process Conformance Analysis

**Summary**: Majority of procurement cases follow standard process, with identifiable deviation patterns

**Detailed Findings**:
- **~80–85%** of cases followed the standard procure-to-pay workflow (request → selection → order → receipt → inspection → payment).
- **~15–20%** showed process deviations categorized into **three distinct patterns**:
  - **Type A**: Orders initiated before request registration (sequence violation)
  - **Type B**: Requests registered after goods receipt (retrospective logging)
  - **Type C**: Contract finalization after order issuance (out-of-sequence approval)

**Implications**:
- **High compliance risk** in deviation cases
- Need for pre-submission validation controls
- Audit exposure in non-conforming transactions

### 2. Workflow Optimization Impact

**Summary**: Simplified workflows demonstrate significant cycle time reduction

**Detailed Findings**:
- Simplified approval process achieved **~80–90% cycle time reduction** vs. complex path:
  - **Streamlined path**: median cycle time in the **order of hours** (single-digit to low double-digit)
  - **Complex path**: median cycle time in the **order of days to weeks**
- Strong inverse correlation validated: **lower transaction amounts → faster processing**
- Approval step count directly impacts total lead time:
  - Single-step approval: fastest processing
  - Multi-step approval: proportional delay increase

**Implications**:
- Low-value purchase simplification initiative is **highly effective**
- Opportunity to expand simplified workflows to more categories
- Potential for automated approval thresholds

### 3. Performance Bottleneck Analysis

**Summary**: Significant portion of cases experience extended lead times driven by approval delays

**Detailed Findings**:
- **~35–45%** of cases exceeded average lead time
- Lead time distribution: mean in the **order of months**; median slightly lower but still **order of weeks to months**
- **Root cause identified**: Approval waiting time (primary driver), especially at payment/financial sign-off stage
- **Secondary factors**:
  - Organizational-level approval variations
  - Multi-department coordination requirements
  - Certain organizational units showed consistently longer approval times

**Implications**:
- Approval stage requires process redesign (high priority)
- Organization-specific training or staffing adjustments needed
- Opportunity for threshold-based automation

### 4. Data Infrastructure Gaps

**Summary**: Critical timestamp data missing in source systems, requiring complex workarounds

**Detailed Findings**:
- **Critical gap**: Native event timestamps missing in core transactional and financial systems
- **Impact**: Process mining not feasible without cross-system integration and derived timestamps
- **Workaround implemented**: Attribute-based mapping using workflow/approval system as bridge
  - Achieved **~70%+** event coverage
  - Required non-trivial data transformation logic
  - Manual validation and reconciliation needed

**Implications**:
- Current architecture **not optimized** for process analytics (high-risk for scalability)
- Enterprise-wide event logging standards required
- Significant manual effort needed for ongoing analysis without remediation

---

## Business Impact & Recommendations

### Immediate Operational Improvements

#### 1. Workflow Optimization

**Action**: Expand simplified approval workflows to additional low-value purchase categories

**Implementation**:
- Increase transaction amount threshold for simplified process
- Reduce approval steps for routine, low-risk purchases
- Implement categorical exemptions (e.g., routine supplies, standard services)

**Expected Impact**:
- **~30–40%** reduction in overall procurement lead time
- Reduced administrative burden on approval stakeholders
- Improved user satisfaction with procurement process

**Timeline**: 0–3 months

---

#### 2. Bottleneck Resolution

**Action**: Implement automated approval thresholds for routine purchases

**Implementation**:
- Define rule-based auto-approval criteria (amount, category, vendor)
- Deploy pre-approved vendor framework for recurring purchases
- Establish escalation protocols for exceptions

**Expected Impact**:
- Address **~35–45%** of long-duration cases
- **~50%+** reduction in approval waiting time for eligible transactions
- Free up approval capacity for high-value/high-risk transactions

**Timeline**: 3–6 months

---

#### 3. Compliance Enhancement

**Action**: Deploy pre-submission validation checks to reduce non-conformance

**Implementation**:
- System-enforced workflow sequence validation
- Mandatory field completion before advancement
- Real-time compliance alerts to users

**Expected Impact**:
- Reduce non-conformance rate from **~15–20%** to **&lt;5%**
- Minimize audit exposure and compliance risk
- Improve data quality and completeness

**Timeline**: 3–6 months

---

### Strategic Process Mining Roadmap

#### Phase 1: Customer-Facing Process Analytics (6–12 months)

**Scope**: End-to-end customer-facing process (e.g., inquiry-to-conversion journey)

**Key Metrics**:
- Conversion rate and lead time by segment
- Drop-off points in funnel
- Customer satisfaction correlation with process efficiency

**Expected Value**:
- Identify friction points in conversion funnel
- Optimize customer touchpoints
- Increase conversion rate and revenue

**Prerequisites**:
- Customer interaction event logging
- Integration with CRM and transactional systems

---

#### Phase 2: Risk & Compliance Monitoring (6–12 months)

**Scope**: Fraud detection, audit compliance, information security

**Key Metrics**:
- Abnormal transaction detection rate
- Policy adherence by process and department
- Risk incident occurrence and resolution time
- Audit finding trends

**Expected Value**:
- Real-time risk identification and mitigation
- Proactive compliance management
- Reduced audit findings and regulatory exposure

**Prerequisites**:
- Risk event taxonomy definition
- Integration with security and audit systems

---

#### Phase 3: HR Process Optimization (12+ months)

**Scope**: Recruitment, onboarding, performance management

**Key Metrics**:
- Time-to-hire by role and department
- Onboarding completion rate and duration
- Employee turnover drivers and patterns
- Promotion and advancement cycle times

**Expected Value**:
- Improve talent acquisition efficiency
- Enhance employee retention
- Data-driven HR policy optimization

**Prerequisites**:
- HR system event logging capability
- Privacy and compliance framework for employee data

---

### Data Governance Framework

#### Problem Statement

Enterprise systems lacked consistent event logging, preventing native process mining capability and requiring significant manual intervention for analysis.

#### Proposed Solution Architecture

**1. Event Logging Standards**
- Define enterprise-wide event schema (case ID, activity, timestamp, actor, system)
- Implement standardized logging across business-critical systems
- Establish event granularity requirements by process type

**2. Data Quality Framework**
- **Completeness**: All process steps must generate events with required attributes
- **Timeliness**: Events logged in real-time or near-real-time (e.g., &lt;1 hour delay)
- **Consistency**: Standardized field formats, naming conventions, and data types
- **Accuracy**: Validation rules to prevent invalid or contradictory data entry

**3. Automated Data Validation**
- Real-time data quality monitoring dashboards
- Automated alerts for missing or anomalous events
- Scheduled data reconciliation jobs across systems

**4. Cross-System Integration Framework**
- Master data management for common entities (vendors, employees, departments)
- API-based event streaming between systems
- Centralized analytics layer for process mining

#### Implementation Roadmap

| Phase | Timeline | Deliverables |
|-------|----------|--------------|
| **Assessment** | Month 1–2 | Current state analysis, gap identification, stakeholder alignment |
| **Design** | Month 3–4 | Event logging standards, data model, integration architecture |
| **Pilot** | Month 5–7 | Implement in 1–2 pilot systems, validate approach |
| **Rollout** | Month 8–12 | Broader implementation, training, change management |
| **Optimization** | Ongoing | Continuous improvement, expanded analytics use cases |

#### Long-Term Value

- **Process Visibility**: Real-time monitoring of business processes
- **Continuous Improvement**: Data-driven optimization culture
- **Scalability**: Foundation for AI/ML-based process automation
- **Compliance**: Audit trail and regulatory compliance capability

---

## Technical Skills Demonstrated

### Process Mining & Analytics

| Skill | Application in Project |
|-------|------------------------|
| **Event Log Reconstruction** | Built unified event log from multiple disparate systems with ~70%+ coverage |
| **Process Conformance Checking** | Validated ~80–85% adherence to standard workflow, identified multiple deviation types |
| **Root Cause Analysis** | Identified approval stage as primary driver of ~35–45% of long-duration cases |
| **Statistical Correlation Analysis** | Proved inverse relationship between transaction size and processing speed |
| **Process Pattern Recognition** | Classified non-conforming cases into distinct violation taxonomies |
| **Temporal Analysis** | Decomposed lead time into processing vs. waiting time components |

### Data Engineering

| Skill | Application in Project |
|-------|------------------------|
| **Multi-System Integration** | Integrated procurement, workflow, and financial systems with different schemas |
| **Data Mapping & Transformation** | Implemented attribute-based matching for cross-system record linkage |
| **Timestamp Reconstruction** | Generated missing event timestamps using workflow/approval system timestamps |
| **Data Quality Assessment** | Applied completeness criteria; filtered to analyzable subset from larger source population |
| **Event Schema Design** | Standardized field names, formats, and data types across heterogeneous sources |
| **Data Validation Logic** | Removed duplicates, invalid activities, and non-identifiable records |

### Business Analysis

| Skill | Application in Project |
|-------|------------------------|
| **Requirement Gathering** | Defined analytical scenarios aligned with stakeholder priorities |
| **KPI Framework Design** | Proposed industry-aligned KPIs for enterprise value chain |
| **Strategic Roadmap Planning** | Developed multi-phase expansion plan with timeline and resource requirements |
| **Stakeholder Communication** | Presented findings with fact-checking validation sessions |
| **Business Case Development** | Quantified ROI for workflow simplification and automation initiatives |
| **Change Management** | Recommended data governance framework with implementation roadmap |

### Tools & Technologies

| Category | Tools | Proficiency Demonstrated |
|----------|-------|--------------------------|
| **Process Mining** | Process mining software | Discovery, conformance checking, variant analysis, temporal charts |
| **Data Processing** | Python (pandas, numpy) | Data cleaning, transformation, merging, statistical analysis |
| **Data Visualization** | Matplotlib, process diagrams | Cycle time charts, correlation plots, process flow maps |
| **Systems** | ERP / procurement / workflow / financial platforms | Cross-system data extraction, schema mapping |

---

## Documentation

### Project Deliverables

- **Sample case documentation** (see repository for available assets) — Analysis overview with approach and generalized findings.

### Repository Structure

```
process-mining-portfolio/
├── README.md
├── .gitignore
└── docs/
    └── Process_Analytics_Portfolio_Sanitized.pdf
---

## Confidentiality Note

This portfolio illustrates work from a process analytics engagement with an enterprise client. Identifying details, exact metrics, and proprietary references have been generalized; comparative insights and impact magnitudes are preserved for portfolio purposes.

---

## Contact

**Minwoo Park**

- **Email**: [Minwoo.Park219@gmail.com](mailto:Minwoo.Park219@gmail.com)
- **Phone**: +1 (706) 461-3489
- **LinkedIn**: [linkedin.com/in/mp74484](https://www.linkedin.com/in/mp74484/)

---

**Last Updated**: January 2026