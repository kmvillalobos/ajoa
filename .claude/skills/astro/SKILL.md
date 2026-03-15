---
name: astro
description: Astro 6 framework patterns including Islands architecture, Content Collections, routing, and build optimization. Use when creating pages, components, or troubleshooting Astro-specific issues.
---

# Astro Framework Skill

## Domain

Astro 6 Patterns, Islands Architecture, Content Collections, Routing, Build

## KPIs

| Metrik | Ziel | Messung |
|--------|------|---------|
| TypeScript Errors | 0 | `npx tsc --noEmit 2>&1 \| grep "error TS" \| wc -l` |
| Build Warnings | 0 | `npm run build 2>&1 \| grep -i "warn" \| wc -l` |
| Build-Zeit | <3s | `npm run build` Timing-Output |

## Regeln

### ClientRouter (NICHT ViewTransitions)

```astro
---
// ✅ Astro 6
import { ClientRouter } from 'astro:transitions';
---
<head>
  <ClientRouter />
</head>

// ❌ Veraltet
import { ViewTransitions } from 'astro:transitions';
```

### Zod Import

```typescript
// ✅ Astro 6
import { z } from 'astro/zod';

// ❌ Veraltet
import { z } from 'astro:content';
import { z } from 'astro:schema';
```

### Content Collections

```typescript
// src/content.config.ts
import { defineCollection } from 'astro:content';
import { z } from 'astro/zod';
import { glob } from 'astro/loaders';

const blog = defineCollection({
  loader: glob({ pattern: '**/*.{md,mdx}', base: './src/content/blog' }),
  schema: z.object({
    title: z.string(),
    description: z.string(),
    pubDate: z.coerce.date(),
    draft: z.boolean().optional(),
  }),
});

export const collections = { blog };
```

```astro
---
// Nutzung in Seiten
import { getCollection } from 'astro:content';
const posts = await getCollection('blog');
---
```

### .astro vs .tsx Entscheidung

| Verwende .astro wenn... | Verwende .tsx wenn... |
|------------------------|----------------------|
| Statischer Content | Client-side Interaktivität nötig |
| Server-side Rendering | State Management nötig |
| Layout-Komponenten | Event Handlers nötig |
| Section-Komponenten | Formulare mit Validierung |
| SEO/Meta-Komponenten | Komplexe UI (Dialogs, Dropdowns) |

### Client Directives

```astro
<!-- Sofort laden (für above-the-fold Interaktivität) -->
<Component client:load />

<!-- Laden wenn sichtbar (für below-the-fold) -->
<Component client:visible />

<!-- Laden im Idle (für nicht-kritische UI) -->
<Component client:idle />

<!-- Nur auf bestimmter Plattform -->
<Component client:only="react" />
```

**Faustregel:** `client:visible` > `client:idle` > `client:load`. Nur `client:load` für sofort sichtbare interaktive Elemente.

### Props-Interface-Pattern

```astro
---
interface Props {
  title: string;
  description?: string;
  variant?: 'default' | 'compact' | 'wide';
  class?: string;
}

const {
  title,
  description,
  variant = 'default',
  class: className,
} = Astro.props;
---
```

### Slot-Komposition

```astro
<!-- Benannte Slots -->
<section>
  <div class="header">
    <slot name="header" />
  </div>
  <div class="content">
    <slot />  <!-- Default Slot -->
  </div>
  <div class="footer">
    <slot name="footer" />
  </div>
</section>
```

### astro.config.mjs Patterns

```javascript
import { defineConfig } from 'astro/config';
import tailwindcss from '@tailwindcss/vite';
import react from '@astrojs/react';
import sitemap from '@astrojs/sitemap';

export default defineConfig({
  site: 'https://example.com',
  integrations: [react(), sitemap()],
  vite: {
    plugins: [tailwindcss()],
  },
});
```

### Import-Alias

Immer `@/` verwenden (konfiguriert in `tsconfig.json`):

```typescript
// ✅
import Hero from '@/components/sections/Hero.astro';
import { Button } from '@/components/ui/button';

// ❌
import Hero from '../../components/sections/Hero.astro';
```

## Vor dem Anwenden

Lies `LEARNINGS.md` in diesem Verzeichnis, um bekannte Anti-Patterns zu vermeiden.
