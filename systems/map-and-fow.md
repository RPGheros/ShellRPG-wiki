# Karte, Fog-of-War und Auto-Routing

## Fog-of-War

Jeder Charakter besitzt eine eigene Sicht auf die Welt:

- **visible**
- **fresh**
- **stale**
- **rumoured**
- **unknown**

## Explore

`explore` steuert automatisch die nächste verdeckte Region an. Beim Aufdecken neuer Felder werden bekannte Rohstoffvorkommen und POIs auf der Karte vermerkt.

## Gather

`gather wood`, `gather iron`, `gather gems` und `gather gold` steuern automatisch das nächstgelegene bekannte Vorkommen an. Wenn noch kein Vorkommen bekannt ist, nutzt der Slice einen sicheren Gerüchtepfad.

## Hunt

`hunt <N|S|W|O>` oder `hunt <x,y>` schickt den Charakter auf Jagd. Während der Suche aktualisiert sich das Overlay live, sobald das Tile wechselt oder eine Beute gefunden wird.

## Oeffentliche Tile-Hinweise

Redigierte Kartenpayloads duerfen jetzt zusaetzlich ein oeffentliches
Tile-Milieu tragen.

- `Milieu` beschreibt nur das oeffentliche Spawn- oder Umfeldbild eines
  Feldes, nicht interne Spawnlogik oder Wahrscheinlichkeiten.
- Tiles koennen dazu redigierte Referenzen auf Fraktions- oder
  Hinweiskoerper tragen, damit Client und WWW dieselben oeffentlichen
  Begriffslinien verwenden.
- Einfache Relationsachsen wie Allianz, Rivalitaet oder Neutralitaet duerfen
  daraus ebenfalls redigiert abgeleitet werden.
- Diese Hinweise bleiben bewusst public-safe und leaken keine Seeds,
  Anti-Cheat-Schwellen oder internen Triggermechaniken.

## Oeffentliche Stadthinweise

Stadttiles und Stadtansichten duerfen jetzt zusaetzlich einen redigierten
`Stadthinweis` tragen.

- Der Stadthinweis ist ein public-safe Verdachts- oder Spannungsmarker fuer
  den oeffentlichen Kartenvertrag.
- Er nutzt dieselbe redigierte Begriffsbasis wie Tile-Milieus, Fraktionsrefs
  und Relationsachsen.
- Persistierte Stadthinweise werden serverseitig als redigierte Alerts und
  Notizen gefuehrt, ohne interne Diagnose-, Spawn- oder Triggerlogik zu
  leaken.
- Derselbe Pfad fuehrt jetzt auch einen ersten persistierten urbanen
  Verdachtspool. Karten- und Stadtansichten duerfen daraus eine
  redigierte Stadtdiagnose und dieselben oeffentlichen Fraktions-,
  Hinweis- und Relationsreferenzen ableiten, ohne private Serverlogik zu
  offenbaren.
- Derselbe Pfad darf jetzt auch eine redigierte Parasitenlage fuer eine
  Siedlung andeuten. Oeffentliche Stadtdiagnosen duerfen dabei Hinweise auf
  Spezialpruefungsbedarf oder Gegenmassnahmen tragen, ohne konkrete
  Befallslogik, Schwellen oder interne Trigger zu verraten.
