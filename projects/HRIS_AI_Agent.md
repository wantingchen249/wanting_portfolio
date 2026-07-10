# Project: HRIS AI Service Agent (Copilot Studio)

---

## Frontmatter

```yaml
title: "HRIS AI Service Agent — Copilot Studio Implementation"
category: "AI Innovation · HR Automation · Digital Transformation"
tags: [AI Agents, Copilot Studio, Power Automate, SharePoint, HRIS, HR Automation, Chatbot]
status: "Completed"
year: 2025
impact_metric: "60% deflection of tier-1 HR queries; 24/7 employee self-service"
technologies: [Microsoft Copilot Studio, Power Automate, SharePoint, Azure OpenAI, Power BI, Teams]
```

---

## 1. Overview

Designed and deployed an AI-powered HR Service Agent using Microsoft Copilot Studio, integrated with the HRIS, SharePoint knowledge base, and Power Automate workflows. The agent handles employee HR enquiries — policy lookups, payslip access, leave balances, onboarding checklists, and benefit queries — autonomously, 24/7. It deflects 60% of tier-1 HR shared-services queries, freeing HR specialists to focus on strategic and complex casework.

---

## 2. Business Context & Challenge

### Organisational Situation
The HR Shared Services team was handling 2,000–2,500 employee enquiries per month. Analysis showed that 62% of these queries were repetitive, tier-1 questions — things like "How do I apply for parental leave?", "What is the medical benefit limit?", "Where do I find my payslip?", or "What's the onboarding checklist for my new team member?"

Every query consumed 8–15 minutes of HR specialist time. Response SLAs were 24–48 hours, causing employee frustration. During peak periods (open enrolment, year-end), the team was overwhelmed.

### Core Problems
- **Volume and repetitiveness:** 62% of queries were answerable without human judgement.
- **SLA pressure:** 24–48 hour response times eroded employee experience scores.
- **No 24/7 support:** Employees in different time zones could not get answers outside office hours.
- **Inconsistent answers:** Different HR specialists sometimes gave different answers to the same policy question.
- **Specialist capacity waste:** HR professionals with advanced expertise were spending hours answering "where is the leave form?"

### Stakeholder Landscape
- **Sponsors:** VP of HR Operations, CHRO
- **Users:** All employees (~5,000); HR Shared Services team (15 specialists)
- **Technical partners:** IT (M365 / Azure), Legal (policy content owner)
- **Integration points:** HRIS (leave balances, org data), SharePoint (policy documents), Payroll (payslip links)

---

## 3. My Role & Approach

**Role:** AI Solution Architect & Project Lead

### Phase 1 — Use Case Scoping & Ticket Analysis (Weeks 1–4)
- Analysed 6 months of HR ticket data (14,800 tickets) — categorised by type, volume, resolution time, and complexity.
- Identified top 20 query types representing 62% of total volume — all tier-1, policy/process-based.
- Defined **agent scope:** 20 automated use cases for Phase 1; complex casework remains with humans.
- Built a **decision tree** for escalation logic: what the agent handles vs. what it routes to a human.
- Stakeholder alignment session with HR leadership to confirm scope and risk appetite.

### Phase 2 — Knowledge Base Design (Weeks 5–8)
- Audited existing HR policy library: 140 policy documents across 5 regions — many outdated or duplicated.
- Ran a "Policy Cleanse Sprint" with Legal and HR: reduced to 85 approved, current documents.
- Structured documents for AI retrieval: clear headings, consistent formatting, metadata tagging (region, topic, effective date).
- Published to a dedicated SharePoint site with strict version control and quarterly review schedule.
- Designed a **Knowledge Confidence Model** — the agent indicates when it is referencing a policy document vs. synthesising an answer, and always cites the source.

### Phase 3 — Agent Build in Copilot Studio (Weeks 9–18)
- Designed 20 agent "topics" — each maps to a query category (leave, benefits, payslip, onboarding, etc.).
- Built natural language triggers for each topic with multi-intent recognition (an employee asking about both leave and payslip in one message).
- Integrated **SharePoint knowledge base** as the grounding source — agent retrieves and summarises policy content.
- Built **HRIS API integration**: agent authenticates as the employee and retrieves their personal HR data (leave balance, employment details, org chart).
- Built **Power Automate flows** for action-based responses:
  - Submit leave request (HRIS API call)
  - Send onboarding checklist (automated email)
  - Escalate complex cases (Teams notification to HR Specialist + ticket creation)
- Implemented **language detection**: English and Mandarin Chinese supported; agent responds in the detected language.
- Built **adaptive cards** in Teams: rich formatted responses with action buttons (not just text).

### Phase 4 — Safety, Compliance & Escalation Design (Weeks 16–20)
- Designed mandatory escalation triggers: any query involving performance management, disciplinary action, or HR investigation routes immediately to a named HR Business Partner.
- Implemented **response confidence thresholds**: if the AI's confidence score falls below 0.75, it escalates rather than guessing.
- Built a **Content Safety filter** using Azure AI Content Safety: screens all agent outputs before delivery.
- Engaged Legal to review and approve all policy-sourced responses for accuracy.
- Designed a **fallback conversation path** that always offers a "speak to a human" option.

