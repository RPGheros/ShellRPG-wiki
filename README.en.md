[Deutsch](README.md) | English

🏛️☠️🌿                                                                 🌿☠️🏛️
╔══════════════════════════════════════════════════════════════════════════════╗
║  _/\______________________________________________________________/\\_     ║
║  \_/\\                                                            /\_/     ║
║  /_/\\   U N R O L L E D   S C R O L L                            /\_\     ║
║  \_\/____________________________________________________________\/_/     ║
╚══════════════════════════════════════════════════════════════════════════════╝
# ShellRPG-wiki · v0.7.6

## 1. Description

**Artifact role:** Redacted documentation and knowledge layer for lore, systems, usage, glossary, FAQ, and project orientation.

**Purpose:** This artifact explains ShellRPG from player, designer, and integration perspectives without exposing private server details. It functions like a project-internal wiki with content pages, cross-links, and navigation.

**Connected artifacts:**
- `ShellRPG-server` remains private and is only described in abstracted form here.
- `ShellRPG-client` and `ShellRPG-www` are documented from the usage and integration perspective.
- The wiki is the central public navigation aid across worldbuilding, mechanics, and terminology.

**Governance:** `WIKI-REDACTED`

The actual content navigation starts in [`index.md`](index.md). That page provides the Wikipedia-like table of contents with logically grouped content pages.

## 2. Dependencies

- Markdown viewer or GitHub/GitLab rendering
- optional local web server for easier browsing

## 3. Installation

A Markdown viewer or git hosting frontend is enough for direct reading.

Optional local browser mode:
```bash
python -m http.server 8090
```

Then open:
```text
http://127.0.0.1:8090/
```

Current redacted canon highlights:
- `Monster` is a distinct faction; `Hive` is treated as a parasitic monster
  subfaction with ork and dwarf splitters
- wildlife is a dedicated NPC faction with prey/predator separation and
  tile-bound migration
- factions and species may gain their own class, recipe, enchanting, and
  crafting traditions
- `Infernit`, material weapon families, and six ring slots are part of the
  visible expansion roadmap

## 4. Feedback & Contribution

Feedback should call out missing cross-links, unclear terms, or editorial inconsistencies.
Contribution must respect the redaction boundary: useful to the public, but never reconstructing the private core.
New content pages should always be added to the wiki navigation structure.

🏛️🌿☠️══════════════════════════════════════════════════════════════☠️🌿🏛️
