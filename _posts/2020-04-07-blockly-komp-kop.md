---
date: 2020-04-07
title: Kompilieren und Übertragen
title_order: 1 # Indicates the order of apperance on the overview pages
categories: Blockly
description: Erfahre, wie du dein Programm in Maschinensprache übersetzt und es auf deine senseBox MCU überträgst.
type: Document
set: blockly-erste-schritte
set_order: 4

resources:
  - name: "Blockly.senseBox.de"
    link: https://blockly.sensebox.de
image1: /images/2020-04-07-komp-kop/kompilieren.png
image2: /images/2020-04-07-komp-kop/Programm.png
image3: /images/2020-04-07-komp-kop/Lern.png
image4: /images/2020-04-07-komp-kop/copy_to_mcu.gif
image5: /images/2020-04-07-komp-kop/copy-to-mcu-mac.gif
---

Nachdem du deinen ersten Sketch programmiert hast, muss dieser nun kompiliert und auf die senseBox MCU übertragen werden.

## Kompilieren

Damit dein Programm von der senseBox ausgeführt werden kann, muss es zuerst in Maschinensprache übersetzt werden. Diesen Vorgang nennt man _Kompilieren_. Im Fall der senseBox übernimmt das Kompilieren unser Server.

Um deinen Sketch kompilieren zu lassen, klicke in Blockly oben rechts auf den orangenen Knopf mit dem Notizblocksymbol.

{% include image.html image=page.image1 %}

Wenn dein Sketch fertig kompiliert ist, wird er dir in Form einer .BIN-Datei zum Download angeboten. Speichere ihn an einem Ort, wo du ihn später wiederfindest.

## Übertragen

Schließe nun deine senseBox MCU-S2 mit Hilfe des USB-Kabels an deinen Computer an. Deine senseBox sollte nun als Wechseldatenträger von deinem Computer erkannt werden.

#### Kopieren

Nun kannst du die zuvor heruntergeladene .BIN-Datei einfach per Drag & Drop auf den Wechseldatenträger <b>SENSEBOX</b> kopieren. Die senseBox wird nun deinen hochgeladenen Sketch abspielen.

{% include image.html image=page.image4 %}

> Wenn deine senseBox nicht als Wechseldatenträger erkannt wird, probiere [die senseBox zu resetten](/misc/reset-mcus2/) die senseBox zu resetten und es nochmal zu versuchen
