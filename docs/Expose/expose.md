
# Expose

- **Typ:** Projektarbeit im Modul Datenbankanwendungen

- **Titel:** DocVer

- **Autoren:** Ken Madlehn, André Grellmann, Pia Schreiner

  

## 1 Vorstellung des Projekthemas

### Beschreibung

DocVer ist ein System zum Verwalten von Dokumenten, welches im Browser läuft und für Mobilgeräte optimiert ist. Durch die Analyse verwalteter Dokumente, bietet es eine Volltextsuche über alle Dokumente an. Optional, bietet DocVer außerdem eine Schnittstelle für Erweiterungen, welche tiefere Analysen der Dokumente ermöglicht.
Durch eine strukturierte Darstellung hochgeladener Dokumente bekommt der Nutzer eine einfache und zeiteffiziente Möglichkeit, seine Dokumente zu durchsuchen und notwendige Dokumente schnell zu finden. 

###  Anforderungen

#### Grundanforderungen:

Das System soll digitalisierte Dokumente, wie z.B. Fotos oder Scans verwalten können. Dafür sollen diese hochgeladen werden und anschließend automatisch zum Nutzer zugeordnet gespeichert, mit optischer Zeichenerkennung (OCR) analysiert und in durchsuchbare PDFs umgewandelt werden. Außerdem sollen sie klassifiziert werden können. Für die Klassifizierung hat der Nutzer einige Standard Kategorien, welche bereits angelegt worden sind und nicht gelöscht werden können. Weiterhin kann jeder Nutzer sich eigene Kategorien anlegen, in welche er seine Dokumente anschließend klassifizieren kann. Die Klassifizierung soll zunächst manuell erfolgen, in dem der Nutzer entweder beim Upload eines Dokuments die Kategorie auswählt, oder das Dokument später in einer Kategorie klassifiziert.  Nachdem die Dokumente in das System aufgenommen wurden, soll eine Volltextsuche über diese möglich sein und eine Übersicht über sie gegeben werden. Auch kann eine Suche nach Begriffen durchgeführt werden, welche Dokumente liefert, die diese Begriffe enthalten. Die Anwendung soll mittels eines Browsers mobil (via Smartphone oder Tablet) sowie lokal (am PC) benutzbar sein. 

#### Optionale Anforderungen

Falls genug Zeit gegen Ende übrig bleibt, wäre eine automatische Klassifizierung denkbar, die hochgeladene Dokumente automatisch in die passende Kategorie einsortieren kann. Außerdem wäre eine Schnittstelle mit erweiternder Funktionalität möglich, welche tiefere Analysen der Dokumente durchführt und es ermöglicht Zusatzmodule zu implementieren, welche die Daten analysiert. Ein Beispiel dafür wäre ein automatisches Fahrtenbuch, welches aus Daten von Tankquittungen erstellt wurde.



#### Randbedingungen:

Zum Benutzen von DocVer wird ein kompatibles Gerät mit Webbrowser und Internetverbindung benötigt. Zusätzlich ist es möglich, dass der Google Chrome Browser, aufgrund der File API, benötigt wird.



#### Stakeholder
| Funktion / Relevanz | Name | Kontakt / Verfügbarkeit | Wissen | Interessen / Ziele |
|---|---|---|---|---|
| Interessent | Martin Meyer | Tel. 2837462, von 16-20 Uhr telefonisch erreichbar | Manuelle Dokumentenverwaltung ist ihm zu aufwendig | Möchte Zugang zu dem Service bekommen |
| Nutzer | Franz Müller | Tel. 2871239, von 12-18 Uhr telefonisch erreichbar | Anmeldedaten, Welche Dokumente sollen verwaltet werden | Möchte seine Dokumente verwalten |

