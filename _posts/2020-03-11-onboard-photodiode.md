---
date: 2020-03-11
title: Photodiode
categories: onboard
description: Photodiode(PD) zum messen von Schwankungen in der Helligkeit
type: Document
resources:
image1: /images/2020-03-11-onboard-photodiode/blockPD.png
---

Eine Photodiode ist ein lichtempfindlicher Halbleiter, der Licht in elektrische Energie umwandelt. Sie wird häufig in verschiedenen Anwendungen wie Fotodetektoren, Belichtungsmessern, Lichtschranken und optischen Kommunikationssystemen eingesetzt. Photodioden liefern Messwerte, die proportional zur Intensität des einfallenden Lichts sind, wodurch sie zur Erfassung von Helligkeitsänderungen oder zur Quantifizierung von Lichtintensitäten in verschiedenen Anwendungen verwendet werden können.

## Programmierung (Arduino)

Um die Photodiode zu testen lade diesen Sketch auf deine senseBox hoch!

```c++
void setup() {
  // put your setup code here, to run once:
  pinMode(PD_ENABLE, OUTPUT);
  analogReadResolution(12);
  digitalWrite(PD_ENABLE, HIGH);

  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:

  Serial.println(analogRead(PD_SENSE));
  delay(100);
}
```

Im Seriellen Monitor werden dir nun die Werte für die Photodiode ausgegeben. Du kannst dir den Verlauf der Werte auch in einem Graph im Seriellen Plotter (Werkzeuge -> Serieller Plotter) anzeigen lassen.

## Programmierung (Blockly)

In Blockly kann der Sensor über folgenden Block ausgelesen werden:

{% include image.html image=page.image1 %}
