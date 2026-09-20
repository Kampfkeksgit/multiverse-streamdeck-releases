# Multiverse Stream Deck – Releases

Hier liegen die fertigen Dateien der [Multiverse-Stream-Deck](https://github.com/Kampfkeksgit)-Software.
**Quellcode ist hier keiner** — dieses Repository trägt nur die Releases.

## Warum ein eigenes Repository

Die installierte Software fragt GitHub **ohne Anmeldung**, ob es etwas
Neueres gibt. Auf ein privates Repository antwortet GitHub mit `404` — genau
wie auf eines ohne Release, und die Datei bekäme ein Nutzer ohnehin nicht
herunter. Ein Token mitzuliefern ist keine Lösung: wer die Software hat, kann
es lesen.

Also liegen die Releases öffentlich und der Quellcode nicht.

## Was in einem Release liegt

| Datei | Was es ist |
|-------|------------|
| `MultiverseStreamDeck-Setup-<version>.exe` | Das Setup der PC-Software |
| `multiverse_master-<version>.bin` | Firmware für das Master-Modul (ESP32-S3) |
| `manifest.json` | Beschreibt beides: Version, Dateiname, SHA-256 |

Der **Tag** eines Release sagt nichts darüber, welche Version darin steckt:
Software und Firmware haben eigene Versionen und wandern nicht im
Gleichschritt. Verbindlich ist allein das `manifest.json`.

Die Software sucht im **neuesten** Release nach `manifest.json`, liest daraus
die Version und lädt die genannte Datei. Die `SHA-256` wird vor dem Start
nachgerechnet; stimmt sie nicht, wird die Datei gelöscht statt ausgeführt.

## Installieren

Das Setup herunterladen und ausführen. Es fragt, ob für dich allein
(ohne Administrator) oder für alle Benutzer.

Ohne Signatur zeigt Windows dabei „Der Computer wurde durch Windows
geschützt". Über **Weitere Informationen → Trotzdem ausführen** geht es
weiter; das legt sich erst mit einem Zertifikat.

Spätere Fassungen holt sich die Software selbst: sie meldet sich, sobald es
etwas Neues gibt, und installiert es auf Knopfdruck.