#### User Stories
| Funktion | Rolle | In meiner Rolle möchte ich | so dass | Akzeptanz | Priorität |
| --| --| -- | -- | -- | -- |
| Registrierung | Interessent | mich bei Do-Ver registrieren | für mich ein Konto erstellt wird | Registrierung möglich | Hoch |
| Anmeldung | Nutzer | mich bei DocVer einloggen | ich den Service benutzen kann | Einloggen möglich | Hoch |
| Dokument hochladen | Nutzer | Dokumente hochladen | der DocVer diese verwalten und analysieren kann | Hochladen möglich | Hoch |
| Kategorie anlegen | Nutzer | Kategorie anlegen | ich meine hochgeladenen Dokumente in eigene Katgorien klassifizieren kann | Kategorie angelegt | Mittel |
| Kategorie löschen | Nutzer | Kategorie löschen | Dokumente nicht mehr mit dieser Kategorie klassifiziert werden können | Kategorie gelöscht | Mittel |
| Dokument klassifizieren | Nutzer | Dokumente klassifizieren | ich diese später besser einordnen kann | Dokument klassifiziert | Mittel |
| Dokumente durchsuchen | Nutzer | meine Dokumente durchsuchen | ich das richtige Dokument finde | Dokument gefunden | Hoch |
| Dokumenteninhalt ansehen | Nutzer | den Text eines Dokuments ansehen | ich einen Überblick über den Inhalt bekomme | Textinhalt angezeigt | Hoch |
| Dokument ansehen | Nutzer | ein ausgesuchtes Dokument ansehen | ich mir Original anschauen kann | Dokument angezeigt | Mittel |
| Dokument löschen | Nutzer | ein Dokument löschen | das Dokument aus dem System entfernt wird | Dokument gelöscht | Hoch |
| Module | Nutzer | Zusatzmodule hinzufügen und benutzen | ich die Daten des Dokuments weiter verarbeiten kann | Modul benutzbar | Niedrig (Optional) |
| Automatische Klassifizierung | Nutzer | Dokumente klassifiziert bekommen | ich dies nicht selber machen muss | Dokument richtig klassifiziert | Niedrig (Optional) |


### Graphische Benutzerschnittstelle

![Mockup](./resources/Mockup.png)

## 2 Geplante Projektarbeit

### Rollenverteilung / Zuständigkeiten

- **André Grellmann:** Dokumentation, NodeJS-Server (für Anbindung zur Datenbank)
- **PiaSchreiner:** Frontend, NodeJS-Server (Für die Kommunikation zwischen Frontend und Backend)
- **Ken Madlehn:** OCR, Infrastruktur-Services, Stored Procedures, Volltextsuche

### Kommunikationskanäle

Für unsere Besprechungen wird Discord eingesetzt, um dadurch die Bildübertragung nutzen zu können und gemeinsam etwas zu erarbeiten. Für kurze Absprachen sowie den zwischenzeitlichen Informationsaustausch nutzen wir Whatsapp.



## 3 Marktanalyse/Stand der Technik

Vergleichbare Produkte auf dem Markt sind z.B. `Abbyy FineReader` und `bitfarm-Archiv`. Bei beiden handelt es sich um Dokument Management Systeme (DMS). Diese bieten viele Funktionen um die OCR-Funktion herum an, wie beispielsweise PDF-Erstellung / -Bearbeitung /-Signierung. Über solche Funktionen könnte man in den Modulen nachdenken (falls die Modul-Schnittstelle implementiert werden würde).

Bei Abbyy handelt es sich um ein kommerzielles System, sodass nicht viel über die Implementierung bekannt ist. Laut eigenen Angaben nutzt es für die OCR Funktion ein KI-System. 

Bitfarm-Archiv ist eine Open-Source Software und bietet eine kostenlose Version an. Für die Datenverwaltung wird MySQL benutzt, was für unser System auch eine denkbare Alternative ist.
Beide Systeme empfehlen für die Serverseite einen Windows-Server (und bitfarm für sehr kleine Anwendungen auch normales Windows) und bieten einen Windows-Client. bitfarm-Archiv bietet zudem noch einen Web-Viewer und iOS-, sowie Android-Apps an. 

Unser System hebt sich dadurch ab, dass es sehr viel portabler ist, da für die Serverseite lediglich Docker verfügbar sein muss und die Clientseite durch die Webanwendung alle Endgeräte, bis auf manche Sonderfälle, abdeckt, welche einen Browser haben. 

## 4 Verwendete Technologien

### Datenbank

Zur Datenverwaltung benutzen wir eine Kombination aus einer relationalen Datenbank und einem Webspeicher. Für den Webspeicher setzen wir Nextcloud ein, um darin die Rohdateien und die generierten durchsuchbaren PDFs zu speichern. Als Datenbank benutzen wir eine Oracle Datenbank und speichern dort die Referenzen zu Roh- und PDF-Dateien, sowie alle darin vorkommende Worte, zugewiesene Tags und Benutzerzugehörigkeit. Um eine (eingeschränkte) Offlinefähigkeit bieten zu können, sollen Teile der Datenbank (z.B. Übersichtsergebnisse von vorherigen Suchen) auf dem Endgerät per File API oder in der Offline DB gecached werden.

### Frontend

