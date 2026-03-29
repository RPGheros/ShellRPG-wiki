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
- Medienbild/GIF pro Tile oder Encounter
- Karte mit FOW, POIs und Ressourcen
- Inventar und Ausrüstung
- Markt
- Quests / Buffs / Journal
- sichtbare Befehle

## Gateway- und Asset-Pfade

- `/api/*` bleibt der same-origin Proxy zum privaten `ShellRPG-server`
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
