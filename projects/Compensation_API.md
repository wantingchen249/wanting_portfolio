# Project: Compensation Data API & Governance Framework

---

## Frontmatter

```yaml
title: "Compensation Data API & Governance Framework"
category: "System Integration · Data Governance · Compensation Analytics"
tags: [API Integration, Data Governance, Compensation, SQL, Power BI, HRIS, GDPR]
status: "Completed"
year: 2024
impact_metric: "100% data compliance; real-time compensation data flow across 5 systems"
technologies: [REST API, SQL, Power BI, Microsoft Purview, Azure Logic Apps, Workday]
```

---

## 1. Overview

Designed and implemented a Compensation Data API integration layer connecting the HRIS, payroll, Finance (budgeting), benchmarking, and BI systems — replacing a fragile web of manual file transfers and scheduled batch processes. The project included a full data governance framework for compensation data, achieving 100% GDPR compliance and enabling real-time compensation analytics for the first time.

---

## 2. Business Context & Challenge

### Organisational Situation
Compensation data was among the most sensitive and most fragmented data in the organisation. Pay data lived in the HRIS, actuals in payroll, budgets in Finance, benchmarks in a third-party platform, and reporting in Excel. Each system spoke a different language. Reconciliation at year-end was a month-long exercise in manually aligning numbers that should have agreed automatically.

### Core Problems
- **Fragmented data flows:** Compensation data moved between 5 systems via scheduled CSV exports and manual uploads — creating version drift and reconciliation nightmares.
- **Latency:** Pay change approvals in the HRIS took up to 72 hours to appear in payroll; Finance had no view of approved changes before month-end close.
- **No governance:** No documented data owner for compensation data; different definitions of "base salary" across HR, Finance, and Payroll.
- **GDPR exposure:** Compensation data was emailed between teams in unencrypted Excel files; no audit trail existed.
- **No analytics:** Compensation analysis was done in Excel; no benchmarking integration; no pay equity view.

### Stakeholder Landscape
- **Sponsors:** CHRO, CFO, Chief Privacy Officer
- **Consumers:** HR Operations, Compensation & Benefits, Finance (FP&A), Legal
- **Data owners:** HRIS team (source system), Payroll (actuals), Finance (budgets)

---

## 3. My Role & Approach

**Role:** Project Lead — Integration Architecture, Data Governance, Analytics

### Phase 1 — Discovery & Data Mapping (Weeks 1–5)
- Mapped all compensation data flows across 5 systems; documented 23 distinct data movement paths.
- Conducted data quality audit: identified 4 field definition mismatches ("base salary" vs. "annual equivalent" vs. "FTE salary") and 2,400 employee records with mismatched job codes across HRIS and payroll.
- Produced a **Data Flow Diagram** and **Compensation Data Dictionary** (42 fields, agreed definitions, data owners).
- Engaged Legal and Privacy teams to map GDPR obligations against each data flow.

### Phase 2 — API Architecture Design (Weeks 6–10)
- Designed a **hub-and-spoke API architecture** with the HRIS as the master system of record.
- HRIS exposes a secure REST API for approved pay changes; consuming systems subscribe to events.
- Designed **data contracts** (JSON schema) for each integration point, versioned and documented.
- Implemented field-level encryption for sensitive compensation fields in transit and at rest.
- Designed an **audit log schema** capturing every compensation data access and modification event.

### Phase 3 — Integration Build (Weeks 11–22)
- Built HRIS→Payroll real-time sync: pay changes approved in HRIS trigger immediate API call to payroll system; confirmation logged.
- Built HRIS→Finance integration: approved headcount and compensation changes pushed to FP&A system nightly, enabling real-time budget vs. actual tracking.
- Built HRIS→Benchmarking platform: anonymised job-level compensation data synced monthly to external benchmarking provider (GDPR-compliant, field-masked).
- Built HRIS→Power BI: live connection via Fabric semantic model for compensation analytics.
- Implemented error handling, retry logic, and dead-letter queues for all integration paths.

### Phase 4 — Data Governance Framework (Weeks 18–25)
- Published the **Compensation Data Governance Policy** (data classification, access control matrix, retention periods).
- Implemented **Microsoft Purview** for data cataloguing, lineage documentation, and sensitivity labelling on all compensation data assets.
- Established **RBAC** (Role-Based Access Control) at the field level: only authorised roles can view salary data in Power BI.
- Created a **Privacy Impact Assessment (PIA)** for each integration, reviewed and signed off by the Chief Privacy Officer.
- Designed automated **GDPR audit reports** in Power BI — who accessed what data, when, and why.

