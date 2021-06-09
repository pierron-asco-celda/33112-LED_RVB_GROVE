# 33112_LED_RVB_GROVE

LED RGB GROVE [33112](https://www.pierron.fr/interface-arduino-uno-5949.html)
Caractéristiques techniques :
- Alimentation : 5 V
- Consommation : 20 mA
- Couleur : RVB

![33188](/img/L-33112.jpg)

# Exemple :
### Arduino / C++
```cpp
// Baud rate 9600

#include "Pierron_33188.h"

Pierron_33188 capteur = new Pierron_33188();

void setup(){
  Serial.begin(9600);
  Serial.println("Calibration du capteur.\nAppuyer sur une touche pour continuer.");
  while (Serial.available() == 0) {
    // Wait for User to Input Data
  }
  capteur.calibre();
}

void loop(){
  float p = capteur.read();
  Serial.print("Pression : ");
  Serial.print(p);
  Serial.println(" hPa");
  delay(1000);
}
```
## À propos :

PIERRON ASCO-CELDA (https://www.pierron.fr/).
