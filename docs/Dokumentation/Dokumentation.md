
# DocVer Dokumentation

**Modul:** Datenbankanwendungen

**Studierende:** Ken Madlehn, André Grellmann, Pia Schreiner



## Einleitung

DocVer ist ein System zum Verwalten von Dokumenten, das im Browser läuft und für Mobilgeräte optimiert ist. Durch die Analyse verwalteter Dokumente, bietet es eine Volltextsuche über alle Dokumente an. Optional, bietet DocVer außerdem eine Schnittstelle für Erweiterungen, welche tiefere Analysen der Dokumente ermöglicht. Durch eine strukturierte Darstellung hochgeladener Dokumente bekommt der Nutzer eine einfache und zeiteffiziente Möglichkeit, seine Dokumente zu durchsuchen und notwendige Dokumente schnell zu finden.
Zum Benutzen von DocVer wird ein kompatibles Gerät mit Webbrowser und Internetverbindung benötigt. In der derzeitigen Version wird der Google Chrome Browser benötigt. Das System soll dadurch sehr zugänglich und für eine breite Nutzergruppe geeignet sein. Jede Person, die ihre Dokumente verwalten möchte und einen PC mit Scanner, ein Smartphone, ein Tablet o.ä. besitzt, soll dies mit unserem Service machen können. Auch für (derzeit noch kleinere) Organisationen ist das System geeignet.

## Planung

### Idee

Das System soll digitalisierte Dokumente, wie z.B. Fotos oder Scans verwalten können. Dafür sollen diese hochgeladen werden und anschließend automatisch zum Nutzer zugeordnet gespeichert, mit optischer Zeichenerkennung (OCR) analysiert und in durchsuchbare PDFs umgewandelt werden. Außerdem sollen sie klassifiziert werden können. Für die Klassifizierung hat der Nutzer einige Standard Kategorien, welche bereits angelegt worden sind und nicht gelöscht werden können. Weiterhin kann jeder Nutzer sich eigene Kategorien anlegen, in welche er seine Dokumente anschließend klassifizieren kann. Die Klassifizierung soll zunächst manuell erfolgen, in dem der Nutzer entweder beim Upload eines Dokuments die Kategorie auswählt, oder das Dokument später in einer Kategorie klassifiziert. Nachdem die Dokumente in das System aufgenommen wurden, soll eine Volltextsuche über diese möglich sein und eine Übersicht über sie gegeben werden. Auch kann eine Suche nach Begriffen durchgeführt werden, welche Dokumente liefert, die diese Begriffe enthalten. Die Anwendung soll mittels eines Browsers mobil (via Smartphone oder Tablet) sowie lokal (am PC) benutzbar sein.

### Mockups

- Mockups überarbeiten und einfügen (Pia)

### Datenbankentwurf

#### ER Diagramm

![ER Diagramm](img/doc-ver_Diagramme-ER-Diagramm.svg)

- Stored Procedures, Functions und Trigger nicht in ER Diagramm sondern mit Tabellen darstellen

#### Stored Procedures
- Funktion hinzufügen (Andre)

#### Stored Functions
|  Stored Function  |          Input         |             Output             | Funktion |
|-------------------|------------------------|--------------------------------|-----------|
| GetDocsByKeywords | User.user_id, keywords | Document.doc_id, Document.name | Gibt eine Liste mit Dokumenten, die min. eines der Keywords enthalten, zurück. |
| GetDocsByUserAndExpression | User.user_id, expression | Document.doc_id, Document.name | Gibt eine Liste mit Dokumenten, die mit dem Regex übereinstimmen, zurück. |
| GetFullDocText | Document.doc_id | Document.name, doc_text | Setzt den gemerierten Text eines Dokuments zusammen und gibt ihn zurück. |
| StoreAnalyzedDoc | Document.doc:_id, Document.analyzed_start, Document.analyzed_end, Document.pdfpath, words | - | Speichert alle, beim analysieren generierte, Daten in der Datenbank. |

#### Trigger
|      Trigger      |      Zeitpunkt      |               Funktion               |
|-------------------|---------------------|--------------------------------------|
| DeleteUnusedWords | ON_DELETE(Document) | Löscht unbenutzte Wörter aus Wordbag |

### Systementwurf

#### Frontend

- Strukturdiagramm NodeJS Server (Pia)

#### Backend

- Strukturdiagramm Angular App (Pia)

#### Gesamtüberblick

![Verteilungsdiagramm](img/doc-ver_Diagramme-Verteilungsdiagramm.svg)



### Kommunikationsentwurf

- Allgemeiner Text zur Kommunikation

  - Kommunikation zwischen Frontend und Backend über REST Routen
  - Kommunikation zwischen Datenbank und Backend mittels ORM Framework und TCP
  - Kommunikation zwischen Backend und Nextcloud?




#### Darstellung des Ablaufs

![Verteilungsdiagramm](img/doc-ver_Diagramme-Sequenzdiagramm.svg)

#### Schnittstellenübersicht

(Andre)

|      Route        |      Parameter      |               Body                   | Funktion |
|-------------------|---------------------|--------------------------------------|----------|
||  |  | |



## Features

- alle Features unter Kategorie als ausführliche Stichpunkte formulieren

### Dokumentenverwaltung mit Klassifizierung

- Dokumente hochladen
- Kategorienverwaltung
- Dokumente in Kategorien ordnen
- Dashboard Ansicht
(Andre)

### OCR Analyse
(Ken)


### Offline Nutzung

- Cachen der Seite mittels PWA
- Cachen der Volltextvorschau von bereits geöffneten Dokumenten
(Pia)


## Genutzte Technologien

### Docker als Environment

- Deployment Übersicht
  - Welche Container?
  - Wie deployed?
(Ken)

### OCR Analyse 

- Genauere Erklärung zur Umsetzung
- Welche OCR Lib
(Ken)

### Nextcloud

- Datenablage der Original Files
- Datenablage der generierten PDFs
(Andre)

### Oracle Datenbank

- Genauere Erklärung zur Umsetzung mit Tablespaces, Nutzer, Stored Procedures etc.
(Ken)

### Node JS

- Libs und kurze Erklärung
(Pia)

### Angular

- Libs und kurze Erklärung
(Pia)

## Fazit

- Mit modernen ORM Frameworks sollte man Oracle nicht nutzen
- Das Erstellen von DB Funktionen mit Oracle ist mühsam (schlechte Debugging Möglichkeiten) 

## Ausblick

- Satzzeichen könnten als Wörter behandelt werden um die Suche zu verbessern
	- Derzeit Satzzeichen am Wort direkt und daher evtl. nicht als Suchergebnis
- Es wäre möglich, die Firebase mit einer eigenen Authentifizierungsmöglichkeit zu ersetzen

Als Erweiterung des Systems, wäre eine automatische Klassifizierung denkbar, die hochgeladene Dokumente automatisch in die passende Kategorie einsortieren kann. Außerdem wäre eine Schnittstelle mit erweiternder Funktionalität möglich, die tiefere Analysen der Dokumente durchführt und es ermöglicht, Zusatzmodule zu implementieren, welche die Daten analysieren. Ein Beispiel dafür wäre ein automatisches Fahrtenbuch, das aus Daten von Tankquittungen erstellt wird.