### Phase 5 — Analytics & Reporting (Weeks 23–28)
- Built Compensation Analytics Dashboard in Power BI:
  - **Pay Equity Analysis** (gender, grade, region — with statistical significance indicators)
  - **Benchmarking View** (internal vs. external market data by job family)
  - **Budget vs. Actuals** (real-time Finance integration)
  - **Compensation Change Tracker** (all approved changes with audit trail)
- Applied field-level RLS: Finance sees budget/actuals but not individual salaries; HR Business Partners see their population only.

---

## 4. Technical Architecture

```
                     ┌──────────────────────────────────┐
                     │    HRIS (Master System)           │
                     │    Workday — Pay Change Events    │
                     └──────────────┬───────────────────┘
                                    │ REST API (HTTPS, OAuth 2.0)
              ┌─────────────────────┼──────────────────────┐
              ▼                     ▼                        ▼
      Payroll System        Finance (FP&A)          Benchmarking Platform
     (Real-time sync)      (Nightly delta)          (Monthly, anonymised)
              │                     │
              └──────────┬──────────┘
                         ▼
               Microsoft Fabric / Lakehouse
               (Compensation Semantic Model)
                         │
                  Power BI Analytics
            ┌────────────────────────────┐
            │  Pay Equity · Benchmarking │
            │  Budget vs. Actuals        │
            │  Audit Trail               │
            └────────────────────────────┘
                   Row-Level Security
              Microsoft Purview (Lineage + Labels)
                  Audit Log → GDPR Reports
```

---

## 5. Key Deliverables

- ✅ Compensation Data Dictionary (42 field definitions, agreed by HR / Finance / Legal)
- ✅ Hub-and-spoke REST API architecture (5 integration paths)
- ✅ HRIS→Payroll real-time sync with audit logging
- ✅ HRIS→Finance nightly delta integration
- ✅ HRIS→Benchmarking monthly anonymised export (GDPR-compliant)
- ✅ Microsoft Purview data catalogue with lineage and sensitivity labels
- ✅ Compensation Data Governance Policy
- ✅ Privacy Impact Assessments (one per integration path)
- ✅ RBAC model (7 security roles across 5 systems)
- ✅ Power BI Compensation Analytics Dashboard (4 pages, 50+ measures)
- ✅ Automated GDPR audit reports

---

## 6. Outcomes & Impact

| Metric | Before | After | Change |
|---|---|---|---|
| Pay change latency (HRIS→Payroll) | Up to 72 hours | Real-time (<5 min) | **−99%** |
| Year-end compensation reconciliation time | ~4 weeks | ~2 days | **−88%** |
| GDPR compliance status | Undocumented | 100% compliant | **✅ Achieved** |
| Data breach risk (unencrypted email) | Active exposure | Eliminated | **✅ Resolved** |
| Audit trail coverage | 0% | 100% | **Full coverage** |
| Pay equity analysis availability | Ad-hoc (quarterly) | Real-time | **New capability** |
| Budget vs. actuals freshness | Monthly (T+4 weeks) | Daily (T+0) | **28x faster** |

**Executive Headline:** *100% GDPR compliance achieved; compensation data latency reduced from 72 hours to real-time; 4-week year-end reconciliation reduced to 2 days.*

---

## 7. Lessons Learned

1. **Start with the data dictionary.** The 3 weeks spent aligning 42 field definitions saved months of integration rework. When HR says "base salary" and Finance says "annual equivalent," they mean different things. Document it before you build.
2. **Privacy by design, not by retrofit.** Engaging the Chief Privacy Officer in Week 2 (not Week 20) meant architectural decisions — encryption, anonymisation, access control — were built in from the start, not bolted on.
3. **Audit logging is a feature, not overhead.** When leadership saw a real-time audit trail showing every compensation data access, it changed the culture around data responsibility. Governance became a selling point, not a constraint.
4. **Finance partnership accelerates adoption.** Solving the budget vs. actuals problem for Finance — a pain they'd had for years — made them strong advocates for the project across the business.

---

## 8. Technologies Used

`REST API (OAuth 2.0)` · `JSON Schema` · `Workday (HRIS)` · `SQL` · `Microsoft Fabric` · `Power BI` · `DAX` · `Power Query` · `Microsoft Purview` · `Azure Logic Apps` · `Row-Level Security` · `GDPR / Privacy frameworks`

---

*Last updated: 2026-07-10*
