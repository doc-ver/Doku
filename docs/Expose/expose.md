
# Expose

- **Typ:** Projektarbeit im Modul Datenbankanwendungen

- **Titel:** DocVer

- **Autoren:** Ken Madlehn, André Grellmann, Pia Schreiner

  

## 1 Vorstellung des Projekthemas

### Beschreibung

DocVer ist ein System zum Verwalten von Dokumenten, das im Browser läuft und für Mobilgeräte optimiert ist. Es bietet eine Volltextsuche über alle Dokumente, die zuvor analysiert und in durchsuchbare PDFs umgewandelt wurden. Falls die Zeit reicht, soll außerdem eine Schnittstelle für Erweiterungen gegeben werden, die auch tiefere Analysen der Dokumente ermöglichen, wie z.B. ein automatisches Fahrtenbuch aus Daten von Tankquittungen.
Durch diese Funktionen soll die Übersicht, über alle gespeicherten Dokumente vereinfacht und dem Nutzer Zeit gespart werden.

###  Anforderungen

#### Grundanforderungen:

Das System soll digitalisierte Dokumente, wie Fotos, Scans, etc., verwalten können. Dafür sollen diese hochgeladen werden und danach automatisch an die richtige Stelle gespeichert, mit Optische Zeichenerkennung (OCR) analysiert und in durchsuchbare PDFs umgewandelt werden. Außerdem sollen sie klassifiziert werden (zuerst manuell, wenn genug Zeit über ist evtl. automatisch). Nachdem die Dokumente in das System aufgenommen wurden, soll eine Volltextsuche über diese möglich sein und eine Übersicht über sie gegeben werden. Die Anwendung soll mobil (via Smartphone oder Tablet) und lokal (am PC o.ä.) benutzbar sein.

 - digitalisierte Dokumente (Foto, Scan etc.) verwalten
 - mit DB synchronisieren
 - klassifizieren
 - von Server analysieren lassen
 - Volltextsuche über analysierte Dokumente
 - Übersicht über Dokumente
 - mobil benutzbar (Smartphone/Tablet)

#### Optionale Anforderungen

Falls genug Zeit gegen Ende übrig bleibt, wären eine automatische Klassifizierung und eine Schnittstelle für Zusatzmodule mit erweiternder Funktionalität (z.B. zum weitergehenden Analysieren bestimmter Dokumente) denkbar.

 - automatische Klassifizierung
 - Schnittstelle für Zusatzmodule mit erweiternder Funktionalität (z.B. zum weitergehenden Analysieren bestimmter Dokumente)

#### Randbedingungen:

Zum Benutzen von DocVer wird ein kompatibles Gerät mit Webbrowser und Internetverbindung benötigt. Zusätzlich kann es sein, dass der Google Chrome Browser, aufgrund der File API, benötigt wird.

- Chrome -> File API?

#### Stakeholder
| Funktion / Relevanz | Name | Kontakt / Verfügbarkeit | Wissen | Interessen / Ziele |
|---|---|---|---|---|
| Interessent | Martin Meyer | Tel. 2837462, von 16-20 Uhr telefonisch erreichbar | Manuelle Dokumentenverwaltung ist ihm zu aufwendig | Möchte Zugang zu dem Service bekommen |
| Nutzer | Franz Müller | Tel. 2871239, von 12-18 Uhr telefonisch erreichbar | Anmeldedaten, Welche Dokumente sollen verwaltet werden | Möchte seine Dokumente verwalten |

#### User Stories
| Funktion | Rolle | In meiner Rolle möchte ich | so dass | Akzeptanz | Priorität |
| --| --| -- | -- | -- | -- |
| Registrierung | Interessent | mich bei DocVer registrieren | für mich ein Konto erstellt wird | Registrierung möglich | Hoch |
| Einloggen | Nutzer | mich bei DocVer einloggen | ich den Service benutzen kann | Einloggen möglich | Hoch |
| Dokument hochladen | Nutzer | Dokumente hochladen | der DocVer diese verwalten kann | Hochladen möglich | Hoch |
| Dokument klassifizieren | Nutzer | Dokumente klassifizieren | ich diese später besser einordnen kann | Dokument klassifiziert | Mittel |
| Dokumente durchsuchen | Nutzer | meine Dokumente durchsuchen | ich das richtige Dokument finde | Dokument gefunden | Hoch |
| Dokumenteninhalt ansehen | Nutzer | den Text eines Dokuments ansehen | ich einen Überblick über den Inhalt bekomme | Textinhalt angezeigt | Hoch |
| Dokument ansehen | Nutzer | ein ausgesuchtes Dokument ansehen | ich mir Original anschauen kann | Dokument angezeigt | Mittel |
| Module | Nutzer | Zusatzmodule hinzufügen und benutzen | ich die Daten des Dokuments weiter verarbeiten kann | Modul benutzbar | Klein (Optional) |
| Automatische Klassifizierung | Nutzer | Dokumente klassifiziert bekommen | ich dies nicht selber machen muss | Dokument richtig klassifieziert | Klein (Optional) |


