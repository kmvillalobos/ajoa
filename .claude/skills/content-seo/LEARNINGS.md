# Learnings — Content & SEO

## Was funktioniert
- Title ohne Brand-Duplikat: Layout hängt `| AstroDeck` automatisch an, daher Page-Title ohne "AstroDeck" übergeben → sauberer `<title>` Tag (2026-03-15)

## Anti-Patterns
- Meta Description unter 150 Zeichen: Lighthouse bewertet SEO auch bei 143 Zeichen mit 100/100, da die Mindestlänge kein hartes Kriterium ist. Das 150-Zeichen-Ziel im SKILL.md ist ein Best-Practice-Richtwert, kein Pflichtmass — aber trotzdem anstreben (2026-03-15)
- Title-Duplikat "AstroDeck ... | AstroDeck" — entsteht wenn der Page-Title bereits den Brand-Namen enthält und das Layout nochmal `| AstroDeck` anhängt (2026-03-15)
