# Learnings — Tailwind CSS

## Was funktioniert
- `hover:shadow-xl hover:shadow-primary/40` statt `hover:shadow-[0_20px_50px_rgba(59,130,246,0.6)]` — themebar, passt sich automatisch an Primärfarben-Änderungen an (2026-03-15)
- `z-0` / `z-10` Tailwind-Klassen statt `style="z-index: 0/1"` — eliminiert Inline Styles ohne visuellen Unterschied (2026-03-15)

## Anti-Patterns
- `rgba(59,130,246,0.6)` in Arbitrary Shadows ist hardcoded Blau — bei Primärfarben-Änderung bleibt der Schatten falsch. Immer `shadow-primary/XX` verwenden (2026-03-15)
- `bg-zinc-900` in AuthLayout ist eine hardcoded Tailwind-Farbe in selten genutztem Layout — wird bei Grep-Checks in `src/**/*.astro` gefunden, sollte `bg-foreground` oder semantisches Token sein (2026-03-15)
