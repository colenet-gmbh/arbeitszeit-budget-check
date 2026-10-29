# Arbeitszeit-Kalkulator

Ein schlankes, browserbasiertes Werkzeug zur Vertragsplanung für Freelancer und Dienstleister mit unterschiedlichen Tagessätzen für Remote- und Vor-Ort-Arbeit.

## Zweck

Als Dienstleister mit einem fixen Gesamtbudget und einer definierten Vertragslaufzeit ist es schwer den Überblick zu behalten: Wie viel Budget ist bereits verbraucht? Wie viel muss für geplante Vor-Ort-Einsätze reserviert werden? Und wie viele Stunden muss ich pro Tag noch arbeiten, damit das Budget bis zum Vertragsende aufgebraucht, aber nicht überschritten wird?

Dieses Tool beantwortet genau diese Frage – täglich, auf einen Blick.

## Funktionsweise

Der Kalkulator nimmt folgende Eingaben entgegen:

- **Vertragsbeginn** und **Vertragsende** – frei wählbar, daraus werden die Monate automatisch abgeleitet
- **Gesamtbudget** der Vertragslaufzeit in Euro
- **Tagessatz Remote** und **Tagessatz Vor Ort** sowie **Stunden je Tagessatz** (nur zur Umrechnung in Stundensätze)
- **Buchungsumfang** in % (z. B. 50 % = 4 h pro Tag) als Vergleichswert
- **Verfügbare Tage je Monat** (Arbeitstage nach Abzug von Urlaub, Feiertagen, Schulungen etc.)
- **Bereits geleistete Stunden** pro Monat, aufgeteilt in Remote und Vor Ort
- **Geplante Vor-Ort-Tage** pro Monat (aktivierbar per Checkbox, ganze Tage zum Vor-Ort-Tagessatz)

Aus diesen Werten berechnet das Tool:

1. Verbrauchtes Budget, reserviertes Budget und verfügbares Restbudget
2. Den **Sollwert in Stunden pro Remote-Tag** – so dass das Budget bis Vertragsende exakt aufgebraucht, aber nicht überschritten wird
3. Das Restbudget wird gleichmäßig auf alle verbleibenden Remote-Tage verteilt: Jeder Monat hat denselben Sollwert, höchstens ein voller Tagessatz. Vor-Ort-Tage sind teurer und senken den Sollwert der übrigen Tage.

## Features

- **Flexibler Vertragszeitraum**: Beliebige Start- und Enddaten – das Tool funktioniert für 2 Monate genauso wie für 12 Monate
- **Tages-Banner** oben auf der Seite: zeigt den heutigen Sollwert auf einen Blick; am Wochenende wird der nächste Arbeitstag angezeigt
- **Gestapelter Fortschrittsbalken**: verbraucht / reserviert / verfügbar in Abstufungen von Meergrün
- **Monatskarten in Klartext**: Stunden pro Remote-Tag, Anzahl Remote-Tage, Vor-Ort-Tage und Budget je Monat, dazu ein Auslastungsbalken mit Markierung des Buchungsumfangs; abgeschlossene Monate zeigen tatsächlich geleistete Stunden (Remote / Vor Ort) sowie die entstandenen Kosten
- **Laufender Monat**: Soll bis heute (laut Plan zum Monatsbeginn) im Vergleich zu den geleisteten Stunden
- **Warnungen** mit Icon, Titel und Begründung: Budget überschritten, mehr geleistet als vorgesehen, Budget nicht ausschöpfbar
- **Vertragsverlängerung**: neues Vertragsende und Budget, Restbudget übernehmen oder sauber neu starten
- **Auto-Save**: alle Eingaben werden automatisch im Browser-LocalStorage gespeichert und beim nächsten Öffnen wiederhergestellt – bei geändertem Vertragszeitraum bleiben Stammdaten erhalten, Monatsdaten starten frisch
- **Colenet-Logo** im Header – klickbar, verlinkt auf colenet.de

## Demo

`arbeitszeit_kalkulator_demo.html` zeigt das Tool mit fiktiven Beispieldaten (Q1 2026, simuliertes Datum 10. Februar 2026) und speichert nichts.

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
4. Tagessätze, Buchungsumfang und verfügbare Tage je Monat eintragen
5. Täglich oder wöchentlich geleistete Stunden aktualisieren
6. Der Sollwert im Banner zeigt jederzeit die aktuelle Empfehlung
