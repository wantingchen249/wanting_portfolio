# 06 · Component Library
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10

---

## Overview

This library catalogs every reusable UI component in the portfolio. Each entry includes: purpose, anatomy, CSS class map, states, and the HTML snippet.

---

## C-01 · Navigation Bar

**Purpose:** Persistent top navigation with brand identity and section links.

**Anatomy:**
```
[Nav Wrapper: position:fixed]
  ├── [Brand Logo: text link → #hero]
  └── [Nav Links: ul > li > a]
```

**Class Map:**
| Class | Role |
|---|---|
| `nav` | Wrapper — fixed, full-width, glassmorphism |
| `.nav-inner` | Max-width container, flex row |
| `.nav-brand` | Logo text link |
| `.nav-links` | Horizontal link list |

**States:** Default → Hover (underline sweep) → Scroll (shadow intensifies)

**HTML:**
```html
<nav>
  <div class="nav-inner">
    <a class="nav-brand" href="#hero">Wanting <span>Chen</span></a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#achievements">Achievements</a></li>
      <li><a href="#leadership">Leadership</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</nav>
```

---

## C-02 · Hero Section

**Purpose:** Full-viewport first impression with identity, role, and CTA.

**Anatomy:**
```
[Hero: min-height 100vh, gradient bg]
  ├── [Blob 1 — ambient animation]
  ├── [Blob 2 — ambient animation]
  └── [Hero Content: z-index above blobs]
        ├── [Badge pill]
        ├── [Avatar circle]
        ├── [H1: EN name + ZH name]
        ├── [Subtitle]
        ├── [Tag cloud]
        └── [CTA buttons: 2]
```

**Class Map:**
| Class | Role |
|---|---|
| `.hero` | Full-viewport section with gradient |
| `.blob`, `.blob1`, `.blob2` | Floating ambient shapes |
| `.hero-content` | Centred content wrapper |
| `.hero-badge` | Pill label above name |
| `.avatar-wrap` | Circle icon container |
| `.hero-tags` | Flex tag cloud |
| `.hero-tag` | Individual tag pill |
| `.hero-cta` | Button row |

---

## C-03 · Section Header

**Purpose:** Consistent section-opening block with label, title, description.

**Variants:** Left-aligned (default) · Centred (`.section-header.centered`)

**HTML:**
```html
<div class="section-header [centered]">
  <span class="section-label">LABEL TEXT</span>
  <h2 class="section-title">Section Title Here</h2>
  <p class="section-desc">Optional supporting description sentence.</p>
</div>
```

**Class Map:**
| Class | Role |
|---|---|
| `.section-label` | Small caps label in accent colour |
| `.section-title` | Large bold heading in primary colour |
| `.section-desc` | Muted body text, max-width 620px |
| `.section-header.centered` | Centre-aligns all children |

---

## C-04 · Stats Bar

**Purpose:** High-contrast numerical credibility strip.

**HTML:**
```html
<div class="stats-bar">
  <div class="stats-grid">
    <div class="stat-item">
      <span class="stat-number" data-target="10">0</span>
      <p class="stat-label">+ Years Experience</p>
    </div>
    <!-- repeat for each stat -->
  </div>
</div>
```

**Behaviour:** `data-target` drives the JS counter animation on scroll-into-view.

---

## C-05 · Skill Card

**Purpose:** Present a technical domain with either skill bars or tag cloud.

**Variants:**
- **Bar variant** — for quantifiable proficiencies (Power BI, SQL, etc.)
- **Tag variant** — for tool ecosystems (HRIS tech stack, AI tools)

**HTML — Bar Variant:**
```html
<div class="skill-card fade-up">
  <div class="skill-card-header">
    <div class="skill-icon-wrap">📊</div>
    <span class="skill-card-title">Business Intelligence</span>
  </div>
  <div class="skill-bars">
    <div class="bar-wrap">
      <div class="bar-label"><span>Power BI</span><span>95%</span></div>
      <div class="bar-track">
        <div class="bar-fill" data-width="95"></div>
      </div>
    </div>
  </div>
</div>
```

**HTML — Tag Variant:**
```html
<div class="skill-card fade-up">
  <div class="skill-card-header">
    <div class="skill-icon-wrap">🏢</div>
    <span class="skill-card-title">HRIS & HR Tech</span>
  </div>
  <div class="skill-tags">
    <span class="skill-tag">Workday</span>
    <span class="skill-tag">SuccessFactors</span>
  </div>
</div>
```

**Class Map:**
| Class | Role |
|---|---|
| `.skill-card` | Card wrapper with hover lift |
| `.skill-icon-wrap` | 44px rounded icon box |
| `.skill-card-title` | Domain title |
| `.skill-bars` | Vertical list of bar items |
| `.bar-wrap` | Single bar row |
| `.bar-label` | Flex row: name left, % right |
| `.bar-track` | Grey background track |
| `.bar-fill` | Gradient fill, animates via `data-width` |
| `.skill-tags` | Flex wrap tag container |
| `.skill-tag` | Individual tag pill |

---

## C-06 · Project Card

**Purpose:** Showcase a project with context, solution, stack, and impact.

**Anatomy:**
```
[project-card]
  ├── [project-header: gradient bg]
  │     ├── [project-emoji]
  │     ├── [project-category]
  │     └── [project-title]
  ├── [project-body]
  │     ├── [project-desc]
  │     └── [project-meta: 3 rows]
  │           ├── Objective row
  │           ├── Challenge row
  │           └── Solution row
  ├── [project-footer: tech badges]
  └── [impact-banner: gradient strip]
```

