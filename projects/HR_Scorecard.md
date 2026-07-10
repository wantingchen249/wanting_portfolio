# Project: Enterprise HR Scorecard & Analytics Dashboard Suite

---

## Frontmatter

```yaml
title: "Enterprise HR Scorecard & Analytics Dashboard Suite"
category: "HR Analytics · Business Intelligence"
tags: [Power BI, Microsoft Fabric, DAX, SQL, Data Governance, HR Analytics]
status: "Completed"
year: 2024
impact_metric: "40% reduction in manual HR reporting time"
technologies: [Power BI, Microsoft Fabric, DAX, Power Query, SQL, Row-Level Security]
```

---

## 1. Overview

Designed and deployed a comprehensive HR Scorecard and Analytics Dashboard Suite using Power BI and Microsoft Fabric, providing real-time visibility into headcount, turnover, diversity, compensation, and workforce planning metrics across global regions. The solution replaced fragmented, manual Excel-based reporting and established a single source of truth for HR data consumed by 200+ HR professionals worldwide.

---

## 2. Business Context & Challenge

### Organisational Situation
The HR function was managing a workforce spread across 5+ global regions, but reporting was fragmented across multiple teams, each maintaining their own Excel files, local SQL queries, and ad-hoc PowerPoint decks. Monthly headcount reports took 5 full working days to compile; by the time leadership reviewed them, the data was already stale.

### Core Problems
- **No single source of truth:** 7 different data sources (HRIS, payroll, LMS, ATS, Finance) with inconsistent definitions.
- **Manual, error-prone processes:** Report production consumed 40% of the HR analytics team's capacity each month.
- **No self-serve capability:** Every data question required a ticket to the central team — creating bottlenecks.
- **Inconsistent KPI definitions:** "Headcount" was calculated differently across regions; "turnover" had 3 competing formulas.
- **No governance:** No documented data dictionary; data lineage was unknown.

### Stakeholder Landscape
- **Primary consumers:** HR Business Partners, CHRO, Regional HR Directors
- **Data providers:** HRIS team, Payroll, Finance, IT
- **Sponsors:** CHRO, VP of HR Operations

---

## 3. My Role & Approach

**Role:** Lead BI Architect & Project Manager

### Phase 1 — Discovery & Requirements (Weeks 1–4)
- Conducted 15+ stakeholder interviews to capture reporting needs, pain points, and KPI definitions.
- Audited existing reports to catalogue all KPIs, source systems, and refresh frequencies.
- Facilitated a KPI alignment workshop with global HR leadership to standardise definitions.
- Produced a Business Requirements Document (BRD) and data dictionary (v1).

### Phase 2 — Data Architecture (Weeks 5–8)
- Designed a **star schema semantic model** in Microsoft Fabric, with fact tables for headcount snapshots, events (hires/terms/transfers), and payroll, linked to shared dimension tables (employee, org, date, geography).
- Built **Power Query ETL pipelines** to ingest and transform data from HRIS (API), payroll (SFTP), and Finance (SQL Server).
- Implemented **Row-Level Security (RLS)** aligned to HR org hierarchy — regional HR leads see only their data; CHRO sees all.

### Phase 3 — Dashboard Development (Weeks 9–14)
- Built 6 core report pages: Headcount Snapshot, Movement (joins/leaves/transfers), Turnover Analysis, Diversity & Inclusion, Compensation Overview, Workforce Planning (with what-if parameters).
- Applied design system: consistent colour palette, typography, navigation, and UX patterns across all pages.
- Created a **Metrics Glossary page** within the report as embedded documentation.

### Phase 4 — Testing & Governance (Weeks 15–17)
- Executed UAT with 12 HR stakeholders across 4 regions; resolved 34 feedback items.
- Documented data lineage, refresh schedule, and ownership in the HR Data Catalogue.
- Set up automated refresh (daily) and alerting for data pipeline failures.

### Phase 5 — Rollout & Enablement (Weeks 18–20)
- Delivered 4 training sessions for 200+ HR users across time zones.
- Created self-service documentation: user guide, KPI glossary, FAQ.
- Established a monthly governance review cycle with data stewards.

---

## 4. Technical Architecture

```
Data Sources
  ├── HRIS Platform (API / REST) ──────────────────────────┐
  ├── Payroll System (SFTP / CSV) ────────────────────────── ▼
  ├── Finance / Headcount Budget (SQL Server) ──► Power Query ETL
  ├── LMS (API) ───────────────────────────────────────────── ▼
  └── ATS (CSV export) ──────────────────────────── Microsoft Fabric Lakehouse
                                                              │
                                              Star Schema Semantic Model
                                         (Fact: Headcount, Events, Payroll)
                                         (Dim: Employee, Org, Date, Geo)
                                                              │
                                                   Power BI Service
                                              ┌────────────────────────┐
                                              │  HR Scorecard App      │
                                              │  - Headcount           │
                                              │  - Movement            │
                                              │  - Turnover            │
                                              │  - D&I                 │
                                              │  - Compensation        │
                                              │  - Workforce Planning  │
                                              └────────────────────────┘
                                                     Row-Level Security
                                               (Per HR org hierarchy role)
```

---

## 5. Key Deliverables

- ✅ Unified HR Semantic Model in Microsoft Fabric (star schema, 5 fact tables, 8 dimension tables)
- ✅ Power BI HR Scorecard App (6 report pages + metrics glossary)
- ✅ Row-Level Security model (12 security roles)
- ✅ Automated daily refresh pipeline with failure alerting
- ✅ HR Data Dictionary v1 (87 KPI definitions)
- ✅ Training programme (4 sessions, 200+ participants)
- ✅ Self-service user guide and FAQ
- ✅ Governance calendar (monthly data steward reviews)

---

## 6. Outcomes & Impact

| Metric | Before | After | Change |
|---|---|---|---|
| Monthly report production time | 5 working days | Same-day (automated) | **−96%** |
| HR analytics team capacity consumed by reporting | ~40% | ~5% | **−35 pp** |
| Number of self-serve users | 0 | 200+ | **+200** |
| KPI definition alignment | 3 competing formulas | 1 agreed standard | **✅ Unified** |
| Data freshness | Monthly | Daily | **30x faster** |
| Report error rate | ~15% (human error) | < 1% | **−14 pp** |
| Stakeholder satisfaction (post-launch survey) | N/A | 4.6 / 5.0 | **New baseline** |

**Executive Headline:** *40% reduction in HR analytics team overhead; same-day headcount visibility for global HR leadership.*

---

## 7. Lessons Learned

1. **KPI alignment is the hardest part.** Technical build was straightforward; getting 12 regional HR leads to agree on one turnover definition took 3 workshops. Invest early in governance, not just engineering.
2. **RLS design must precede data modelling.** Adding security logic after the model is built is expensive; design the org hierarchy model from day one.
3. **Training format matters.** Self-paced documentation alone achieved 40% adoption; live, role-specific sessions pushed it to 90%+.
4. **Embed the glossary in the report.** A linked Metrics Glossary page reduced "what does this mean?" tickets by an estimated 70%.

---

## 8. Technologies Used

`Power BI` · `Microsoft Fabric` · `Lakehouse` · `Dataflows Gen2` · `DAX` · `Power Query / M` · `SQL Server` · `REST API connectors` · `Row-Level Security` · `Power BI Service` · `Deployment Pipelines`

---

*Last updated: 2026-07-10*
