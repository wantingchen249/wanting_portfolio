# 03 · Design System
> **Portfolio:** Wanting Chen 陳琬婷
> **Version:** 1.0 · **Date:** 2026-07-10

---

## 1. Design Philosophy

The portfolio design system is built on four principles:

| Principle | Expression |
|---|---|
| **Authoritative** | Deep navy primary palette communicates confidence and expertise |
| **Data-Centric** | Visual hierarchy mirrors analytical thinking: structure → insight → action |
| **Human-Centred** | Rounded corners, generous whitespace, and warm accents prevent clinical coldness |
| **Purposeful Motion** | Animation is used only where it carries information (counters, bars, scroll state) |

---

## 2. Color Palette

### 2.1 Core Colors

| Token | Hex | RGB | Usage |
|---|---|---|---|
| `--primary` | `#1a3f6f` | 26, 63, 111 | Headlines, nav brand, primary UI elements |
| `--accent` | `#2d8bba` | 45, 139, 186 | Section labels, links, skill tags, borders |
| `--accent2` | `#4fc3f7` | 79, 195, 247 | Stats numbers, hero highlights, gradients |
| `--light` | `#e8f4fd` | 232, 244, 253 | Section backgrounds, skill tag fills |
| `--surface` | `#ffffff` | 255, 255, 255 | Cards, modal surfaces |
| `--text` | `#1e293b` | 30, 41, 59 | Body copy, labels |
| `--muted` | `#64748b` | 100, 116, 139 | Secondary text, descriptions |
| `--border` | `#e2e8f0` | 226, 232, 240 | Card borders, dividers |

### 2.2 Gradients

| Token | Definition | Usage |
|---|---|---|
| `--grad` | `linear-gradient(135deg, #1a3f6f 0%, #2d8bba 60%, #4fc3f7 100%)` | Hero, skill bars, impact banners, progress bar |
| `--grad-card` | `linear-gradient(135deg, #f0f9ff 0%, #e8f4fd 100%)` | Card backgrounds, about panel |

### 2.3 Semantic Colors

| Token | Hex | Usage |
|---|---|---|
| `--success` | `#10b981` | Positive metrics, completed states |
| `--warning` | `#f59e0b` | Caution states, work-in-progress |
| `--error` | `#ef4444` | Error states (form validation) |
| `--info` | `#3b82f6` | Informational callouts |

### 2.4 Dark Surface (Stats Bar / Contact Section)

| Element | Value |
|---|---|
| Stats bar background | `var(--primary)` |
| Contact section background | `var(--primary)` |
| Footer background | `#0f2542` |
| Text on dark | `rgba(255,255,255,0.88)` |
| Muted text on dark | `rgba(255,255,255,0.75)` |

---

## 3. Typography

### 3.1 Font Stack

```css
font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
```

No external font loading — system stack ensures zero latency and wide CJK support.

### 3.2 Type Scale

| Role | Size | Weight | Line-Height | Token Usage |
|---|---|---|---|---|
| Hero H1 | `clamp(2.2rem, 5vw, 3.4rem)` | 800 | 1.15 | `.hero h1` |
| Section Title | `clamp(1.7rem, 3vw, 2.4rem)` | 800 | 1.2 | `.section-title` |
| Card Title | `1.08–1.2rem` | 700–800 | 1.3 | `.project-title`, `.skill-card-title` |
| Body | `0.98–1.02rem` | 400 | 1.7 | `p`, `.about-text p` |
| Label / Badge | `0.7–0.8rem` | 600–700 | — | `.section-label`, `.tech-badge` |
| Caption / Meta | `0.75–0.85rem` | 400–600 | 1.55 | `.meta-val`, `.achievement-desc` |

### 3.3 Type Rules
- **Section labels** are always: `uppercase · letter-spacing: 2px · color: var(--accent) · font-size: .75rem`
- **Chinese characters** (陳琬婷) always render in a smaller size (`60%` of parent) with reduced opacity (`0.82`).
- **Bold inside paragraphs** uses `font-weight: 700`, not `<b>` tags.

---

## 4. Spacing System

8-point grid. All spacing values are multiples of `0.5rem` (8px).