### Phase 5 — Pilot & Refinement (Weeks 20–26)
- Ran a 6-week pilot with 500 employees (10% of workforce) across 2 regions.
- Collected feedback via a 3-question post-conversation micro-survey (satisfaction, resolution, clarity).
- Reviewed all escalated conversations weekly — identified 8 topic gaps; built 4 new topics; improved 6 existing flows.
- Deflection rate in pilot: 54% (target: 50%). Quality score: 4.2/5.0.

### Phase 6 — Full Deployment & Monitoring (Weeks 26–30)
- Deployed to all 5,000 employees via Microsoft Teams (accessible on mobile and desktop).
- Published as a SharePoint embedded widget on the HR Portal.
- Built a **Power BI Operations Dashboard** for HR leadership:
  - Daily / weekly query volume and deflection rate
  - Topic distribution (what employees ask most)
  - Escalation rate and reason classification
  - Response satisfaction scores
  - Knowledge base coverage gaps (unanswered query clustering)
- Established weekly agent review cadence: HR Ops reviews new query clusters; Legal reviews any policy-adjacent responses; IT monitors performance.

---

## 4. Technical Architecture

```
Employee (Teams / HR Portal)
          │
          ▼
  Microsoft Copilot Studio
  ┌─────────────────────────────────────────┐
  │  Topic Router (NLU + Intent Detection)  │
  │  20 Topics: Leave · Benefits · Payslip  │
  │  Onboarding · Policy · Org Chart · ...  │
  └──────────────────┬──────────────────────┘
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
  SharePoint     HRIS API      Power Automate
  (Policy KB)  (Personal HR    (Actions: submit
                  data)         leave, send docs,
                                escalate to human)
       │             │             │
       └─────────────┴─────────────┘
                     │
            Azure AI Content Safety
            (Output screening)
                     │
            Response to Employee
            (Adaptive Card in Teams)
                     │
            Satisfaction Survey (3Q)
                     │
            Power BI Ops Dashboard
            (Deflection · CSAT · Topics)
```

---

## 5. Key Deliverables

- ✅ 20 agent topics (full build, tested, live)
- ✅ Policy knowledge base (85 documents, structured, version-controlled)
- ✅ HRIS API integration (authenticated personal data retrieval)
- ✅ Power Automate flows (leave submission, onboarding, escalation)
- ✅ Language support: English + Mandarin Chinese
- ✅ Azure AI Content Safety integration
- ✅ Escalation framework (mandatory + confidence-based)
- ✅ Power BI Operations Dashboard
- ✅ Post-conversation satisfaction survey
- ✅ Weekly governance review process

---

## 6. Outcomes & Impact

| Metric | Before | After | Change |
|---|---|---|---|
| Tier-1 HR queries handled by human | ~62% of 2,000–2,500/month | ~25% | **−60% (rel.)** |
| Average HR query response time | 24–48 hours | < 2 minutes | **−97%** |
| 24/7 availability | Business hours only | 24/7 | **New capability** |
| Employee satisfaction (HR service) | 3.4 / 5.0 | 4.3 / 5.0 | **+0.9 points** |
| HR specialist capacity freed | 0 | ~18 hrs/week | **New capacity** |
| Policy answer consistency | Variable | 100% sourced | **Standardised** |
| Language support | English only | EN + ZH | **+1 language** |

**Executive Headline:** *60% of HR queries now handled autonomously, 24/7; HR specialists reclaim 18 hours per week for strategic work; employee satisfaction with HR services increased from 3.4 to 4.3.*

---

## 7. Lessons Learned

1. **Quality of knowledge base = quality of agent.** The single biggest predictor of agent accuracy was the cleanliness of the policy library. The "Policy Cleanse Sprint" was the best investment in the project.
2. **Escalation design builds trust.** Employees and HR specialists were sceptical of AI initially. Building clear, transparent escalation paths — and honouring them — was the key to adoption.
3. **Confidence thresholds matter more than coverage.** An agent that says "I'm not sure — let me connect you with HR" is more trusted than one that confidently gives a wrong answer. Always build graceful uncertainty.
4. **Operations dashboard is non-negotiable.** Without the Power BI ops dashboard, we would have been flying blind on agent performance. The weekly review cycles it enables are how the agent gets smarter over time.
5. **Multilingual is a differentiator.** Adding Mandarin language support increased APAC adoption by 35% versus the English-only pilot group.

---

## 8. Technologies Used

`Microsoft Copilot Studio` · `Power Automate` · `SharePoint (Knowledge Base)` · `Microsoft Teams (Adaptive Cards)` · `HRIS REST API` · `Azure OpenAI` · `Azure AI Content Safety` · `Power BI` · `DAX` · `Microsoft 365` · `OAuth 2.0`

---

*Last updated: 2026-07-10*
