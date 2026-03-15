---
name: ui-design
description: Visual hierarchy, spacing, typography, OKLCH color theory, and layout patterns for AstroDeck projects. Use when creating or reviewing UI components, adjusting spacing, typography, or visual consistency.
---

# UI/UX Design Skill

## Domain

Visual Hierarchy, Spacing, Typography, OKLCH-Farbtheorie, Layout-Patterns

## KPIs

| Metrik | Ziel | Messung |
|--------|------|---------|
| Lighthouse Performance | >90 | Lighthouse JSON → `categories.performance.score * 100` |
| First Contentful Paint | <1.8s | Lighthouse JSON → `audits.first-contentful-paint` |
| Largest Contentful Paint | <2.5s | Lighthouse JSON → `audits.largest-contentful-paint` |
| Cumulative Layout Shift | <0.1 | Lighthouse JSON → `audits.cumulative-layout-shift` |
| Total Blocking Time | <200ms | Lighthouse JSON → `audits.total-blocking-time` |

## Regeln

### Heading-Skala

```
h1: text-5xl md:text-7xl font-bold      → Hero-Headlines
h2: text-3xl md:text-5xl font-bold      → Section-Headlines
h3: text-xl md:text-2xl font-semibold   → Sub-Headlines, Card-Titles
h4: text-lg font-semibold               → Feature-Titles
p:  text-base/text-lg text-muted-foreground → Body
```

- `font-bold` für Headlines (h1, h2)
- `font-semibold` für Sub-Headlines (h3, h4)
- Niemals `font-extrabold` oder `font-black` verwenden

### Section-Padding-System

```
Standard-Section:  py-20 px-6
Kompakte Section:  py-12 px-6
Hero-Section:      py-24 px-6  oder  min-h-[80vh] px-6
CTA-Section:       py-16 px-6
```

### Container-Widths

```
Standard Content:   max-w-7xl mx-auto
Narrow Content:     max-w-4xl mx-auto (text-heavy, centered)
Wide Content:       max-w-none (full-width backgrounds)
Card Container:     max-w-5xl mx-auto (default BaseLayout)
```

### Grid-Patterns

```
2-Spalten:  grid md:grid-cols-2 gap-8
3-Spalten:  grid md:grid-cols-2 lg:grid-cols-3 gap-8
4-Spalten:  grid grid-cols-2 md:grid-cols-4 gap-6
Features:   grid md:grid-cols-2 lg:grid-cols-3 gap-8
```

### Card-Pattern

```astro
<div class="rounded-xl border border-border bg-card p-6 shadow-sm">
  <h3 class="text-xl font-semibold mb-2">{title}</h3>
  <p class="text-muted-foreground">{description}</p>
</div>
```

- Immer `rounded-xl` (nicht `rounded-lg` oder `rounded-md`)
- Immer `border border-border` für Konsistenz
- Immer `bg-card` (nicht `bg-white` oder `bg-gray-50`)
- Padding: `p-6` Standard, `p-8` für große Cards

### Design-Consistency-Checklist

- [ ] Heading-Hierarchie eingehalten (h1 → h2 → h3, kein Überspringen)
- [ ] Einheitliche Section-Paddings (`py-20 px-6`)
- [ ] Farben nur via CSS-Variablen (`text-primary`, nicht `text-blue-500`)
- [ ] Konsistente Border-Radius (`rounded-xl`)
- [ ] Mobile-first Responsive (Breakpoints: `md:` und `lg:`)
- [ ] Dark Mode getestet

## Vor dem Anwenden

Lies `LEARNINGS.md` in diesem Verzeichnis, um bekannte Anti-Patterns zu vermeiden.