Das Frontend läuft auf den oben genannten Endgeräten im Browser als Progressive Web App (PWA). Dabei wird ein responsives Design mit Hilfe von Bootstrap eingesetzt um die Ansicht auf allen Endgeräten optimal darstellen zu können. Als Web-Framework wird Angular in der Version 9 genutzt.

### Backend

Das Backend besteht aus zwei Komponenten. Zum einen nutzen wir einen NodeJS Server mit JavaScript und verschiedener Komponenten. Für die Authentifizierung wird das Firebase Admin SDK genutzt, da wir Google Firebase für die User- bzw. Zugriffskontrolle nutzen. Da die Kommunikation zwischen Backend und Frontend mit Hilfe von REST stattfindet, enthält der NodeJS Server zusätzlich einen Express Server, welche die notwendigen Routen definiert.

Die zweite Komponente ist ein OCR Server, welcher mit Python implementiert wird. Dieser nutzt Tesseract zum Erkennen der Texte und OpenCV zum vorherigen Bearbeiten der zu analysierenden Bilddatei.

### Environment

Zum Speichern der hochgeladenen Bilddateien und generierten PDFs nutzen wir einen Nextcloud Server. Alle weiteren Daten werden in einer Oracle Datenbank verwaltet. Das ganze Projekt soll Hilfe von Docker deployed werden können. Dabei gibt es folgende Container:

- Oracle DB
- OCR Server
- NodeJS Server
- Angular PWA Anwendung
- Nextcloud Server

### Kommunikation Server / Client

Der Client fragt Daten über den REST-Server an. Dieser fragt Daten aus der Datenbank oder der Nextcloud ab und sendet anschließend die Daten als JSON und die Dateien in dem gespeicherten Format zurück. Der REST-Server nutzt die ORM-Library Sequelize, für den Datanaustausch mit der Datenbank.
Von dem Client können Daten nicht nur abgefragt, sondern auch Bilddateien von den zu analysierenden Dokumenten hochgeladen werden. Nachdem eine solche zum REST-Server hochgeladen wurde, speichert dieser die Datei auf dem Nextcloud Server und Daten wie Name und Speicherort in der Oracle Datenbank und sendet dem OCR Server ein Triggersignal. Dieser fragt dann aus der Datenbank unanalysierte Dateien ab, besorgt diese von der Nextcloud, analysiert diese und speichert die daraus resultierenden Daten in die Datenbank und das die generierte durchsuchbare PDF Datei in die Nextcloud.

![Sequenzdiagramm](../Overview/resources/Diagramme/doc-ver_Diagramme-Sequenzdiagramm.svg)

- DB ↔ GraphQL ↔ Angular ↔ Client
- Datei ↔ Client ↔ Webdav ↔ OCR API ↔ WebDav
- OCR API ↔ [Volltext] ↔ DB

### Code Versionierung / Kollaboratives arbeiten

Um unseren Code zu versionieren sowie weitere Dateien untereinander auszutauschen, benutzen wir unsere dafür angelegte GitHub-Organisation. Die Dokumentation ist dabei in Markdown verfasst und kann über GithubPages[^docs] eingesehen werden. Für die Versionierung im Git haben wir vier verschiedene Repositories angelegt:

- NodeJS Server
- Webanwendung
- OCR Server
- Dokumentation

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
| 25.05.20 - 31.05.20 | Mockups & Frontend vervollständigen, Einarbeitung in Sequelize, Exposé ausformulieren |
| 01.06.20 - 07.06.20 | Benötigte REST-Funktionen vorbereiten, Datenbankanbindung steht |
| 08.06.20 - 14.06.20 | Userfunktionalität fertigstellen |
| 15.06.20 - 21.06.20 | Volltextsuche fertigstellen, Settings-Funktionalität fertigstellen |
| 22.06.20 - 28.06.20 | Dokumenten-Funktionalität fertigstellen |
| 29.06.20 - 05.07.20 | Tests durchführen, Dokumentation abschließen |

## A Gliederungsentwurf

Gliederungsentwurf für Dokumentation der Endabgabe

 1. Einleitung
 2. Planung / Diagramme
 3. Features
 4. Genutzte Technologien
 5. Fazit
 6. Ausblick

## B Vorläufiges Literaturverzeichnis
- [Abbyy FineReader](https://www.abbyy.com/de-de/finereader/)
- [bitfarm-Archiv](https://www.bitfarm-archiv.de/dokumentenmanagement/)
- [Firebase](https://firebase.google.com/)
- [Sequelize for Oracle](https://www.npmjs.com/package/sequelize-oracle)



------



[^docs]: Link zur Dokumentation: https://doc-ver.github.io/Doku/#/.
