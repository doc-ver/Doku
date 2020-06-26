# DocVer Dokumantation

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

### Mockups



### Datenbankentwurf

#### ER Diagramm

![ER Diagramm](img/doc-ver_Diagramme-ER-Diagramm.svg)

- Stored Procedures, Functions und Trigger nicht in ER Diagramm sondern mit Tabellen darstellen

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

### Oracle Datenbank

- Genauere Erklärung zur Umsetzung mit Tablespaces, Nutzer, Stored Procedures etc.

### Node JS

- Libs und kurze Erklärung

### Angular

- Libs und kurze Erklärung

## Fazit



## Ausblick

