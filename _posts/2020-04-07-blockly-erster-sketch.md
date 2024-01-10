---
date: 2020-04-07
title: Dein erster Sketch
title_order: 1 # Indicates the order of apperance on the overview pages
categories: Blockly
description: Schreibe dein erstes Programm für die senseBox
type: Document
set: blockly-erste-schritte
set_order: 3

resources:
  - name: "Blockly.senseBox.de"
    link: https://blockly.sensebox.de
image1: /images/2020-04-07-blockly-erster-sketch/Auswahl.png
image2: /images/2020-04-07-blockly-erster-sketch/Oberflaeche.png
image3: /images/2020-04-07-blockly-erster-sketch//blockly-es-1.svg
image4: /images/2020-04-07-blockly-erster-sketch//blockly-es-2.png
image5: /images/2020-04-07-blockly-erster-sketch//blockly-es-3.png
image6: /images/2020-04-08-blockly-erste-schritte/modi.png
---

Blockly ist die vom senseBox-Team entwickelte grafische Programmierumgebung für die senseBox. Sie ist online kostenlos und ohne Softwareinstallation verfügbar und basiert auf dem [Blockly Framework](https://developers.google.com/blockly) von Google.

## Erste Schritte

Öffne Blockly für senseBox in deinem Browser unter [https://blockly.sensebox.de](https://deploy-preview-246--blockly-react.netlify.app/). Dort musst du zuerst deine senseBox-Version auswählen. Wähle hier `senseBox MCU-S2` aus.

{% include image.html image=page.image1 %}

## Oberfläche

Nachdem du deine senseBox-Version ausgewählt hast, befindest du dich auf der Programmieroberfläche. Diese lässt sich in fünf wichtige Bereiche einteilen.

{% include image.html image=page.image2 %}

1. **Die Menüleiste:**
   In der Menüleiste kannst du das verwendete Board oder die Sprache ändern. Auf der linken Seite hast du darüber hinaus die Möglichkeit zu den Tutorials und zu der Gallerie zu navigieren. Die Tutorials sind eine Anleitung für deine ersten Blockly Sketches und führen dich an die verschiedenen Sensoren und Funktionen der senseBox heran. In der Gallerie findest du ausgewählte Sketche vom senseBox-Team.
2. **Die Toolbar:**
   Hier findest du alle Blöcke zum Programmieren der senseBox. Die Farbe der Blöcke zeigt die jeweilige Kategorie an, zu welcher der Block gehört.
3. **Der Arbeitsbereich:**
   In diesem Bereich fügst du deine Programme zusammen. Unten rechts befinden sich Schaltfläche zum Zentrieren, Vergrößern, Verkleinern und Löschen der Blöcke.
4. **Kopieren, kompilieren und andere Funktionen von Blockly:**
   Hier findest du den wohl wichtigsten Knopf für Blockly. Mit dem orangenen 'Kompilieren' Knopf kannst du deinen erstellten Sketch kompilieren & herunterladen. Darüber hinaus kannst du hier deinen Sketch umbenenen, herunterladen, teilen, Screenshots erstellen oder den Arduino QUellcode deines Sketches in in die Zwischenablage speichern.
5. **Arduino Quellcode und XML Blöcke:**
   Hier wird dir parellel zur grafischen Programmierung der Arduino Quellcode angezeigt. Durch einen Klick auf die Schaltfläche XML Blöcke lässt sich die Ansicht auf den XML Code umschalten.

## Programmieren

Um dein Programm zu schreiben, müssen die Blöcke aus der Toolbar per Drag & Drop im Arbeitsbereich platziert werden.

### Schritt 1: Setup und Endlosschleife

Dieser Block wird direkt beim Starten der Oberfläche geladen und sollte immer verwendet werden. Die zwei Basisfunktionen `Setup()` und `Endlosschleife()` werden immer benötigt, um ein funtkionsfähiges Programm zu schreiben.
Alle Blöcke, die innerhalb der `Setup()`-Funktion stehen, werden nur zu Beginn des Programmes einmal ausgeführt. In dieser Funktion wird zum Beispiel das Display initialsiert oder die WLAN Verbindung hergestellt. Alle Blöcke, die innerhalb der `Endlosschleife()` stehen, werden fortlaufend ausgeführt. Der Mikrocontroller führt hierbei alle Blöcke immer wieder von oben nach unten hin aus. In der `Endlosschleife()` werden zum Beispiel die Sensoren ausgelesen oder auch die Messwerte auf SD-Karte gespeichert oder ins Internet übertragen.

{% include image.html image=page.image3 %}

### Schritt 2: Die eingebaute LED einschalten

Als erstes muss die eingebauten LED initialisiert werden. Dafür ziehe den `RGB LED(WS2818) initialisieren` in die Setup Funktion. Die Werte für Anzahl & Helligkeit kannst du hier unverändert lassen.

{% include image.html image=page.image4 %}

> Die eingebaute LED findest du über dem roten Reset-Knopf auf der senseBox MCU.

### Schritt 3: Die eingebaute LED blinken lassen

Nun wollen wir die LED jede Sekunde in einer anderen Farbe blinken lassen. Hierfür nehmen wir aus der Kategorie `Zeit` den `Intervall` Block und ziehen ihn in die `Endlosschleife()`. Dort können wir den noch den Wert für das Interval von `10000ms` auf `1000ms` ändern, damit der Block alle 1000 Millisekunden (1 Sekunde) ausgeführt wird.
In der Kategorie `LED` nehmen wir jetzt den Block `Setze RGB-LED an Port:` und platzieren ihn innerhalb des Intervalls. Stelle hier sicher, dass der ausgewählte `Port` der gleiche ist wie im initialisieren Block im `Setup()`. Letztlich müssen wir noch eine Farbe angeben in welcher die RGB-LED leuchten soll. Da jede Sekunde eine neue zufällige Farbe erscheinen soll, nehmen wir uns in der Kategorie `LED` den Block `zufällige Farbe` und ziehen ihn zum Feld `Farbe`.
Der vollständige Sketch sieht wiefolgt aus.

{% include image.html image=page.image5 %}

## Herunterladen und Übertragen

Nachdem dein Programm fertig ist, klickst du den orangenen "Sketch kompilieren" Button und es wird dir eine .BIN-Datei zum Download angeboten. Diese musst du an einem beliebigen Ort speichern.

### Übertragen

Schließt du deine senseBox MCU-S2 an deinen Computer an und führst einen Doppelklick auf dem roten Button aus, wird diese als Wechseldatendräger erkannt. Mit einem Klick auf “Code Kompilieren” in der Weboberfläche wird dein Programmcode auf dem Server kompiliert und eine .BIN-Datei wird dir zum Download angeboten.

Nun kannst du die heruntergaldene .BIN-Datei einfach per Drag & Drop auf den neu erscheinenden Wechseldatenträger ('SENSEBOX') kopieren. Die senseBox startet neu und spielt nun deinen Sketch ab.
