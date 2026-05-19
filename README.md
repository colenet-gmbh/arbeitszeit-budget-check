# Arbeitszeit-Kalkulator

Ein schlankes, browserbaisertes Werkzeug zur Quartalsplanung für Freelancer und Dienstleister mit unterschiedlichen Tagessätzen für Remote- und Vor-Ort-Arbeit.

## Zweck

Als Dienstleister mit einem fixen Gesamtbudget pro Quartal ist es schwer den Überblick zu behalten: Wieviel Budget ist bereits verbraucht? Wieviel muss für geplante Vor-Ort-Einsätze reserviert werden? Und wieviele Stunden darf ich pro Tag im Schnitt noch arbeiten, um das Budget nicht zu überschreiten?

Dieses Tool beantwortet genau diese Frage – täglich, auf einen Blick.

## Funktionsweise

Der Kalkulator nimmt folgende Eingaben entgegen:

- **Gesamtbudget** des Quartals in Euro
- **Tagessatz Remote** und **Tagessatz Vor Ort** sowie **Stunden pro Tag**
- **Verfügbare Stunden je Monat** (eigene Kapazität nach Abzug von Urlaub, Feiertagen, Schulungen etc.)
- **Bereits geleistete Stunden** pro Monat, aufgeteilt in Remote und Vor Ort
- **Geplante Vor-Ort-Einsätze** pro Monat (aktivierbar per Checkbox mit Stundenangabe)

Aus diesen Werten berechnet das Tool:

1. Verbrauchtes Budget, reserviertes Budget und verfügbares Restbudget
2. Den **Sollwert in Stunden pro Tag** für jeden verbleibenden Monat des Quartals – so dass das Budget bis Quartalsende exakt aufgebraucht, aber nicht überschritten wird
3. Die Verteilung erfolgt gewichtet nach verbleibender persönlicher Kapazität je Monat

## Features

- **Tages-Banner** oben auf der Seite: zeigt den heutigen Sollwert auf einen Blick; am Wochenende wird der nächste Arbeitstag angezeigt
- **Gestapelter Fortschrittsbalken**: verbraucht / reserviert / verfügbar in Abstufungen von Meergrün
- **Monatskarten** mit Remote-Budget, geplantem Vor-Ort-Anteil, Arbeitstagen und Gesamtbudget je Monat
- **Automatisches Reset** beim Quartalswechsel: geleistete Stunden und Reservierungen werden zurückgesetzt, Stammdaten bleiben erhalten
- **Auto-Save**: alle Eingaben werden automatisch im Browser-LocalStorage gespeichert und beim nächsten Öffnen wiederhergestellt

## Technische Details

- Einzelne HTML-Datei, kein Server, keine Installation, keine Abhängigkeiten
- Läuft vollständig im Browser (Chrome, Firefox, Safari, Edge)
- Datenpersistenz über `localStorage` des Browsers – Daten sind an Browser und Dateipfad gebunden
- Schriften werden von Google Fonts geladen (DM Sans, DM Mono) – Internetverbindung beim ersten Öffnen empfohlen

## Nutzung

1. Datei `arbeitszeit_kalkulator.html` herunterladen
2. Im Browser öffnen (Doppelklick genügt)
3. Stammdaten einmalig eintragen (Budget, Tagessätze, verfügbare Stunden)
4. Täglich oder wöchentlich geleistete Stunden aktualisieren
5. Der Sollwert im Banner zeigt jederzeit die aktuelle Empfehlung

## Weiterentwicklung

Das Projekt besteht aus einer einzigen Datei und eignet sich gut für Git-Versionskontrolle:

```bash
git init
git add arbeitszeit_kalkulator.html README.md
git commit -m "Initiales Commit"
```
