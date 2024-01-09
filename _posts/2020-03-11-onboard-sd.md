---
date: 2020-03-11
title: SD-Modul
categories: onboard
description: Mit dem SD-Modul kannst du Daten auf einer SD-Karte speichern, um sie später wiederzuverwenden
type: Document
image1: /images/2020-03-11-onboard-sd/sdmodule.png
---

Auf der Rückseite deiner MCU-S2 ist ein SD-Karten Modul für MicroSD Karten verbaut. Auf der Micro SD Karte lassen sich Daten speichern um sie später an einem anderen Endgerät, wie zum Beispiel einem Laptop, wiederzuverwenden.

{% include image.html image=page.image1 %}

# Programmierung (Blockly)

Informationen zur Programmierung des SD-Bees mit Blockly findest du [hier](/blockly/blockly-SD/)

# Programmierung (Arduino)

Im folgenden Beispiel zeigen wir dir, wie du eine Datei auf der SD Karte erstellst. Mit der Funktion `appendFile` kannst du der Datei weitere Zeilen hinzufügen. Den vollständigen Arduino Sketch mit allen Funktionen der `SD & FS Library` findest du [hier](https://github.com/sensebox/senseBox-MCU-S2-ESP32S2/blob/main/examples/sd-card/sd-card.ino).

```c++
#include "FS.h"
#include "SD.h"
#include "SPI.h"

void setup() {
  Serial.begin(115200);
  pinMode(SD_ENABLE,OUTPUT);
  digitalWrite(SD_ENABLE,LOW);
  delay(2000);

  SPIClass sdspi = SPIClass();
  sdspi.begin(VSPI_SCLK,VSPI_MISO,VSPI_MOSI,VSPI_SS);

  if (SD.begin(VSPI_SS,sdspi)) {
    Serial.println("SD-Karte erkannt.");
    writeFile(SD, "/hello.txt", "Hello World");
  } else {
    Serial.println("SD-Karte nicht erkannt. Überprüfe die Verbindung.");
  }
}

void loop() {
  // Hier kannst du weitere Anweisungen für dein Programm hinzufügen
}

void writeFile(fs::FS &fs, const char * path, const char * message){
    Serial.printf("Writing file: %s\n", path);

    File file = fs.open(path, FILE_WRITE);
    if(!file){
        Serial.println("Failed to open file for writing");
        return;
    }
    if(file.print(message)){
        Serial.println("File written");
    } else {
        Serial.println("Write failed");
    }
    file.close();
}

void appendFile(fs::FS &fs, const char * path, const char * message){
    Serial.printf("Appending to file: %s\n", path);

    File file = fs.open(path, FILE_APPEND);
    if(!file){
        Serial.println("Failed to open file for appending");
        return;
    }
    if(file.print(message)){
        Serial.println("Message appended");
    } else {
        Serial.println("Append failed");
    }
    file.close();
}


```