**HTML:**
```html
<div class="project-card fade-up">
  <div class="project-header">
    <span class="project-emoji">📊</span>
    <div class="project-category">HR Analytics · Power BI</div>
    <div class="project-title">Project Title Here</div>
  </div>
  <div class="project-body">
    <p class="project-desc">2–3 sentence overview of the project.</p>
    <div class="project-meta">
      <div class="meta-row">
        <span class="meta-icon">🎯</span>
        <span class="meta-label">Objective</span>
        <span class="meta-val">One sentence objective.</span>
      </div>
      <div class="meta-row">
        <span class="meta-icon">⚠️</span>
        <span class="meta-label">Challenge</span>
        <span class="meta-val">One sentence challenge.</span>
      </div>
      <div class="meta-row">
        <span class="meta-icon">💡</span>
        <span class="meta-label">Solution</span>
        <span class="meta-val">One sentence solution.</span>
      </div>
    </div>
  </div>
  <div class="project-footer">
    <span class="tech-badge">Power BI</span>
    <span class="tech-badge">DAX</span>
  </div>
  <div class="impact-banner">⚡ Impact: <span>Quantified outcome here</span></div>
</div>
```

---

## C-07 · Achievement Card

**Purpose:** Display a single quantified business outcome.

**HTML:**
```html
<div class="achievement-card fade-up">
  <span class="achievement-icon">⏱️</span>
  <div class="achievement-metric">40<span class="unit">%</span></div>
  <div class="achievement-title">Reporting Time Saved</div>
  <div class="achievement-desc">Supporting description in 1–2 sentences.</div>
</div>
```

---

## C-08 · Leadership Card

**Purpose:** Present a leadership or collaboration dimension with evidence bullets.

**HTML:**
```html
<div class="leadership-card fade-up">
  <div class="lc-header">
    <span class="lc-icon">👥</span>
    <span class="lc-title">Cross-Functional Leadership</span>
  </div>
  <ul class="lc-list">
    <li>Evidence point one</li>
    <li>Evidence point two</li>
    <li>Evidence point three</li>
  </ul>
</div>
```

---

## C-09 · Button

**Purpose:** Primary call-to-action; two variants.

**Variants:**

| Variant | Class | Use Case |
|---|---|---|
| Solid white | `.btn .btn-white` | Primary CTA on dark/gradient backgrounds |
| Outline | `.btn .btn-outline` | Secondary CTA on dark/gradient backgrounds |
| Solid accent | `.btn .btn-accent` | CTA on light backgrounds (Phase 2) |

**HTML:**
```html
<!-- Primary -->
<a class="btn btn-white" href="#projects">🚀 View Projects</a>

<!-- Secondary -->
<a class="btn btn-outline" href="#contact">📬 Get in Touch</a>
```

---

## C-10 · Contact Card

**Purpose:** Clickable contact link card on dark background.

**HTML:**
```html
<a class="contact-card" href="mailto:wanting_chen@usiglobal.com">
  <span class="cc-icon">📧</span>
  <span>wanting_chen@usiglobal.com</span>
</a>
```

---

## C-11 · Fade-Up Animation Wrapper

**Purpose:** Applies scroll-reveal animation to any element.

**Usage:** Add `.fade-up` class to any element. The `IntersectionObserver` in `main.js` adds `.visible` when the element enters the viewport.

```html
<div class="fade-up">
  <!-- Any content -->
</div>
```

**Do not** nest `.fade-up` inside another `.fade-up` — apply to the outermost wrapper only.

---

## C-12 · Hero / Skill Badge Pill

**Purpose:** Small tag indicating a domain, skill, or category.

**Variants:**

| Variant | Class | Background | Text |
|---|---|---|---|
| Hero tag | `.hero-tag` | `rgba(255,255,255,.15)` | White |
| Domain pill | `.domain-pill` | `var(--primary)` | White |
| Skill tag | `.skill-tag` | `var(--light)` | Accent |
| Tech badge | `.tech-badge` | `var(--primary)` | White |

---

## C-13 · Progress Bar

**Purpose:** Scroll-depth indicator at the very top of the page.

```html
<div id="progress-bar"></div>
```

**JS:** Updates `width` as a percentage of total scroll depth.

---

## C-14 · About Panel (Left Card)

**Purpose:** Visual identity card for the About section.

```html
<div class="about-img-wrap fade-up">
  <span class="about-icon">🌟</span>
  <h3>Wanting Chen 陳琬婷</h3>
  <p>HRIS & Data Analytics Specialist</p>
  <div class="about-domains">
    <span class="domain-pill">HRIS</span>
    <!-- more pills -->
  </div>
</div>
```

---

## Phase 2 Components (Planned)

| Component | Description |
|---|---|
| **Mobile Drawer Nav** | Slide-in navigation for `max-width: 768px` |
| **Project Filter Bar** | Tag-based filter for the projects grid |
| **Chat Widget** | Floating Wanda AI agent bubble |
| **Blog Card** | Article preview card for `/blog/` index |
| **Toast Notification** | Contact form submission feedback |
| **Image Lightbox** | Full-screen project screenshot viewer |
| **Dark Mode Toggle** | `prefers-color-scheme` aware switch |

---

*Last updated: 2026-07-10*
