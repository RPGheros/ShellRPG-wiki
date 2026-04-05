# Terminal-Guide

## Start

```bash
python -m shellrpg_client
```

## Live-Status

Der Terminal-Client pollt den Server live während laufender Aktionen wie `hunt`, `gather` und `explore`.
Terminal-Medien bleiben lokal; die WWW-/CDN-Assetkette ist davon getrennt.
Wenn der Server Matrix-/Peer-Diagnostik liefert, erscheint in der letzten
HUD-Zeile zusaetzlich ein kompakter `Mx:`-Hinweis fuer den aktuellen
Matrixzustand.

## Wichtige Befehle

- `hunt N`
- `hunt 1,2`
- `gather wood`
- `gather gems`
- `explore`
- `attack` / `guard` / `dodge`
- `cast soultrap`
- `read chronicle_graufurt`
- `book next`
- `lang en` / `lang de`

## Matrixdiagnose

- `matrix health` zeigt den kompakten Matrixzustand mit Severity- und
  Reason-Code-Rollups sowie Hotspots
- `matrix status` erweitert dieselbe Sicht um bevorzugten Stand und
  Peer-Liste
- `matrix conflicts` zeigt Character-Konflikte mit stabilen IDs,
  Feld-Merges und kurzen Deltas
- `matrix conflicts <filter>` filtert lokal z. B. nach Character,
  Severity, Reason-Code, Feldname, `conflict_id` oder `field_conflict_id`
- `matrix inspect <conflict_id|field_conflict_id|character>` zeigt einen
  Drilldown mit Preferred-, Fallback- und Gemerged-Preview, Gewinnerseite,
  Merge-Modus und priorisierten Delta-Gruenden
- `matrix peers` fokussiert nur die Peer-Diagnose
