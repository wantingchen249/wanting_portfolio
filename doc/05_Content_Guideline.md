# 05 · Content Guidelines
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10

---

## 1. Brand Voice

### The Three Words
> **Precise · Data-Driven · Human-Centred**

Every piece of content — a hero headline, a project description, a blog post — should feel like it was written by someone who:
- Thinks in systems and evidence.
- Communicates with clarity and respect for the reader's time.
- Cares about the people behind the data.

### Voice Dimensions

| Dimension | We Are | We Are Not |
|---|---|---|
| **Tone** | Professional, authoritative | Stiff, bureaucratic |
| **Confidence** | Assured, evidence-backed | Boastful, self-congratulatory |
| **Depth** | Technically accurate | Jargon-heavy without explanation |
| **Warmth** | Approachable, collaborative | Cold, transactional |
| **Length** | Concise, complete | Verbose or shallow |

---

## 2. Writing Rules

### 2.1 General Principles
1. **Lead with impact.** State the outcome before the method.
   - ✅ *"Reduced manual reporting time by 40% through a unified Power BI dashboard suite."*
   - ❌ *"I built a Power BI dashboard that had various charts and ended up saving time."*

2. **Use active voice.**
   - ✅ *"Wanting led the integration of 5 HR systems."*
   - ❌ *"The integration of 5 HR systems was led by Wanting."*

3. **Quantify everything you can.**
   - Every project must contain at least one metric.
   - Prefer: `40%`, `200+ users`, `3 months ahead`, `5 regions` over general adjectives.

4. **Be specific about tools.**
   - ✅ *"Built using Power BI, Microsoft Fabric, DAX, and Power Query."*
   - ❌ *"Built with Microsoft data tools."*

5. **Avoid hedging language** unless genuinely uncertain.
   - ❌ *"Helped to somewhat improve the reporting process."*
   - ✅ *"Reduced reporting cycle from 5 days to same-day."*

### 2.2 Person & Perspective
- Refer to Wanting by name or in first person depending on context.
- **Section descriptions** (3rd person): *"Wanting designed the HR analytics framework…"*
- **AI agent responses** (1st person on behalf of): *"Wanting led this project to…"*
- **Blog posts** (1st person): *"When I first encountered this data quality challenge…"*

### 2.3 Chinese Name Usage
- Always include `陳琬婷` when the full English name `Wanting Chen` appears in a heading or formal context.
- In body copy, use either `Wanting` or `Wanting Chen` — not both in the same paragraph.

### 2.4 Sentence Structure
- Vary sentence length: long analytical sentences balanced with short punchy ones.
- Maximum paragraph length in body copy: **4 lines**.
- Maximum project description length: **3 sentences** (card view) · **unlimited** (detail page).

---

## 3. Content Formats

### 3.1 Section Label
```
Format:  ALL CAPS · 2px letter-spacing · ~5 words max · positioned above section title
Example: EXPERTISE | PORTFOLIO | IMPACT | COLLABORATION
```

### 3.2 Section Title
```
Format:  Title Case · sentence-fragment or noun phrase · max 6 words
Examples:
  "Technical & Domain Skills"
  "Signature Projects"
  "Key Achievements"
  "Bridging People & Technology"
```

### 3.3 Project Card (Short Form)
```
Structure:
  [Emoji] [Category in caps]
  [Project Title — max 8 words]
  [Description — 2–3 sentences max]
  [Objective / Challenge / Solution — 1 sentence each]
  [Tech badges — 4–6 items]
  [Impact banner — 1 line with metric]
```

### 3.4 Project Case Study (Long Form)
```
Sections:
  1. Overview (2–3 sentences)
  2. Business Context & Challenge (1–3 paragraphs)
  3. My Role & Approach (1–3 paragraphs)
  4. Technical Architecture (diagram description or bullet list)
  5. Key Deliverables (bulleted list)
  6. Outcomes & Impact (metric table or bullet list)
  7. Lessons Learned (2–4 bullets)
  8. Technologies Used (comma-separated tags)
```

