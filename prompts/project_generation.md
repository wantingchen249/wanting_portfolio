# Prompt: Project Case Study Generation
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10
> **Use:** Generate a new project case study in the standard portfolio format.

---

## When to Use This Prompt

Use this prompt when:
- Adding a new completed project to the portfolio.
- Expanding a brief project note into a full case study.
- Refreshing an existing case study with updated outcomes.

---

## Input Requirements

Before running the prompt, gather the following information about the project:

```
PROJECT INPUT CHECKLIST
━━━━━━━━━━━━━━━━━━━━━━
□ Project name / working title
□ Primary category (e.g., "HR Analytics · Power BI")
□ Year completed
□ My role in the project (e.g., Project Lead, BI Architect, PM)
□ Business problem / what was broken before
□ What I did — approach, phases, key decisions
□ Technologies and tools used
□ At least ONE quantified outcome (%, time saved, $ value, # users, etc.)
□ 2–4 lessons learned
□ Any notable stakeholders or cross-functional dimensions
```

---

## The Prompt

Copy and paste the following into your AI assistant, filling in the `[INPUT]` sections:

---

```
You are a professional portfolio writer for Wanting Chen 陳琬婷,
an HRIS and Data Analytics professional. Your task is to write a
full project case study in the standard portfolio format.

## Project Information

**Project Name:** [INSERT]
**Category:** [INSERT — e.g., "HR Analytics · Business Intelligence"]
**Year:** [INSERT]
**My Role:** [INSERT]
**Technologies Used:** [INSERT — comma separated]
**Key Metric / Impact:** [INSERT — e.g., "40% reduction in reporting time"]

**Business Problem (what was broken):**
[INSERT — 3–5 sentences describing the situation before the project]

**What I Did (approach, phases, key actions):**
[INSERT — bullet points or paragraph describing your contribution]

**Outcomes:**
[INSERT — what changed after; include numbers if possible]

**Lessons Learned:**
[INSERT — 2–4 key takeaways]

## Instructions

Write a case study with the following sections:

1. **Frontmatter** (YAML block: title, category, tags, status, year, impact_metric, technologies)
2. **Overview** (2–3 sentences; lead with impact)
3. **Business Context & Challenge** (organisational situation + 4–6 core problems + stakeholder landscape)
4. **My Role & Approach** (phased breakdown; what Wanting specifically did; key decisions)
5. **Technical Architecture** (ASCII diagram or structured description of data/system flows)
6. **Key Deliverables** (bulleted list with ✅ checkmarks)
7. **Outcomes & Impact** (table: Before / After / Change for each metric)
8. **Lessons Learned** (4 numbered insights, each 2–4 sentences)
9. **Technologies Used** (backtick-formatted tag list)

## Style Rules
- Write in third person: "Wanting led…" / "The project…"
- Lead every section with the most important information first
- Every metric must be specific: use %, hours, headcount, $ or named outcomes
- Use active voice throughout
- Maximum 4 lines per paragraph in narrative sections
- Technologies section: wrap each tool in backticks, separated by ·
- Match the style and structure of this reference example:

[PASTE ONE EXISTING PROJECT FILE AS REFERENCE — e.g., contents of HR_Scorecard.md]
```

---

## Post-Generation Checklist

After the AI generates the case study, verify:

- [ ] All metrics are real and documented (no invented numbers)
- [ ] Technologies listed match actual tools used
- [ ] YAML frontmatter is complete and well-formed
- [ ] Lessons learned are genuine and specific (not generic platitudes)
- [ ] Technical architecture section is accurate
- [ ] Tone matches the portfolio voice: precise, data-driven, professional
- [ ] File saved as: `projects/[Project_Name_Snake_Case].md`
- [ ] Frontmatter tags align with the site map taxonomy (`04_Site_Map.md`)
- [ ] `knowledge/Resume.md` updated with new project in the Key Projects table

---

## Variation: Quick Card (for Project Grid)

If you only need the short-form card content for the homepage grid (not a full case study), use this shorter prompt:

```
Write a short project card entry for Wanting Chen's portfolio homepage.

Project: [INSERT NAME]
Category: [INSERT]
Emoji: [INSERT relevant emoji]
Technologies: [INSERT — 4–6 tools]
Impact: [INSERT — one-line metric]
Objective: [INSERT — one sentence]
Challenge: [INSERT — one sentence]
Solution: [INSERT — one to two sentences]

Format:
- project-emoji: [emoji]
- project-category: [CATEGORY · TYPE]
- project-title: [Title, max 8 words]
- project-desc: [2–3 sentences]
- meta-objective: [1 sentence]
- meta-challenge: [1 sentence]
- meta-solution: [1–2 sentences]
- tech-badges: [list of 4–6 tools]
- impact-banner: ⚡ Impact: [metric]
```

---

*Last updated: 2026-07-10*
