# DocVer Dokumentation

**Modul:** Datenbankanwendungen

**Studierende:** Ken Madlehn, André Grellmann, Pia Schreiner



## Einleitung

- Einleitungstext
- Zielgruppe

## Planung

### Idee

- System zum Verwalten von Dokumenten
- browserbasiert für Mobilgeräte optimiert
- Volltextsuche von Dokumenten
- Strukturierung von Dokumenten

Das System soll digitalisierte Dokumente, wie z.B. Fotos oder Scans verwalten können. Dafür sollen diese hochgeladen werden und anschließend automatisch zum Nutzer zugeordnet gespeichert, mit optischer Zeichenerkennung (OCR) analysiert und in durchsuchbare PDFs umgewandelt werden. Außerdem sollen sie klassifiziert werden können. Für die Klassifizierung hat der Nutzer einige Standard Kategorien, welche bereits angelegt worden sind und nicht gelöscht werden können. Weiterhin kann jeder Nutzer sich eigene Kategorien anlegen, in die er seine Dokumente anschließend klassifizieren kann. Die Klassifizierung soll zunächst manuell erfolgen, in dem der Nutzer entweder beim Upload eines Dokuments die Kategorie auswählt, oder das Dokument später in einer Kategorie klassifiziert. Nachdem die Dokumente in das System aufgenommen wurden, soll eine Volltextsuche über diese möglich sein und eine Übersicht über sie gegeben werden. Auch kann eine Suche nach Begriffen durchgeführt werden, welche Dokumente liefert, die diese Begriffe enthalten. Die Anwendung soll mittels eines Browsers mobil (via Smartphone oder Tablet) sowie lokal (am PC) benutzbar sein.

### Mockups



### Datenbankentwurf

#### ER Diagramm

![ER Diagramm](img/doc-ver_Diagramme-ER-Diagramm.svg)

- Stored Procedures, Functions und Trigger nicht in ER Diagramm sondern mit Tabellen darstellen

#### Stored Procedures
| Stored Procedure | Input |
|------------------|-------|
| StoreAnalyzedDoc | Document.doc:_id, Document.analyzed_start, Document.analyzed_end, Document.pdfpath, words |

#### Stored Functions
|  Stored Function  |          Input         |             Output             |
|-------------------|------------------------|--------------------------------|
| GetDocsByKeywords | User.user_id, keywords | Document.doc_id, Document.name |
| GetDocsByUserAndExpression | User.user_id, expression | Document.doc_id, Document.name |
| GetFullDocText | Document.doc_id | Document.name, doc_text |

#### Trigger
|      Trigger      |      Zeitpunkt      |               Funktion               |
|-------------------|---------------------|--------------------------------------|
| DeleteUnusedWords | ON_DELETE(Document) | Löscht unbenutzte Wörter aus Wordbag |

### Systementwurf

#### Frontend

- Strukturdiagramm NodeJS Server

#### Backend

- Strukturdiagramm Angular App

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



## Features

### Dokumentenverwaltung mit Klassifizierung

- Dokumente hochladen
- Kategorienverwaltung
- Dokumente in Kategorien ordnen
- Dashboard Ansicht

### OCR Analyse



### Offline Nutzung

- Cachen der Seite mittels PWA
- Cachen der Volltextvorschau von bereits geöffneten Dokumenten



## Genutzte Technologien

### Docker als Environment

- Deployment Übersicht
  - Welche Container?
  - Wie deployed?

### OCR Analyse 

- Genauere Erklärung zur Umsetzung
- Welche OCR Lib

### Nextcloud

- Datenablage der Original Files
- Datenablage der generierten PDFs

### Oracle Datenbank

- Genauere Erklärung zur Umsetzung mit Tablespaces, Nutzer, Stored Procedures etc.

### Node JS

- Libs und kurze Erklärung

### Angular

- Libs und kurze Erklärung

## Fazit



## Ausblick
