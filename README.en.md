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

## Maintenance Note

- For relevant content, contract, feature, or editorial changes touching this
  endpoint, update `README.md`, `README.en.md`, and `VERSION` together.

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
- the redacted terminal guide now also documents the local `matrix` command
  tree for matrix/peer diagnostics in the public terminal client
- the same redacted terminal path now also describes the compact `Mx:` HUD
  hint for ongoing matrix health inside the terminal client
- the same redacted terminal path now also documents filterable
  `matrix conflicts` output and a dedicated `matrix inspect` drilldown for
  character, conflict, and field IDs
- redacted map and city views may now also expose first civilization and
  governance hints such as lead bodies, development stages, protectorate
  state, and autonomy recovery without leaking private war or diagnosis
  heuristics
- those same redacted city views may now also describe that occupation and
  autonomy state as a dynamically advancing server-side condition rather than
  as a purely static marker
- the same redacted path may now also use development stages as real city
  field, material, and dialogue limits: city views may expose redacted `city
  field limits`, while NPC and WWW consumers may read shorter or richer
  interaction paths depending on stage
- redacted city and NPC views may now also expose explicit `city carrier`,
  `material basis`, and `armory basis` lines whenever the safe server
  contract provides them
- `Neutral Communes` may therefore now appear redacted as real multiethnic
  city carriers without exposing internal governance or recipe heuristics
- redacted NPC views may now also expose `economy profile`, `trade focus`,
  `service focus`, `craft focus`, and `role craftables` whenever the same
  safe server view derives trader/mechanic professions from carrier- and
  material-bound runtime profiles
- those same redacted NPC paths may now also describe `offer rotation` and
  `market dynamics` as long as they stay limited to public stock changes and
  visible per-item market pressure
- those same redacted city and NPC paths may now also describe `regional
  scarcity`, `build profile`, and `special resources` as long as they stay
  limited to public-safe trade scarcity, build/production tendencies, and
  visible specialty stock
- those same redacted city and NPC paths may now also describe `regional
  yield` and `shard pressure` as long as they stay limited to public-safe
  specialty finds, controlled shard stock, and visible market availability
- those same redacted city and NPC paths may now also describe `demand`,
  `storage pressure`, and `caravan flow` as long as they stay limited to
  public-safe city storage state, visible throughput, and redacted
  long-range need
- those same redacted city paths may now also describe
  `construction capacity` and active `construction sites` as long as they
  only expose public-safe build orders and visible tick progress
- the `Merchant Guild` may therefore now appear redacted as a multiethnic
  city and trade body whenever the same safe server contract already carries
  it canonically through registry, spawn, and governance consumers
- redacted market and NPC paths may now also describe public `trade flow`
  and `caravan throughput` price reasons as long as they stay limited to
  visible market pressure instead of internal simulation heuristics

## 4. Feedback & Contribution

Feedback should call out missing cross-links, unclear terms, or editorial inconsistencies.
Contribution must respect the redaction boundary: useful to the public, but never reconstructing the private core.
New content pages should always be added to the wiki navigation structure.

🏛️🌿☠️══════════════════════════════════════════════════════════════☠️🌿🏛️
