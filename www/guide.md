# WWW-Guide

## Start

```bash
python -m pip install -e .
shellrpg-www --config config/shellrpg-www.toml
```

Dann im Browser:

`http://127.0.0.1:8080/`

Alternativ kann der schlanke Wrapper `./shell.sh` genutzt werden.

## Oberfläche

- Status inkl. Reaktionsfenster
- Servermatrix-/Gateway-Diagnostik ueber denselben same-origin WWW-Pfad
- Medienbild/GIF pro Tile oder Encounter
- Karte mit FOW, POIs und Ressourcen
- Inventar und Ausrüstung
- Markt
- Quests / Buffs / Journal
- sichtbare Befehle

## Gateway- und Asset-Pfade

- `/api/*` bleibt der same-origin Proxy zum privaten `ShellRPG-server`
- `/api/matrix/health` wird im Browser als additive Diagnosequelle fuer den
  `Servermatrix`-Panelpfad konsumiert; wenn der Endpunkt fehlt, bleibt die
  restliche WWW-Oberflaeche bewusst funktionsfaehig
- derselbe Panelpfad zeigt Character-Konflikte jetzt pro Figur verdichtet
  an, inklusive Merge-Gruppen fuer Wissensstand, Fortschritt und Inventar
- pro Konflikt gibt es dort jetzt einen aufklappbaren Drilldown mit
  echten Feldvergleichen fuer bevorzugten Stand, Gegenseite und gemergtes
  Ergebnis sowie kurzen Vergleichs- und Importhinweisen
- fuer groessere Merge-Faelle werden zusaetzlich Delta-Badges und kurze
  serverseitig vorbereitete Diffs gegen den Gewinnerstand gezeigt
- bei sehr grossen Merges kommen serverseitig gewichtete Priorisierungen
  hinzu; der Drilldown trennt diese sichtbar in Plus- und Upgrade-Hinweise
  und zeigt dabei jetzt auch domain-spezifisch gewichtet wichtigere POIs,
  wertigere Ressourcen und kritischere Fortschrittsflags weiter oben an
- dieselben priorisierten Hinweise liefern jetzt zudem einen kurzen
  `reason`, damit der Drilldown die Reihenfolge direkt erklaert
- derselbe Vertrag liefert jetzt auch einen stabilen `reason_code`, den das
  WWW fuer kompakte Kategorien wie `kritisch`, `selten` oder `strategie`
  nutzt
- derselbe Drilldown zeigt jetzt ausserdem Hotspots fuer auffaellige
  Charaktere, Gruppen und Peers, kleine Konflikthistorien
  (`seen_count`/`still_open`) sowie Filter- und Sortierpfade fuer
  Schweregrad, Gruppen und Merge-Dichte
- bei abgeschnittenen Kurz-Diffs bleiben ueber verdeckte
  Reason-Code-/Severity-Rollups auch groessere Merge-Faelle redigiert
  lesbar
- dieselbe WWW-Stadtansicht liest jetzt aus dem Serververtrag auch
  `Stadtfeldgrenzen`, waehrend das NPC-Menue eine redigierte
  `Dialoggrenze` und stage-abhaengig verkuerzte Dienste/Questschritte
  anzeigt
- dieselben Stadt- und NPC-Panels lesen jetzt ausserdem `Stadttraeger`,
  `Materialbasis` und `Ruestkammer` direkt aus dem Serververtrag
- `Neutrale Kommunen` koennen damit auch im WWW als explizite
  multiethnische Stadttraeger erscheinen
- Craftables im NPC-Menue folgen dabei derselben serverseitigen
  Material-/Rezeptbasis statt blossen Platzhalterlisten
- dasselbe NPC-Menue liest jetzt ausserdem `Wirtschaftsprofil`,
  `Handelsfokus`, `Servicefokus`, `Werkfokus` und `Rollen-Craftables`
  fuer dynamische Trader-/Mechanic-Berufe direkt aus dem Serververtrag
- `npc buy ...` und `npc service ...` im Browser koennen damit auch
  berufsgetriebene Haendler- und Werkstattpfade konsumieren, die dieselbe
  Carrier-/Materialbasis weiterverwenden
- dasselbe NPC-Menue liest jetzt ausserdem `Angebotsrotation` und
  `Handelsdynamik` sowie sichtbare prozentuale Marktanpassungen pro Ware,
  damit lokale Stadtwaren, Fraktionsspezialitaeten und rotierende
  Craft-/Enchanting-Gueter als serverseitig gesteuerte Marktlage lesbar
  bleiben
- dieselben Stadt- und NPC-Panels lesen jetzt ausserdem
  `Regionale Knappheit`, `Bauprofil` und `Spezialressourcen`, sodass
  Handelsknappheit, regionale Spezialgueter und fraktionsgebundene
  Bau-/Produktionsneigung ebenfalls direkt aus dem Serververtrag kommen
- dieselben Stadt- und NPC-Panels lesen jetzt ausserdem
  `Regionale Ader` und `Splitterdruck`, sodass Spezialfunde und erste
  kontrollierte Splitterware ebenfalls direkt aus dem Serververtrag kommen
- dieselben Stadt- und NPC-Panels lesen jetzt ausserdem `Nachfrage`,
  `Lagerdruck` und `Karawanenfluss`, damit Stadtlager, Umschlag und
  regionaler Fernbedarf ebenfalls direkt aus dem Serververtrag kommen
- dieselbe Stadtansicht liest jetzt ausserdem `Baustellenkapazitaet` plus
  laufende `Baustellen`, damit parallele Bauauftraege und ihr
  Tick-Fortschritt direkt aus dem Serververtrag kommen
- das Marktpanel bleibt dabei an dieselbe Quelle gebunden: Preisgruende
  duerfen jetzt Wetterdruck und regionale Knappheit gemeinsam erklaeren
- dieselben Markt- und NPC-Panels duerfen jetzt auch oeffentliche
  `Handelsstrom`- und `Karawanenumschlag`-Preisgruende zeigen, wenn
  Stadtlager oder Fernware denselben Servermarkt sichtbar verschieben
- dieselbe Markt- und NPC-Ansicht darf jetzt auch zusaetzliche
  Splitterware wie `Rubin-`, `Obsidian-`, `Smaragd-`, `Opal-` oder
  `Zirkon-Splitter` aus derselben serverseitigen Regional- und
  Carrierlogik lesen
- `/asset/*` liefert WWW-Bildpfade mit GitHub-backed CDN-Prioritaet,
  dynv6-Fallback und lokaler Workspace-Sicherung
- lokale Secret- und Asset-Origin-Listen bleiben betriebsintern und werden
  nicht redigiert veroeffentlicht
- `ShellRPG-www` ist bewusst kein TYPO3-/TypoScript-CMS, sondern das
  eigentliche Spiel-Gateway fuer den Browserpfad
- falls spaeter ein CMS fuer getrennte Public-Inhalte noetig wird, gehoert es
  in einen separaten Pfad und nicht in das Spiel-Gateway selbst

## Sprache

DE/EN lassen sich über die Buttons umschalten.
