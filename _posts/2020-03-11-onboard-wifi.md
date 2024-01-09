---
date: 2020-03-11
title: WiFi-Modul
categories: onboard
description: Mit dem verbauten WiFi Chip kannst du dich mit dem Internet verbinden und Messwerte speichern & teilen.
type: Document
---

Der ESP32 ist das Verbindungsstück, um die senseBox mit dem Internet zu verbinden. Die Daten der senseBox werden per WLAN (WiFi) in das bestehende Netzwerk übertragen. Der ESP32 basiert auf dem ESP32 Mikrocontroller von Espressif.

## Technische Informationen

- Dual-band 2.4GHz und 5GHz WiFi
- Verschlüsselungsprotokolle: WPA/WPA2/WPA3/WPA2-Enterprise/WPA3-Enterprise/WAPI/WPS and DPP
- Netzwerkdienste: DHCP, DNS, TCP/IP (IPv4), UDP, HTTP, HTTPS
- Bezeichnung: ESP32

## Verbindungstest

Um die Verbindung des Bees mit dem Internet zu testen, also sowohl die Funktion der Komponente, als auch des Netzwerks, nutze den folgenden Sketch. Denk daran in den Variablen `ssid` und `pass` die Informationen zu deinem WiFi-Netzwerk anzupassen:

```c++
#include <WiFi.h>
#include <WiFiMulti.h>

WiFiMulti WiFiMulti;

// Passe den Namen und das Passwort des WiFi-Netzwerkes hier an!
char ssid[] = "ssid";
char pass[] = "pass";

void setup()
{
    Serial.begin(115200);
    delay(10);

    // We start by connecting to a WiFi network
    WiFiMulti.addAP(ssid, pass);

    Serial.println();
    Serial.println();
    Serial.print("Waiting for WiFi... ");

    while(WiFiMulti.run() != WL_CONNECTED) {
        Serial.print(".");
        delay(500);
    }

    Serial.println("");
    Serial.println("WiFi connected");
    Serial.println("IP address: ");
    Serial.println(WiFi.localIP());

    delay(500);
}


void loop()
{

}
```

Wenn bei allen Ausgaben im seriellen Monitor Werte angezeigt werden, insbesondere wenn die IP-Adresse etwa in der Form _192.107.256.4_ ausgegeben wird, ist das WiFi-Modul richtig initialisiert und die senseBox kann mit dem Internet genutzt werden.
