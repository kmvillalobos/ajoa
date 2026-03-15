# Learnings — QA

## Was funktioniert
- `interface Foo extends Bar {}` → `type Foo = Bar` behebt `no-empty-object-type` ESLint-Error sauber (2026-03-15)
- `// eslint-disable-next-line` für `env.d.ts` Triple-Slash-Referenz ist akzeptabel, da Astro diese Datei vorschreibt (2026-03-15)

## Anti-Patterns
- Prettier kann `<!-- Astro-Kommentare -->` innerhalb von `.map()` Expressions nicht parsen — erzeugt Parse-Error in `format:check`. Kommentare in `.map()` müssen durch `{/* JSX-Kommentare */}` ersetzt oder entfernt werden (2026-03-15)
- `@vercel/analytics/astro` erzeugt im lokalen Preview-Server einen 404 auf `/_vercel/insights/script.js`, was Lighthouse Best Practices von 100 auf 96 senkt. Kein Produktions-Problem, aber verfälscht lokale Lighthouse-Messungen (2026-03-15)