### 3.5 Skill Entry
```
Format: [Tool Name] — [Proficiency Level] — [Specific application in 1 sentence]
Example: "Power BI — Advanced — Built a global HR analytics dashboard suite
          serving 200+ users with row-level security and live HRIS connections."
```

### 3.6 Achievement Card
```
Format:
  [Emoji icon]
  [Big number + unit]  ← must be real, documented metric
  [Short title — 3–5 words]
  [Supporting description — 1–2 sentences]
```

### 3.7 Blog Post
```
Structure:
  Title: [Compelling, specific — avoid clickbait]
  Subtitle: [Optional — adds context]
  Hook: [Opening paragraph — problem or provocative insight]
  Body: [3–5 H2 sections, each 150–300 words]
  Takeaways: [Bulleted summary — 3–5 points]
  CTA: [Link back to portfolio or invitation to connect]

Length: 800–1,500 words
```

---

## 4. Terminology Standards

### 4.1 Approved Terms (use these consistently)

| Preferred | Avoid |
|---|---|
| HRIS | HR system, HR software (unless referring specifically) |
| People Analytics | HR Analytics (use either, but be consistent per piece) |
| Digital Transformation | Digitisation / Digitalization (unless technically precise) |
| Workforce Planning | Headcount Planning (former is more strategic) |
| Data Governance | Data Management (latter is too generic) |
| AI-powered | AI-driven, AI-enabled (use "powered" for consistency) |
| Microsoft Fabric | Fabric (always include "Microsoft" on first mention) |
| Power BI | PowerBI (always with space; capitalise both words) |

### 4.2 Acronym Rules
- Define on first use: *"Human Resource Information System (HRIS)"*.
- After first use, acronym alone is acceptable.
- Never define an acronym that will only appear once.

---

## 5. Metadata Standards

### 5.1 HTML Meta Tags (per page)
```html
<title>[Page Name] · Wanting Chen 陳琬婷</title>
<meta name="description" content="[120–160 char description]">
<meta name="author" content="Wanting Chen">
<meta name="keywords" content="HRIS, Power BI, People Analytics, Microsoft Fabric, Digital Transformation">
<meta property="og:title" content="[Page Name] · Wanting Chen">
<meta property="og:description" content="[Social share description]">
<meta property="og:type" content="website">
```

### 5.2 Project Frontmatter (Markdown)
```markdown
---
title: "[Project Name]"
category: "[Primary Category]"
tags: [tag1, tag2, tag3]
status: "Completed" | "In Progress" | "Planned"
year: YYYY
impact_metric: "[Key metric]"
technologies: [tool1, tool2, tool3]
---
```

---

## 6. Image & Media Guidelines

| Asset Type | Spec |
|---|---|
| Profile photo | Square, min 400×400px, professional attire, neutral background |
| Project screenshots | 16:9, annotated if needed, compressed < 200KB |
| Diagram / architecture | White or light background, exported as SVG preferred |
| Blog header image | 1200×630px (OG image standard) |
| Favicon | 32×32px, `favicon.ico` or SVG |

---

## 7. Accessibility Standards

- **Alt text** on all images: descriptive, not "image of dashboard".
- **Colour contrast** ratios: minimum 4.5:1 (normal text), 3:1 (large text) — WCAG AA.
- **Keyboard navigation**: all interactive elements focusable and labelled.
- **ARIA labels**: all icon-only buttons must have `aria-label`.
- **Motion**: implement `prefers-reduced-motion` media query.

---

## 8. Update Protocol

When adding new content:
1. Update the relevant `knowledge/` or `projects/` markdown file first.
2. Reflect changes in `index.html`.
3. Run Lighthouse audit — resolve any regressions before publishing.
4. Update `knowledge/Resume.md` if a new role, project, or cert is added.
5. Notify the AI agent's knowledge base of additions.

---

*Last updated: 2026-07-10*
