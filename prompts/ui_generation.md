[ui_generation.md](https://github.com/user-attachments/files/29884332/ui_generation.md)
# Prompt: UI Component & Page Generation
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10
> **Use:** Generate new HTML/CSS UI components or pages consistent with the portfolio design system.

---

## When to Use This Prompt

Use this prompt when:
- Adding a new section to `index.html`.
- Building a new standalone page (project detail, blog post).
- Creating a new reusable UI component.
- Updating the visual design of an existing section.

---

## Design System Reference (Always Include)

When generating UI, always provide the AI with these design tokens from `03_Design_System.md`:

```css
/* === DESIGN TOKENS — paste into every UI prompt === */
:root {
  --primary:    #1a3f6f;
  --accent:     #2d8bba;
  --accent2:    #4fc3f7;
  --light:      #e8f4fd;
  --surface:    #ffffff;
  --text:       #1e293b;
  --muted:      #64748b;
  --border:     #e2e8f0;
  --grad:       linear-gradient(135deg, #1a3f6f 0%, #2d8bba 60%, #4fc3f7 100%);
  --grad-card:  linear-gradient(135deg, #f0f9ff 0%, #e8f4fd 100%);
  --shadow-sm:  0 2px 8px rgba(26,63,111,.10);
  --shadow-md:  0 8px 30px rgba(26,63,111,.14);
  --shadow-lg:  0 20px 60px rgba(26,63,111,.18);
  --radius:     14px;
  --radius-lg:  22px;
  --radius-pill: 100px;
}
font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
/* 8-point grid: use multiples of 0.5rem for all spacing */
/* Card hover: translateY(-4px to -6px) + --shadow-md or --shadow-lg */
/* Animations: fade-up with IntersectionObserver, skill bars on scroll */
```

---

## Prompt A — New Section (for index.html)

```
You are a front-end developer building a personal portfolio for
Wanting Chen 陳琬婷, an HRIS and Data Analytics professional.

## Task
Add a new "[SECTION NAME]" section to the portfolio's index.html.

## Section Specification
- Section ID: #[section-id]
- Purpose: [Describe what this section communicates to the visitor]
- Content to display: [Describe the data/content — e.g., "3 blog post cards", "a timeline of 5 career milestones"]
- Background: [white / var(--light) / var(--primary) / other]
- Layout: [grid / flex / single column / split]
- Interactive elements: [hover effects / animation / filters / none]

## Content Data
[Paste the actual content that should populate the section]

## Design Constraints
- Must use ONLY the design tokens defined below (no external libraries)
- All cards must have `.fade-up` class for scroll animation
- Typography must follow the type scale in the design system
- Hover states: `translateY(-4px)` + `--shadow-md` for cards
- Section must follow this structure:
  <section id="[id]">
    <div class="container">
      <div class="section-header [centered?]">
        <span class="section-label">LABEL</span>
        <h2 class="section-title">Title</h2>
        <p class="section-desc">Description</p>
      </div>
      [CONTENT GRID]
    </div>
  </section>

## Design Tokens
[PASTE DESIGN TOKENS FROM ABOVE]

## Output
Provide:
1. The complete HTML for the section
2. The CSS (scoped to this section's classes only — no global overrides)
3. Any JavaScript needed (minimal, scroll-based only)
4. Where to insert the section in index.html (before/after which section)
5. Which nav link to add (text + anchor)
```

---

## Prompt B — New Standalone Page (e.g., Project Detail)

```
You are a front-end developer building a project detail page for
Wanting Chen's portfolio. The page must be self-contained HTML with
all CSS inline, consistent with the main portfolio design.

## Page Specification
- Page title: "[PROJECT NAME] · Wanting Chen 陳琬婷"
- Project data source: [PASTE contents of the relevant projects/*.md file]
- Page URL: /projects/[kebab-case-slug].html

## Page Structure
Build a page with these sections:
1. Navigation bar (same as main site — link back to #projects)
2. Hero strip (project name, category, year, tech badges — gradient background)
3. Overview & Impact (key metrics prominently displayed)
4. Business Challenge (problem statement)
5. Approach (phases — could use a timeline or numbered cards)
6. Technical Architecture (monospace/code-style block)
7. Key Deliverables (checklist)
8. Outcomes (before/after table)
9. Lessons Learned (numbered cards)
10. Back to Portfolio CTA button

## Design Constraints
[PASTE DESIGN TOKENS]

## Output
1. Complete standalone HTML file (all CSS embedded in <style> tag)
2. Filename: [slug].html
3. Ensure "Back to Portfolio" button links to: ../index.html#projects
```

---

## Prompt C — New Reusable Component

```
You are building a reusable HTML/CSS component for Wanting Chen's portfolio.

## Component Specification
- Component name: [NAME — e.g., "Timeline Card", "Testimonial Card", "Filter Bar"]
- Purpose: [What it displays and when it's used]
- Content it receives: [List the data fields — title, description, date, etc.]
- States needed: [default, hover, active, selected, disabled]
- Responsive behaviour: [How it behaves on mobile vs desktop]

## Example instance (the component rendered with real data):
[PROVIDE ONE EXAMPLE with actual content]

## Design Constraints
[PASTE DESIGN TOKENS]

## Output
1. HTML structure (one instance as example)
2. CSS (scoped class names — prefix with component name, e.g., `.timeline-`)
3. Usage notes: how to replicate for additional instances
4. Add to Component Library: a summary entry in the format of `06_Component_Library.md`
```

---

## Prompt D — Dark Mode Variant

```
Generate dark mode CSS variables for Wanting Chen's portfolio design system.
The dark mode should:
- Maintain brand identity (navy/blue palette)
- Swap light backgrounds for dark surfaces
- Ensure WCAG AA contrast ratios are maintained
- Activate via `prefers-color-scheme: dark` media query
- Override only the :root variables — do not duplicate component CSS

Current light mode tokens:
[PASTE DESIGN TOKENS]

Output:
1. @media (prefers-color-scheme: dark) { :root { ... } } block
2. Any component-level overrides needed (gradient text, image overlays)
3. Contrast ratio verification table for key text/background combinations
```

---

## Post-Generation Checklist

After generating UI code, verify:

- [ ] All CSS uses design tokens (no hardcoded hex values except in `:root`)
- [ ] Responsive: tested mental model for `max-width: 768px`
- [ ] `.fade-up` class applied to animatable elements
- [ ] Hover states implemented (`transform` + `box-shadow`)
- [ ] No external CSS or JS dependencies introduced
- [ ] `aria-label` added to all icon-only elements
- [ ] Colour contrast passes WCAG AA (use browser DevTools or contrast checker)
- [ ] Section added to `04_Site_Map.md` if it's a new top-level section
- [ ] Component documented in `06_Component_Library.md` if reusable

---

*Last updated: 2026-07-10*
