---
name: qa
description: Testing, validation, code quality, and launch readiness for AstroDeck projects. Use when running audits, checking build quality, or preparing for production deployment.
---

# QA Skill

## Domain

Testing, Validierung, Code-Qualität, Launch-Readiness

## KPIs

| Metrik | Ziel | Messung |
|--------|------|---------|
| Lighthouse Best Practices | >90 | Lighthouse JSON → `categories.best-practices.score * 100` |
| ESLint Errors | 0 | `npm run lint -- --format json` |
| ESLint Warnings | 0 | `npm run lint -- --format json` |
| Formatting Issues | 0 | `npm run format:check` |
| HTML Validation Errors | 0 | `npx html-validate dist/` |

## Regeln

### Build-Pipeline

```bash
# Vollständige QA-Pipeline
npm run lint          # ESLint Errors/Warnings
npm run format:check  # Prettier Formatting
npx tsc --noEmit      # TypeScript Errors
npm run build         # Astro Build (0 Errors, 0 Warnings)
```

### Pre-Launch-Checklist

#### Content
- [ ] Kein Platzhalter-Content ("Lorem ipsum", "TODO", "FIXME")
- [ ] Alle Links funktionieren (keine `#` oder `javascript:void(0)`)
- [ ] Bilder haben beschreibende Alt-Texte
- [ ] Texte sind korrekturgelesen

#### Branding
- [ ] Logo ersetzt (nicht mehr AstroDeck-Standard)
- [ ] Favicon gesetzt (`public/favicon.svg`)
- [ ] OG-Image erstellt (`public/og-image.png`, 1200×630px)
- [ ] Site-Title und Description in `astro.config.mjs`

#### Legal
- [ ] Impressum vorhanden (DACH-Pflicht)
- [ ] Datenschutzerklärung vorhanden
- [ ] Cookie-Banner konfiguriert (wenn Tracking aktiv)

#### Analytics & Forms
- [ ] Analytics-Code eingebunden (wenn gewünscht)
- [ ] Formulare senden an korrekte Endpoints
- [ ] Formulare haben Honeypot/CAPTCHA

#### Performance
- [ ] Lighthouse Performance >90
- [ ] Bilder optimiert (WebP/AVIF, responsive sizes)
- [ ] Keine unnötigen `client:load` Direktiven
- [ ] External Scripts mit SRI

### Lighthouse-Ziele

| Kategorie | Minimum | Ideal |
|-----------|---------|-------|
| Performance | 90 | 95+ |
| Accessibility | 90 | 95+ |
| Best Practices | 90 | 95+ |
| SEO | 90 | 95+ |

### Responsive-Testing Breakpoints

| Gerät | Breite | Prüfen |
|-------|--------|--------|
| Mobile S | 375px | Layout, Navigation, Text-Größe |
| Tablet | 768px | Grid-Umbrüche, Seitenleisten |
| Laptop | 1024px | Volle Navigation, Grid-Layouts |
| Desktop | 1280px | Max-Width Container, große Bilder |

### Dark-Mode-Testing

- [ ] Alle Seiten in Dark Mode prüfen
- [ ] Keine weißen Flächen oder unlesbarer Text
- [ ] Bilder/Icons sichtbar (kein schwarzes Logo auf schwarzem Hintergrund)
- [ ] Toggle funktioniert und persistiert Auswahl

### Cross-Browser

- [ ] Chrome/Edge (Chromium)
- [ ] Firefox
- [ ] Safari (WebKit)
- [ ] Mobile Safari (iOS)
- [ ] Chrome Mobile (Android)

## Vor dem Anwenden

Lies `LEARNINGS.md` in diesem Verzeichnis, um bekannte Anti-Patterns zu vermeiden.
