# Economy

Der aktuelle Vertical Slice bildet eine kleine, aber echte Marktlogik ab.

## Stadtregel
Jede Stadt erhält pro Stadtstufe:
- 1 NPC-Händler
- +4 Basisressourcen

## Sichtbare Märkte im Slice
- Graufurt
- Valmora-Hain
- Aschenwall
- Eisenhall
- Freiwinkel
- Marktwacht
- Gildenhafen

## Regionale Knappheit und Bauprofile

- dieselbe sichere Serverlinie nutzt jetzt echte regionale
  Handelsknappheitsprofile statt nur starre Warenlisten
- Stadt- und NPC-Vertraege duerfen dafuer redigierte Linien wie
  `Regionale Knappheit`, `Bauprofil` und `Spezialressourcen` zeigen
- `Haendlergilde` ist dabei jetzt ein redigierter multiethnischer
  Stadt-/Handelskoerper, der dieselben Markt- und Bauprofile konsumiert
- `ECO-005` ist redigiert jetzt produktiv abgeschlossen:
  Bauprofile wirken auf Baukosten, Produktion, Spezialwaren und echte
  Baustellenkapazitaet
- redigierte Stadtvertraege duerfen dafuer jetzt auch
  `Baustellenkapazitaet` und laufende `Baustellen` zeigen, solange nur
  sichtbare Bauauftraege und Tick-Fortschritt offengelegt werden

## Regionale Adern und Splitterdruck

- dieselbe Serverlinie fuehrt jetzt ueber `regional_yields` erste
  regionale `Adern`, die Gathering, Markt und NPC-Waren zugleich koppeln
- `gather ...` kann dadurch je nach Region und Carrier neben Grundressourcen
  auch Spezialfunde wie `Hainharz`, `Magnetit`, `Infernit`,
  `Moorbernstein` oder `Frostsalz` heben
- dieselben redigierten Stadt- und NPC-Vertraege duerfen dazu jetzt auch
  `Regionale Ader` und `Splitterdruck` zeigen
- erste kontrollierte Splitterware wie `Rubin-`, `Obsidian-`,
  `Smaragd-`, `Opal-`, `Bernstein-` und `Zirkon-Splitter` darf dabei als
  sichtbare Markt- und Fokusware erscheinen, ohne interne Spawn-,
  Monster- oder Droplogik offenzulegen

## Handelsstroeme und Stadtlager

- dieselbe sichere Serverlinie fuehrt jetzt ueber `city_trade` erste
  echte Handelsstroeme aus Carrier, Stadtlager, Gebaeuden und
  Regionalprofilen zusammen
- redigierte Stadt- und NPC-Vertraege duerfen dazu jetzt auch
  `Nachfrage`, `Lagerdruck` und `Karawanenfluss` zeigen
- Stadtticks duerfen damit oeffentlich sichtbar Nachfragegueter aus
  `city.storage` verbrauchen, erste Fernware zufuehren und kontrollierte
  Stadtgueter wie `Magnetitlinse` oder `Moorbernstein-Amulett` in die
  sichtbare Umschlaglinie heben
- dieselbe Marktlogik darf dazu jetzt auch oeffentliche
  `Handelsstrom`- und `Karawanenumschlag`-Preisgruende zeigen, solange nur
  sichtbarer Marktdruck und keine internen Simulationsheuristiken
  erklaert werden

## Redigierte Ausbauachsen

- starke Fraktions- und Splitteroekologie darf kuenftig regionale Maerkte,
  Jagd, Spawns und Rohstofffluesse mitpraegen
- Spezialressourcen wie `Infernit`, `Magnetit`, `Hainharz`,
  `Frostsalz` und `Moorbernstein` laufen jetzt bereits als erste
  fraktions- und regiongebundene Markt-/Craftingachsen
