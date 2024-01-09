---
date: 2020-03-11
title: Onboard LED's
categories: onboard
description: Informationen wie die LED's, die auf dem Board verbaut sind angesteuert werden können
type: Document
resources:
image1: /images/2020-03-11-onboard-leds/onboardLEDBlock.png
aufbau: /images/2020-03-11-sensoren-distanz/Aufbau-Ultraschall.png
block: /images/2020-03-11-sensoren-distanz/ultraschall-block.svg
---

Die RGB-LED auf der senseBox MCU-S2 bietet dir die Möglichkeit nahezu alle Farben darzustellen. Diese kannst du für Statusmeldungen deines Programmes oder ähnliches nutzen.  
{% include image.html image=page.image1 %}

## Programmierung (Arduino)

Dieser Sketch gibt lässt die RGB-LED jede Sekunde in einer zufällige Farbe leuchten.

```c++
#include <Adafruit_NeoPixel.h>
Adafruit_NeoPixel rgb_led_1

void setup() {
    rgb_led_1.begin();
    rgb_led_1.setBrightness(30);
}

void loop() {
  if (time_startInterval > time_actualInterval + intervalInterval)
    {
        time_actualInterval = millis();
        rgb_led_1.setPixelColor(0,rgb_led_1.Color(random(0, 255), random(0, 255), random(0, 255)));
        rgb_led_1.show();
    }
}
```

## Programmierung (Blockly)

In Blockly kann der Sensor über folgenden Block ausgelesen werden:

{% include image.html image=page.image1 %}

Wähle den Port `onBoard` aus. Die Werte für Helligkeit und Anzahl kannst du unverändert lassen.
