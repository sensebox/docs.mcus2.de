---
set: erste-schritte-arduino
resources:
  - name: Arduino
    link: https://www.arduino.cc
  - name: Arduino Old Releases
    link: https://www.arduino.cc/en/Main/OldSoftwareReleases#previous
title_order: 1
date: 2020-03-11
set_order: 1
image1: /images/2020-03-11-allgemein-arduino-ide-installieren/arduino-download.png
image2: /images/2020-03-11-allgemein-arduino-ide-installieren/arduino-donate.png
type: Document
title: Installation der Arduino IDE
description: Installation der Arduino IDE
categories: arduino
---

Bevor du die senseBox über die Arduino IDE programmieren kannst, musst du Treiber sowie eine Software auf deinem Computer installieren.

Schau dir die Anleitung für dein Betriebsystem an und folge den angegebenen Schritten.

## Arduino Software für Windows herunterladen

Die senseBox ist ein Microcontroller mit verschiedenen Komponenten und Sensoren. Sie wird über die Entwicklungsumgebung _Arduino IDE_ programmiert. Lade die neueste Version von der [Arduino Homepage](https://www.arduino.cc/en/software) herunter:

{% include image.html image=page.image1 %}

Arduino ist ein Open-Source Projekt und wird durch Spenden finanziert. Daher wirst du vor dem Download nach einer Spende gefragt; falls du nichts spenden möchtest, kannst du auf `JUST DOWNLOAD` klicken.

{% include image.html image=page.image2 %}

Lege auf deiner Festplatte einen neuen Ordner an und entpacke darin die zip-Datei. Durch das Ausführen der Datei `arduino.exe` kann die IDE gestartet werden.

## Arduino Software für Mac(OSX) herunterladen

Die senseBox ist ein Microcontroller mit verschiedenen Komponenten und Sensoren. Sie wird über die Entwicklungsumgebung _Arduino IDE_ programmiert. Lade die neueste Version von der [Arduino Homepage](https://www.arduino.cc/en/software) herunter:

{% include image.html image=page.image1 %}

Arduino ist ein Open-Source Projekt und wird durch Spenden finanziert. Daher wirst du vor dem Download nach einer Spende gefragt; das kannst du überspringen, indem du auf `JUST DOWNLOAD` klickst.

{% include image.html image=page.image2 %}

In deinem Downloads-Ordner sollte eine Arduino.app-Datei erscheinen. Verschiebe diese Datei in deinen "Programme"-Ordner. Durch Öffnen der Datei `Arduino.app` kann die IDE gestartet werden.

## Arduino Software für Linux herunterladen

Die senseBox ist ein Microcontroller mit verschiedenen Komponenten und Sensoren. Sie wird über die Entwicklungsumgebung _Arduino IDE_ programmiert. Lade die neueste Version von der [Arduino Homepage](https://www.arduino.cc/en/software) herunter:

{% include image.html image=page.image1 %}

Arduino ist ein Open-Source Projekt und wird durch Spenden finanziert. Daher wirst du vor dem Download nach einer Spende gefragt; das kannst du überspringen, indem du auf `JUST DOWNLOAD` klickst.

{% include image.html image=page.image2 %}

### Installation der IDE unter Linux {#installation-der-ide-unter-linux}

Linux-Nutzer können das von Arduino bereitgestellte `AppImage` benutzen um Arduino zu installieren. Dafür muss das AppImage nach dem herunterladen noch Berechtigungen zum ausführen bekommen,

```text
# Change to the directory containing the AppImage e.g.
cd Downloads
# Make the AppImage executable (change the version number if need be):
chmod +x arduino-ide_2.2.1_Linux_64bit.AppImage
# Run the AppImage
./arduino-ide_2.2.1_Linux_64bit.AppImage
```

Alternativ kann das AppImage auch über das Graphic User Interface ausführbar gemacht werden. Wie das geht wird dir [hier](https://docs.appimage.org/introduction/quickstart.html) beschrieben.
