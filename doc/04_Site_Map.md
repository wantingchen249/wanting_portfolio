# 04 · Site Map
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10

---

## 1. Information Architecture Overview

```
Wanting Chen Portfolio
│
├── [/]  Home (index.html — Single Page Application)
│   ├── #hero             Hero
│   ├── #stats            Stats Bar
│   ├── #about            About
│   ├── #skills           Skills & Expertise
│   ├── #projects         Projects
│   ├── #achievements     Achievements
│   ├── #leadership       Leadership & Collaboration
│   └── #contact          Contact
│
├── [/projects/]  Project Detail Pages (Phase 2)
│   ├── hr-scorecard.html
│   ├── lms-replacement.html
│   ├── compensation-api.html
│   ├── hris-ai-agent.html
│   └── powerbi-adoption.html
│
├── [/blog/]  Insights & Articles (Phase 2)
│   ├── index.html        Blog index
│   └── [slug].html       Individual posts
│
└── [/assets/]  Static Assets
    ├── css/
    ├── js/
    └── img/
```

---

## 2. Page-Level Detail

### 2.1 Home — `index.html`

The portfolio's primary surface. All content is available without leaving the page.

| Section | Anchor | Purpose | Key Elements |
|---|---|---|---|
| **Hero** | `#hero` | First impression · role statement | Name (EN + ZH), role title, tag cloud, CTA buttons |
| **Stats Bar** | `#stats` | Credibility via numbers | 5 animated KPI counters |
| **About** | `#about` | Human narrative | Career summary, domain pills, highlights |
| **Skills** | `#skills` | Technical proof points | 6 skill cards with animated bars and tag clouds |
| **Projects** | `#projects` | Portfolio evidence | 6 project cards: Objective → Challenge → Solution → Stack → Impact |
| **Achievements** | `#achievements` | Quantified outcomes | 8 metric cards |
| **Leadership** | `#leadership` | Soft skills / collaboration | 4 leadership dimension cards |
| **Contact** | `#contact` | Conversion | Email, LinkedIn, company links |

### 2.2 Project Detail Pages — `/projects/*.html` (Phase 2)

Each project gets a standalone deep-dive page linked from the project card.

| Page | Source Doc | Status |
|---|---|---|
| `hr-scorecard.html` | `projects/HR_Scorecard.md` | Planned |
| `lms-replacement.html` | `projects/LMS_Replacement.md` | Planned |
| `compensation-api.html` | `projects/Compensation_API.md` | Planned |
| `hris-ai-agent.html` | `projects/HRIS_AI_Agent.md` | Planned |
| `powerbi-adoption.html` | `projects/PowerBI_Adoption.md` | Planned |

### 2.3 Blog — `/blog/` (Phase 2)

Thought-leadership articles generated using `prompts/blog_generation.md`.

Planned categories:
- People Analytics & BI
- HRIS Implementation Lessons
- AI in HR
- Data Governance

---

## 3. Navigation Structure

### 3.1 Primary Navigation (Desktop)
```
[Logo: Wanting Chen]  ·  About  ·  Skills  ·  Projects  ·  Achievements  ·  Leadership  ·  Contact
```
- Sticky, `position: fixed`, top offset.
- Active link highlighted on scroll (Phase 2: `IntersectionObserver` active-state tracking).
- CTA button: `Get in Touch` → `#contact`.

### 3.2 Mobile Navigation
- Hamburger icon → slide-in drawer (Phase 2).
- Phase 1: Nav links hidden on `max-width: 768px`.

### 3.3 Footer Navigation
```
© 2026 Wanting Chen 陳琬婷  ·  HRIS & Data Analytics Professional
[Back to top ↑]
```

---

## 4. User Flows

### 4.1 Recruiter Flow (Primary)
```
Landing → Hero (role understood in 5s)
  → Stats Bar (credibility established)
    → Projects (3 most relevant cards reviewed)
      → Contact (email Wanting or save LinkedIn)
```
Time to conversion target: **< 90 seconds**

### 4.2 Technical Peer Flow
```
Landing → About (background verified)
  → Skills (proficiency levels checked)
    → Project Detail Page (technical architecture reviewed)
      → Blog (insights read — Phase 2)
```

### 4.3 Executive / Consulting Flow
```
Landing → Hero
  → About (strategic narrative)
    → Achievements (ROI evidence)
      → Leadership (stakeholder management evidence)
        → Contact (direct email)
```

### 4.4 AI Agent Flow
```
Visitor opens chat widget
  → Wanda greets and offers topic options
    → Visitor asks about a project or skill
      → Wanda answers with sourced, structured response
        → Visitor follows deep-link to relevant section
          → Contact conversion
```

---

## 5. Content Taxonomy

### 5.1 Project Tags (for filtering — Phase 2)

| Tag | Projects |
|---|---|
| `Power BI` | HR Scorecard, PowerBI Adoption |
| `HRIS` | HR Scorecard, LMS Replacement, HRIS AI Agent |
| `AI / Automation` | HRIS AI Agent, Compensation API |
| `Data Governance` | HR Scorecard, Compensation API |
| `System Integration` | LMS Replacement, Compensation API |
| `Analytics` | HR Scorecard, PowerBI Adoption |
| `Change Management` | LMS Replacement, PowerBI Adoption |

### 5.2 Skill Categories

```
Technical Skills
  ├── Business Intelligence (Power BI, Fabric, DAX, Power Query)
  ├── Data Engineering (SQL, Data Modeling, ETL, Governance)
  ├── HRIS & HR Tech (Workday, SuccessFactors, LMS, ATS)
  └── AI & Automation (Copilot Studio, Power Automate, AI Agents)

Professional Skills
  ├── Project Management (Agile, Risk, Stakeholder)
  ├── Communication (Executive Presentation, Cross-cultural)
  └── Domain Expertise (HR Strategy, Workforce Planning, Compensation)
```

---

## 6. URL Conventions (Phase 2)

| Pattern | Example |
|---|---|
| Project pages | `/projects/[kebab-case-name]` |
| Blog posts | `/blog/[YYYY-MM-DD-slug]` |
| Assets | `/assets/[type]/[name]` |
| Deep links | `/#[section-anchor]` |

---

## 7. SEO Metadata Plan

| Page | Title | Description |
|---|---|---|
| Home | `Wanting Chen 陳琬婷 · HRIS & People Analytics` | `Senior HRIS professional specialising in Power BI, Microsoft Fabric, HR data governance, and digital transformation across global organisations.` |
| HR Scorecard | `HR Scorecard Dashboard · Wanting Chen Portfolio` | `How Wanting Chen built a global HR analytics dashboard suite reducing reporting time by 40%.` |
| HRIS AI Agent | `AI-Powered HR Service Agent · Wanting Chen Portfolio` | `Case study: Building an AI chatbot with Copilot Studio that deflected 60% of HR tier-1 queries.` |

---

*Last updated: 2026-07-10*
