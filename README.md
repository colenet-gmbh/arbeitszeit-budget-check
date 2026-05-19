# Arbeitszeit-Kalkulator

Ein schlankes, browserbasiertes Werkzeug zur Vertragsplanung für Freelancer und Dienstleister mit unterschiedlichen Tagessätzen für Remote- und Vor-Ort-Arbeit.

## Zweck

Als Dienstleister mit einem fixen Gesamtbudget und einer definierten Vertragslaufzeit ist es schwer den Überblick zu behalten: Wieviel Budget ist bereits verbraucht? Wieviel muss für geplante Vor-Ort-Einsätze reserviert werden? Und wieviele Stunden darf ich pro Tag im Schnitt noch arbeiten, um das Budget nicht zu überschreiten?

Dieses Tool beantwortet genau diese Frage – täglich, auf einen Blick.

## Funktionsweise

Der Kalkulator nimmt folgende Eingaben entgegen:

- **Vertragsbeginn** und **Vertragsende** – frei wählbar, daraus werden die Monate automatisch abgeleitet
- **Gesamtbudget** der Vertragslaufzeit in Euro
- **Tagessatz Remote** und **Tagessatz Vor Ort** sowie **Stunden pro Tag**
- **Verfügbare Stunden je Monat** (eigene Kapazität nach Abzug von Urlaub, Feiertagen, Schulungen etc.)
- **Bereits geleistete Stunden** pro Monat, aufgeteilt in Remote und Vor Ort
- **Geplante Vor-Ort-Einsätze** pro Monat (aktivierbar per Checkbox mit Stundenangabe)

Aus diesen Werten berechnet das Tool:

1. Verbrauchtes Budget, reserviertes Budget und verfügbares Restbudget
2. Den **Sollwert in Stunden pro Tag** für jeden verbleibenden Monat der Laufzeit – so dass das Budget bis Vertragsende exakt aufgebraucht, aber nicht überschritten wird
3. Die Verteilung erfolgt gewichtet nach verbleibender persönlicher Kapazität je Monat

## Features

- **Flexibler Vertragszeitraum**: Beliebige Start- und Enddaten – das Tool funktioniert für 2 Monate genauso wie für 12 Monate
- **Tages-Banner** oben auf der Seite: zeigt den heutigen Sollwert auf einen Blick; am Wochenende wird der nächste Arbeitstag angezeigt
- **Gestapelter Fortschrittsbalken**: verbraucht / reserviert / verfügbar in Abstufungen von Meergrün
- **Monatskarten** mit Remote-Budget, geplantem Vor-Ort-Anteil, Arbeitstagen und Gesamtbudget je Monat
- **Auto-Save**: alle Eingaben werden automatisch im Browser-LocalStorage gespeichert und beim nächsten Öffnen wiederhergestellt – bei geändertem Vertragszeitraum bleiben Stammdaten erhalten, Monatsdaten starten frisch

## Technische Details

- Einzelne HTML-Datei, kein Server, keine Installation, keine Abhängigkeiten
- Läuft vollständig im Browser (Chrome, Firefox, Safari, Edge)
- Datenpersistenz über `localStorage` des Browsers
- Schriften werden von Google Fonts geladen (DM Sans, DM Mono) – Internetverbindung beim ersten Öffnen empfohlen
- Tab-Icon (Favicon) eingebettet – sichtbar in Chrome, Firefox und Edge

## Nutzung

1. Datei `arbeitszeit_kalkulator.html` herunterladen
2. Im Browser öffnen (Doppelklick genügt)
3. Vertragsbeginn, Vertragsende und Budget eintragen
4. Tagessätze und verfügbare Stunden je Monat anpassen
5. Täglich oder wöchentlich geleistete Stunden aktualisieren
6. Der Sollwert im Banner zeigt jederzeit die aktuelle Empfehlung
