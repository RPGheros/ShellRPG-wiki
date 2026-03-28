# Peer-Savepoint-Aushandlung beim Boot

Beim Start vergleicht der Server lokale und per Bootstrap erreichbare Savepoint-Metadaten. Priorität: höchster Tickstand, dann jüngster Zeitstempel. Wenn ein entfernter Savepoint gewinnt, wird dessen Zustand geladen.
