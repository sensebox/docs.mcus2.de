---
date: 2020-03-11
title: Installation des Board-Support-Packages
title_order: 2
categories: arduino
description: Installation des Board-Support-Packages für die senseBox MCU-S2
type: Document
set: erste-schritte-arduino
set_order: 2
image1: /images/2020-03-11-board-support-package-installieren/arduino-boards.png
---

<div class="description">Damit die Arduino IDE deine senseBox MCU unterstützt und du Programme auf diese übertragen kannst, musst du vor Beginn noch zwei Board-Support-Packages installieren. Diese beinhalten die nötigen Treiber und die notwendige Software, um mit dem Prozessor der senseBox zu kommunizieren. Das Board-Support-Package der senseBox enthält außerdem bereits unsere senseBox-Libraries. Damit stehen euch alle grundlegenden Methoden zur Programmierung der beiliegenden Sensoren zur Verfügung.</div>

## Board-Support Package hinzufügen

Füge die folgende URL in deiner Arduino IDE unter _`Arduino -> Einstellungen...`_ in das Feld für _Zusätzliche Bordverwalter-URLs_ ein:

```
https://mariopesch.github.io/sensebox-esp32-dev/package_esp32_index.json

```

Öffne den _Boardverwalter_ mit einem Klick auf das _Boardverwalter_ Symbol auf der linken Seite (siehe Bild)
{% include image.html image=page.image1 %}
Gib "ESP32" oben in die Suchleiste ein, um die Packages schneller zu finden und installiere das Board `esp32` von _Espressif Systems_. <b>Achtung! Stelle sicher , dass du mindestens die Version 2.0.15-alpha3 installierst! </b>.
