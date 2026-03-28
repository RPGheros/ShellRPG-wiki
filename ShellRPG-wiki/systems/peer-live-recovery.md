# Peer-Live-Recovery

Diese Seite beschreibt den Live-Recovery-Pfad beim Rejoin.

- Login mit `rejoin=true`
- Peer-Vergleich nach höchstem Tick, dann Zeitstempel
- Remote-Import nur wenn neuer
- manueller Trigger über `server recover live` oder `/api/recover/live`
