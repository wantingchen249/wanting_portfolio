# Project: LMS Modernisation & Learning Analytics Implementation

---

## Frontmatter

```yaml
title: "LMS Modernisation & Learning Analytics Implementation"
category: "Learning Technology · System Implementation"
tags: [LMS, Power BI, Change Management, System Integration, L&D Analytics, HRIS]
status: "Completed"
year: 2023
impact_metric: "35% increase in training completion rate"
technologies: [LMS Platform, Power BI, API Integration, Power Automate, SharePoint]
```

---

## 1. Overview

Led the end-to-end evaluation, procurement, and implementation of a modern Learning Management System (LMS) to replace a legacy platform that had been in use for 8+ years. The project included data migration, HRIS integration, a Power BI learning analytics dashboard, and a comprehensive change management programme — resulting in a 35% increase in training completion rates and full L&D ROI visibility for senior leadership.

---

## 2. Business Context & Challenge

### Organisational Situation
The organisation's existing LMS had reached end-of-life. The platform offered no mobile access, poor user experience, and zero analytics capability. L&D reported completion rates anecdotally. Compliance training tracking was manual — a significant audit and regulatory risk.

### Core Problems
- **Poor learner experience:** Desktop-only, slow, unintuitive interface driving low engagement and completion.
- **No analytics:** No data on completion rates, time-to-complete, repeat attempts, or learning effectiveness.
- **Manual compliance tracking:** Compliance training records managed in spreadsheets; audit preparation took weeks.
- **No HRIS integration:** Employee data (name, role, department, region) required manual upload to the LMS monthly — causing data drift and errors.
- **No ROI visibility:** L&D budget was significant; leadership had no view of return on investment.

### Stakeholder Landscape
- **Sponsors:** CHRO, Chief Learning Officer (CLO), CFO (budget holder)
- **Users:** 5,000+ employees across 5 regions; L&D team of 12
- **Dependent teams:** IT, HR, Legal/Compliance, Finance

---

## 3. My Role & Approach

**Role:** Project Manager & HRIS Integration Lead

### Phase 1 — Discovery & Requirements (Weeks 1–6)
- Facilitated requirements workshops with L&D, HR, IT, Legal, and Finance.
- Conducted learner experience surveys (N=320) to capture end-user pain points.
- Produced a Requirements Specification covering 68 functional and 14 non-functional requirements.
- Mapped all existing courses (420+), completion records, and compliance curricula for migration scope.

### Phase 2 — Vendor Evaluation & Procurement (Weeks 7–14)
- Designed a structured RFP scoring framework (technical capability 40%, UX 25%, integration 20%, cost 15%).
- Managed RFP process with 6 vendors; coordinated 4 demos and 3 reference calls.
- Led procurement negotiation; achieved 18% cost reduction from initial vendor quote.
- Produced vendor evaluation matrix and executive recommendation deck for CHRO sign-off.

### Phase 3 — Implementation & Integration (Weeks 15–28)
- Managed vendor delivery team (8 people) + internal IT integration lead.
- Designed and tested HRIS→LMS automated data sync (employee profile updates pushed daily via API).
- Built course migration process: 420 courses audited → 310 migrated, 110 retired.
- Designed and deployed compliance tracking module with automated email reminders (Power Automate).
- Created enrolment automation rules: mandatory training auto-assigned by role/region/grade.

### Phase 4 — Analytics Build (Weeks 25–30)
- Built a Power BI Learning Analytics Dashboard connected to LMS API:
  - **Completion Rate by Course / Team / Region / Grade**
  - **Compliance Status (RAG rating per employee)**
  - **Time-to-Complete Trends**
  - **Learning Hours by Business Unit**
  - **Training ROI Estimates** (cost per completion vs. average programme cost)
- Implemented automated weekly email digests to L&D leads with completion summaries.

### Phase 5 — Change Management & Go-Live (Weeks 28–34)
- Developed change management plan covering comms, training, and support.
- Delivered 8 "New LMS" roadshows across regions (virtual + in-person); 1,200+ employees reached.
- Created role-specific quick-start guides in 2 languages (English + Mandarin).
- Managed a 4-week parallel-run period before legacy system decommission.
- Monitored adoption metrics weekly; ran targeted outreach for low-adoption teams.

---

## 4. Technical Architecture

```
Data Flows
  HRIS (Workday) ──── daily API sync ──── LMS (Employee Profile)
                                                │
                        Course Enrolment Rules (auto-assign)
                        Compliance Module (tracking + alerts)
                        Power Automate (email reminders)
                                                │
                               LMS API / Reporting DB
                                                │
                                       Power BI Dashboard
                              (Completion · Compliance · ROI · Trends)
                                                │
                              SharePoint Embedded (L&D Portal)
                         + Automated Weekly Email Digest (Power Automate)
```

---

## 5. Key Deliverables

- ✅ LMS Vendor Selection (RFP, evaluation matrix, board recommendation)
- ✅ HRIS↔LMS automated daily sync (API integration, error handling, reconciliation)
- ✅ Course migration: 310 courses, 420+ completion records migrated
- ✅ Compliance tracking module with role-based mandatory training rules
- ✅ Power Automate: reminder flows, manager escalation, digest reports
- ✅ Power BI Learning Analytics Dashboard (5 pages, 30+ measures)
- ✅ Change management programme: 8 roadshows, 1,200+ employees reached
- ✅ Quick-start guides (English + Mandarin)
- ✅ Legacy system decommission (on schedule)

---

## 6. Outcomes & Impact

| Metric | Before | After | Change |
|---|---|---|---|
| Training completion rate (overall) | ~52% | ~70% | **+35% (rel.)** |
| Compliance training completion (regulated courses) | 71% | 96% | **+25 pp** |
| Time to prepare compliance audit report | 3 weeks manual | 2 hours (automated) | **−95%** |
| HRIS data sync to LMS | Monthly manual upload | Daily automated | **30x faster** |
| L&D analytics visibility | None | Full dashboard | **New capability** |
| Employee NPS on learning platform | N/A (no baseline) | +42 | **New baseline** |
| Vendor cost vs. initial quote | Budgeted | −18% | **Cost saving** |

**Executive Headline:** *35% increase in training completion; compliance audit time reduced from 3 weeks to 2 hours; full L&D ROI visibility established for the first time.*

---

## 7. Lessons Learned

1. **Retire ruthlessly.** We initially planned to migrate all 420 courses. Auditing revealed 26% were outdated, duplicated, or unused. Retiring them reduced migration cost and improved learner experience. Always audit before migrating.
2. **Integration is the critical path.** The HRIS→LMS sync was the most complex dependency. Starting integration design in Week 10 (not Week 15) would have saved 2 weeks of delay.
3. **Compliance tracking drives adoption.** When leadership realised the system could produce live compliance dashboards, engagement at the executive level increased significantly — unlocking budget for Phase 2 analytics.
4. **Language matters.** Adding Mandarin-language guides increased adoption in APAC teams by an estimated 20 percentage points above forecast.

---

## 8. Technologies Used

`LMS Platform (vendor-specific)` · `Power BI` · `Power Automate` · `Workday (HRIS)` · `REST API` · `SharePoint` · `SQL (LMS reporting DB)` · `DAX` · `Power Query` · `Microsoft 365`

---

*Last updated: 2026-07-10*