### Graphische Benutzerschnittstelle

![Mockup](./resources/Mockup.png)

## 2 Geplante Projektarbeit

### Rollenverteilung / Zuständigkeiten

- Noch aufschreiben

### Kommunikationskanäle

Für Besprechungen benutzen wir Discord und für kurze Absprachen oder gegenseitigen Informationsaustausch Whatsapp.

- Discord
- Whatsapp

## 3 Marktanalyse/Stand der Technik

- Gibt es schon vergleichbare Produkte in der Forschung oder am Markt?
	- Abbyy (OCR)
	- Docusnap
- Wie hebt sich die Anwendung von der Konkurrenz ab?
- Wie lösen andere das Problem? Wovon kann man sich inspirieren lassen?

## 4 Verwendete Technologien

### Datenbank (Oracle / Relational / NoSQL)

Zur Datenverwaltung benutzen wir eine Kombination aus einer relationellen Datenbank und einem Webspeicher. Für den Webspeicher nutzen wir Nextcloud, um darin die Rohdateien und die generierten durchsuchbaren PDFs zu speichern. Als Datenbank benutzen wir eine Oracle Datenbank und speichern dort die Referenzen zu Roh- und PDF-Dateien, sowie alle darin vorkommende Worte, zugewiesene Tags und Benutzerzugehörigkeit. Um eine (eingeschränkte) Offlinefähigkeit bieten zu können, sollen Teile der Datenbank (z.B. Übersichtsergebnisse von vorherigen Suchen) auf dem Endgerät per File API oder in der Offline DB gecasht werden.

- Oracle -> SSH Zugang Linux
  - ggf. Nutzerdaten
  - Referenz zu Dateien im WebDav
  - Volltext ohne Wordposition
- WebDav (Nextcloud)
  - Dateien
  - Durchsuchbare PDF ~2-5MB
- Offline DB (Index Browser) -> Evaluation
  - Cache

### Frontend (Desktop / Webanwendung / Mobil)

Das Frontend läuft auf den oben genannten Endgeräten im Browser als Progressive Web App (PWA) mit Responsive Web Design. Als Web-Framework benutzen wir dafür Angular.

- Angular
- Progressive Web App (PWA)
- Responsive Web Design

### Backend (Sprache)



- NodeJS Server
  - Apollo - GraphQL (Datenaustausch)
  - FirebaseAdmin - Usercreation / Verifizierung
- OCR Server
- Arbeitspaket -> API Input Keywords / Response Vorkommen in Datei

### Environment

Unsere Anwendung soll über Docker deployed werden können.

- Docker

### Kommunikation Server / Client

- DB ↔ GraphQL ↔ Angular ↔ Client
- Datei ↔ Client ↔ Webdav ↔ OCR API ↔ WebDav
- OCR API ↔ [Volltext] ↔ DB

### Code Versionierung / Kollaboratives arbeiten

Um unseren Code zu versionieren und weitere Dateien (z.B. zur Dokumentation) untereinander auszutauschen, benutzen wir unsere dafür angelegte GitHub-Organisation. 

- Git

## 5 Zeitplanung

### Meilensteine

- **Meilenstein 1:** Konzept und Mockup
- **Meilenstein 2:** Prototyp und Dokumentation
- **Endabgabe:** Finales Produkt

### Wochenplanung

| Woche| Planung |
|--|--|
| 20.04.20 - 26.04.20 | Kick Off |
| 27.04.20 - 03.05.20 | Recherche + Machbarkeit und Prototyp Architektur |
| 04.05.20 - 10.05.20 | Überarbeitete Prototyp Architektur und Mockup Ideen |
| 11.05.20 - 17.05.20 | Klickdummy für Webanwendung und OCR fertig, Datenbankarchitektur definiert, NodeJS Server mit Firebase aufgesetzt |
| 18.05.20 - 24.05.20 | Evaluation Oracle DB mit und ohne graphQL, Festlegen der finalen Version der Architektur |
| 25.05.20 - 31.05.20 |  |
| 01.06.20 - 07.06.20 |  |
| 08.06.20 - 14.06.20 |  |
| 15.06.20 - 21.06.20 |  |
| 22.06.20 - 28.06.20 |  |
| 29.06.20 - 05.07.20 |  |
| 06.07.20 - 12.07.20 |  |
| 13.07.20 - 19.07.20 |  |

## A Gliederungsentwurf

Gliederungsentwurf für Dokumentation der Endabgabe

 1. Einleitung
 2. --
 3. --
 4. --
 5. Evaluierung
 6. Fazit
 7. Ausblick

## B Vorläufiges Literaturverzeichnis
Überblick über die bisher ermittelten Literaturquellen (Alphabetisch nach den Namen der Autoren sortiert)

### Literatur
[ABC] Beschreibung
