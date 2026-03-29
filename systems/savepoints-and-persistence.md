# Savepoints und Persistenz

ShellRPG v0.6.6 speichert Savepoints serverseitig.

## Standardauslöser
- nach Tick
- nach Stadtbau
- nach Miliz-/Garnisonsänderungen
- nach Crafting/Socketing/Enchanting
- nach Markttransaktionen
- nach Questfortschritt
- vor Shutdown (empfohlen)

## Prioritätsregel
Wenn mehrere Server Savepoint-Metadaten austauschen, gilt der Savepoint mit:
1. dem **höchsten Tickstand**
2. bei Gleichstand dem **neueren Zeitstempel**

als priorisierte Wiederanlaufbasis.