| Token | Value | Usage |
|---|---|---|
| `space-xs` | `0.25rem` (4px) | Icon gaps, tight padding |
| `space-sm` | `0.5rem` (8px) | Tag gaps, small margins |
| `space-md` | `1rem` (16px) | Component internal padding |
| `space-lg` | `1.5rem` (24px) | Card padding |
| `space-xl` | `2rem` (32px) | Section horizontal padding |
| `space-2xl` | `3rem` (48px) | Section header margin-bottom |
| `space-section` | `80px` | Section vertical padding |

---

## 5. Border Radius

| Token | Value | Usage |
|---|---|---|
| `--radius` | `14px` | Standard cards, skill cards, achievement cards |
| `--radius-lg` | `22px` | Project cards, about panel |
| `--radius-pill` | `100px` | Buttons, tags, badges, nav items |
| `--radius-sm` | `6–10px` | Skill tags, tech badges, bar tracks |

---

## 6. Shadow System

| Token | Value | Usage |
|---|---|---|
| `--shadow-sm` | `0 2px 8px rgba(26,63,111,.10)` | Default card state |
| `--shadow-md` | `0 8px 30px rgba(26,63,111,.14)` | Hover state, elevated cards |
| `--shadow-lg` | `0 20px 60px rgba(26,63,111,.18)` | Project card hover, modals |

---

## 7. Animation & Motion

### 7.1 Transition Defaults
```css
transition: all 0.25s ease;          /* Standard interactive transitions */
transition: transform 0.28s ease;    /* Card hover lifts */
transition: opacity 0.65s ease, transform 0.65s ease; /* Scroll reveal */
```

### 7.2 Scroll Reveal (Fade-Up)
- **Class:** `.fade-up` → `.fade-up.visible`
- **Trigger:** `IntersectionObserver` at threshold `0.12`
- **Effect:** `opacity 0→1`, `translateY 28px→0`
- **Stagger:** 80ms delay per sibling element

### 7.3 Skill Bar Animation
- Triggered on scroll into view (threshold `0.3`)
- Duration: `1.2s ease`
- Width driven by `data-width` attribute

### 7.4 Counter Animation
- Triggered on scroll into view (threshold `0.5`)
- Increments every 35ms using `setInterval`
- 40 steps to target value

### 7.5 Floating Blobs (Hero)
```css
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-22px); }
}
/* Duration: 8s, second blob offset by -4s */
```

### 7.6 Motion Accessibility
All animations respect `prefers-reduced-motion`:
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}
```

---

## 8. Layout Grid

| Context | System |
|---|---|
| **Page max-width** | `1140px` centred |
| **Section padding** | `80px 2rem` (desktop) · `60px 1.2rem` (mobile) |
| **Skills grid** | `repeat(auto-fit, minmax(280px, 1fr))` |
| **Projects grid** | `repeat(auto-fit, minmax(330px, 1fr))` |
| **Achievements grid** | `repeat(auto-fit, minmax(240px, 1fr))` |
| **Leadership grid** | `repeat(auto-fit, minmax(280px, 1fr))` |
| **Stats grid** | `repeat(auto-fit, minmax(170px, 1fr))` |
| **About grid** | `1fr 1fr` (stacks to `1fr` on mobile) |

---

## 9. Component States

| State | Visual Treatment |
|---|---|
| **Default** | `--shadow-sm` · no transform |
| **Hover (card)** | `translateY(-4px to -6px)` · `--shadow-md or --shadow-lg` |
| **Hover (nav link)** | `color: var(--primary)` · underline pseudo-element expands to `100%` |
| **Hover (button)** | `translateY(-2px)` · elevated shadow |
| **Active** | Scale `0.98` (optional, for click feedback) |
| **Focus** | `outline: 2px solid var(--accent)` · `outline-offset: 3px` |

---

## 10. Icon System

Icons are rendered as Unicode emoji for zero-dependency portability:

| Category | Examples |
|---|---|
| Section markers | 📊 🗄️ 🏢 🤖 📋 🌐 |
| Project types | 🔗 🎓 🛡️ 📈 |
| Achievements | ⏱️ 🌍 🚀 👥 |
| UI interaction | ✅ ❌ ▹ ✦ ⚡ |

For production upgrade, replace with SVG sprite or Lucide icons for crisp rendering at all DPIs.

---

*Last updated: 2026-07-10*
