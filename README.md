# Readme

github pages auf https://sgse-2020.github.io/Ausarbeitungen/#/ verfügbar

### Docsify lokal ausführen

Für die lokale Ausführung von __docsify__ wird [node](https://nodejs.org/en/download/) benötigt.

Die installation von __docsify__ findet mit npm auf der Konsole statt. Dazu ist der folgende Befehl auszuführen:

```bash
npm i docsify-cli -g
```

Im Anschluss kann in dem Projektordner __Ausarbeitungen__ das folgende Skript ausgeführt werden, um den __docsify__-Entwicklungsserver zu starten:
```bash
docsify serve docs
```

Auf den Entwicklungsserver kann mit einem Webbrowser unter der Adresse `http://localhost:3000` zugegriffen werden. 
Änderungen werden bei Click im Browser oder in der Kommandozeile Hot-Deployed. Der Entwicklungsserver kann mir `ctrl+c` 
oder durch Schließen des Konsolenfensters gestoppt werden.

### Einpflegen neuer Dateien in github pages

Ausarbeitungen müssen als markdown Datei in den docs Ordner

Damit die Ausarbeitung in der Seitennavigation auftaucht muss ein Eintrag in die sidebar.md im nachfolgenden Format gemacht werden:
 \* \[Titel der Ausarbeitung\](dateiname) 

