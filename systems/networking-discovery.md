# Netzwerk, Discovery und Handshake

ShellRPG v0.6.6 erweitert den privaten Serverkern um drei eng verbundene Infrastrukturbausteine:

1. **LAN-Discovery** per Broadcast-Beacon
2. **WAN-Peer-Bootstrap** über konfigurierte Peers
3. **Handshake-Login** mit SHA-256-basierter Sitzungsableitung

## Discovery-Modell
- **LAN:** Server senden regelmäßig Broadcast-Beacons ins lokale Netz.
- **Internet/WAN:** Server können über eine konfigurierbare Peer-Liste andere Nodes abfragen.
- **Ziel:** lokale Autarkie im LAN und kontrollierte Peer-Verbindung über bekannte Internet-Nodes.

## Oeffentliche Betriebsgrenze

- redigierte Dokumentation benennt nur sichere Bedienpfade und Betriebsrollen
- lokale dynv6-Tokens oder Secret-Dateien werden nie dokumentiert
- dynv6 kann fuer einen redigierten DynDNS-Pfad genutzt werden, ersetzt aber
  kein vollwertiges Multi-Origin-Routing

## Handshake-Login
Der Login ist als **hashbasierte Sitzungsaushandlung** modelliert. Dabei wird aus Client-Nonce, Server-Nonce und einem Server-Pepper ein Sitzungs-Token abgeleitet.

Wichtig:
- SHA-256 wird hier als **Hashfunktion** verwendet.
- Das ist **keine symmetrische oder asymmetrische Verschlüsselung**.
- Der Zweck ist Sitzungsbindung und Integrität, nicht Geheimtexttransport.

## Relevante Endpunkte
- `/api/login`
- `/api/discovery/status`
- `/api/savepoint/status`
