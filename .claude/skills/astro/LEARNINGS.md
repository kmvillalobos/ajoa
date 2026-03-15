# Learnings — Astro Framework

## Was funktioniert
- `context: import('astro').APIContext` als inline Type-Import für API-Route-Parameter — behebt TS7006 ohne extra Import-Statement (2026-03-15)
- `context.site ?? 'https://fallback.dev'` als Fallback für `site` in RSS-Feed — behebt TS2322 (URL | undefined not assignable to string | URL) (2026-03-15)

## Anti-Patterns
