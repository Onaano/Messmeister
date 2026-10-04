# 📏 Messmeister — Längen, Gewichte & Fassungsvermögen

Interaktives Lernspiel zu Größen, Messen und Einheiten, angesiedelt in einer
freundlichen Messwerkstatt. **Zielgruppe:** Grundschule (Klasse 2–4) und Förderunterricht.

Die drei Lernbereiche: 📏 Längen (mm, cm, m, km) · ⚖️ Gewichte (g, kg) · 💧 Fassungsvermögen (ml, l)

## 🎮 Die neun Modi

1. **Miss nach!** — Lineal ablesen (leicht: ab 0 · mittel: Anfang/Ende ablesen · schwer: halbe cm und mm)
2. **Richtig messen** — Wie wurde richtig gemessen? / Anfang und Ende → Länge
3. **Schätze mal!** — Größen einschätzen; auch umgekehrt: „Was wiegt ungefähr 1 kg?“
4. **Welche Einheit passt?** — Einheit zum Gegenstand wählen oder in einen Satz einsetzen
5. **Schwerer oder leichter?** — Gegenstände, Angaben, Vergleichszeichen, gleich schwer in anderer Einheit
6. **Wie viel ist drin?** — Messbecher/Messkrug ablesen, „Wie viel fehlt bis 1 l?“, Gefäße und Mengen vergleichen
7. **Verwandle die Einheit!** — Umrechnen (auch „1 m 50 cm“), „Was ist am längsten?“, „Stimmt das?“
8. **Was könnte stimmen?** — Satz ergänzen, „Welcher Satz stimmt?“, „Stimmt das?“
9. **Messmeister-Challenge** — alles gemischt, Stufe leicht/mittel/schwer

Bereiche (Längen/Gewichte/Fassungsvermögen/Gemischt) und Stufen sind – wo sinnvoll – wählbar.
Eine Runde = 8 **richtig gelöste** Aufgaben. Kein Punktabzug, keine Zeit, kein Game Over.

## 🧮 Mathematische Grundsätze

- Alle Größen werden intern in **Basiseinheiten** gespeichert und gerechnet: Millimeter, Gramm, Milliliter.
  Zentrale Funktionen: `convertLength/Weight/Volume`, `formatLength/Weight/Volume`, `formatCompound`, `compareMeasurements`.
- **Digitale Messaufgaben messen nie in Bildschirm-Zentimetern.** Gegenstand und Lineal liegen im selben SVG
  (`viewBox` fest, 1 virtueller cm = feste Zahl SVG-Einheiten). Skaliert das SVG, skaliert beides gleich mit.
- Messbecher: Skala **und** Wasserstand entstehen aus derselben Funktion `yOf(ml)`, der Wasserstand liegt exakt auf der Skala.
- Alltagsgrößen haben einen hinterlegten plausiblen Bereich; falsche Antworten liegen immer mindestens um den
  Faktor 4 daneben → keine mehrdeutigen Schätzaufgaben.
- Keine Dezimalschreibweise als Schwerpunkt: „1 kg 500 g“ statt „1,5 kg“.

## 🔀 Abwechslung

Zu Beginn jeder Runde wird ein **Rundenplan** erstellt: Die Aufgabenarten werden gleichmäßig verteilt und so
gemischt, dass dieselbe Art nicht zu oft hintereinander kommt (bei 3 Arten höchstens 3×, bei 4 Arten höchstens 2× pro Runde).
Der Wiederholungsschutz gilt **auf Gegenstandsebene über alle Aufgabenformate und Bereiche hinweg**: Derselbe Gegenstand
(Mehlpackung, Radiergummi, Handy …) kommt in einer Runde nie zweimal als Aufgabe vor – auch nicht, wenn er in zwei Bereichen
existiert (z. B. Radiergummi als Länge und als Gewicht). Bereits gezeigte Gegenstände werden bevorzugt nicht noch einmal als
Aufgabenziel oder als falsche Antwort gewählt. Gemessen über 300 Runden je Modus sieht man in „Was könnte stimmen?“ in 0 % der Runden
einen Gegenstand doppelt, in „Schätze mal!“ höchstens in 3 %.

Dafür gibt es einen großen Vorrat: **47 Alltagsgrößen** (Längen, Gewichte, Fassungsvermögen), 41 Einheiten-Aufgaben,
15 Gegenstände zum Gewichtsvergleich und **10 Messgegenstände** fürs Lineal (Bleistift, Radiergummi, Pinsel, Schere, Stift, Buch,
Löffel, Schlüssel, Zahnbürste, Möhre) mit wechselnden Farben. Dazu mehrere Fragetexte („Was ist mehr?“ / „Welche Menge ist größer?“).

## 🛠️ Technik

Eine einzige `index.html` — HTML, CSS, Vanilla JavaScript, keine Abhängigkeiten, keine externen Bilder/Fonts/APIs,
keine Cookies, kein Tracking, keine Datenspeicherung. Optionale Sprachausgabe (SpeechSynthesis, `de-DE`):
Einheiten werden ausgesprochen („cm“ → „Zentimeter“). Zahl und Einheit werden nie durch einen Zeilenumbruch getrennt.
Responsiv für Smartphone, Tablet, Desktop und Smartboard; Touch und Maus.

## 🌐 Veröffentlichung

GitHub: `index.html`, `README.md`, `.gitignore` hochladen · Netlify: Ordner per Drag & Drop (Build command leer, Publish directory `.`).

## ✅ Qualitätssicherung

- Alle Prüflisten der Vorgabe (Lineal 0→7, 2→8, 3→11, 5→14, 0→7,5, 2→8,5; Umrechnungen; Vergleiche) bestanden.
- Lineal: Position jedes Strichs, Beschriftung, Gegenstandsenden und abgelesene Länge aus dem erzeugten SVG nachgerechnet.
- Messbecher: Skalenstriche, Wasserstand und Antwort aus dem erzeugten SVG nachgerechnet.
- Alle Generatoren in tausenden Stichproben geprüft: je 4 verschiedene Optionen, richtige Antwort enthalten,
  keine falschen Umrechnungen, keine mehrdeutigen Schätzaufgaben, keine Dezimalschreibweise.
- 30 Modus/Bereich/Stufen-Kombinationen als volle Runden über die Oberfläche durchgespielt, inkl. falscher Antwort,
  Neue Runde, Stufe ändern, Zurück, Moduswechsel ohne übernommenen Zustand.
- 6 Bildschirmgrößen (375×667 bis 1920×1080): keine horizontale Scrollbar, nichts abgeschnitten, Touchflächen groß genug.

## 🖨️ Arbeitsmaterialien

Im Ordner `arbeitsblaetter/` (jeweils HTML und PDF):

- `teilnehmeruebersicht` — A4 quer, 30 Kinder × 10 Runden zum Abhaken
- `arbeitsblatt-laengen` — Lineal ablesen (ganze/halbe cm, mm), richtig messen, Einheit wählen, umrechnen, Länge schätzen
- `arbeitsblatt-gewichte-inhalt` — Gewichte vergleichen (<, =, >), Messbecher ablesen, „Wie viel fehlt bis 1 l?“, Einheit wählen, umrechnen, Alltagsgrößen

Lineale, Messbecher und Gegenstände auf den Blättern entstehen mit demselben Code wie im Spiel (feste Skala im SVG,
Wasserstand und Skala aus derselben Funktion). Die Blätter wurden direkt aus dem fertigen HTML nachgerechnet.

## 📄 Lizenz

© Förderfreude Games. Alle Rechte vorbehalten.
