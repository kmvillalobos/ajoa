# Learnings — UI/UX Design

## Was funktioniert
- `py-20 px-6` als Standard-Section-Padding funktioniert konsistent über alle Sections → visuell harmonisch ohne Lighthouse-Impact (2026-03-15)
- `shadow-lg` statt `shadow-[0_25px_50px_-12px_rgba(0,0,0,0.15)]` — Tailwind-Standard-Shadow ist themebar und ausreichend für Card-Elevation (2026-03-15)

## Anti-Patterns
- `py-32` (128px) ist zu grosszügig für Standard-Sections — erzeugt visuelle Inkonsistenz mit anderen Sections die `py-20` (80px) nutzen (2026-03-15)
- `rounded-lg` auf Cards widerspricht dem Design-System (`rounded-xl`). Inkonsistenz ist nicht durch automatisierte Checks messbar — nur durch manuellen Code-Review (2026-03-15)
- `font-bold` auf h3 statt `font-semibold` — subtiler Unterschied, aber das Design-System definiert klare Hierarchie: bold für h1/h2, semibold für h3/h4 (2026-03-15)
