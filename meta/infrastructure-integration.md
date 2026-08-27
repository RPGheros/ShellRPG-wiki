# Wiki-Integration in die zentrale WWW-Infrastruktur

## Ziel

`ShellRPG-www` ist der primäre öffentliche Einstiegspunkt. Das redigierte Wiki
bleibt eine eigenständige Dokumentationsverantwortung und wird über die eigene
Subdomain `https://wiki.shellrpg.tld` logisch mit WWW verbunden.

```text
Internet
  |
  +-- https://www.shellrpg.tld   -> ShellRPG-www (Hauptendpunkt)
  |
  +-- https://wiki.shellrpg.tld  -> ShellRPG-wiki (redigierte Dokumentation)

ShellRPG-www
  |
  +-- privates /api/* -> ShellRPG-server
  +-- WWW-Bilder      -> ShellRPG-cdn

ShellRPG-wiki
  +-- kein CDN-Verbrauch
```

## Warum Subdomain statt `/wiki`

Das Wiki-Repository besteht aus redigiertem Markdown und besitzt keine eigene
Python-Webruntime im WWW-Gateway. Eine Pfadmontage unter `/wiki` würde die
Dokumentationsauslieferung unnötig in die Anwendungsruntime mischen. Die
Subdomain hält Verantwortlichkeiten, Deployment und Rollback getrennt, während
Navigation, DNS/TLS-Governance und öffentliche Markenführung konsistent bleiben.

## Navigation

- WWW verlinkt sichtbar auf `https://wiki.shellrpg.tld`.
- Das Wiki verlinkt zurück auf `https://www.shellrpg.tld`.
- Alte Wiki-URLs sollen am äußeren Reverse Proxy bzw. am bisherigen Wiki-Host
  auf die kanonische Wiki-Subdomain weitergeleitet werden.
- Redirects werden vor Abschaltung alter Hosts auf Schleifen und Pfaderhalt
  geprüft.

## Authentifizierung, Cookies und Sessions

Das Wiki ist gemäß Manifest öffentlich/redigiert. Deshalb ist aktuell keine
geteilte Browser-Session mit WWW erforderlich.

- WWW-Sitzungscookies bleiben host-only und werden nicht auf `.shellrpg.tld`
  erweitert.
- Das Wiki erhält keine Session-Tokens vom CDN.
- Falls später geschützte Wiki-Bereiche erforderlich werden, soll SSO an einer
  zentralen WWW-/Identity-Schicht angebunden werden. Das CDN bleibt davon
  vollständig getrennt.

## CDN-Grenze

Das Wiki darf `ShellRPG-cdn` nicht als Host für eigene Inhalte oder Assets
verwenden.

- keine Wiki-Bilder in `assets/www/public/media`
- keine Wiki-CSS-/JS-Dateien im CDN
- keine Wiki-Uploads an den CDN-Endpunkt
- keine CDN-Schreibschnittstelle aus dem Wiki

Dokumentationsseiten dürfen den WWW/CDN-Betriebsweg redigiert beschreiben, aber
sie konsumieren ihn nicht als eigenen Hosting-Pfad.

## Reverse Proxy und TLS

Die Repositories enthalten keine produktive Reverse-Proxy- oder Zertifikats-
konfiguration. Im Deployment gelten daher folgende Anforderungen:

- `wiki.shellrpg.tld` ausschließlich über HTTPS veröffentlichen.
- nur den tatsächlich benötigten Wiki-Origin hinter dem äußeren Proxy öffnen.
- keine privaten WWW-/Server-Ports über die Wiki-Route exponieren.
- HSTS/CSP/CORS nur passend zur tatsächlich verwendeten Wiki-Runtime setzen;
  keine pauschalen `*`-Freigaben einführen.

## Validierung vor Cutover

1. Wiki-Startseite über HTTPS erreichbar.
2. WWW -> Wiki und Wiki -> WWW funktionieren.
3. Bestehende wichtige Wiki-URLs bleiben erhalten oder redirecten pfaderhaltend.
4. Keine Redirect-Schleifen.
5. Keine Mixed-Content-, CORS- oder Cookie-Fehler.
6. Netzwerkprüfung zeigt keine Requests des Wikis an den WWW-CDN-Bildhost.
7. Alte Wiki-Einstiege erst nach erfolgreicher Validierung deaktivieren.
