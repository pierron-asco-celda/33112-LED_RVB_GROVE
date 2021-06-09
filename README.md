# 33112 LED RVB GROVE

LED RVB GROVE [33112](https://www.pierron.fr/interface-arduino-uno-5949.html)

<div style="text-align: justify">Ce module "LED RVB GROVE" est basé sur la puce P9813 qui est un pilote LED couleur. Il fournit 3 pilotes à courant constant ainsi qu’une sortie modulée de 256 nuances de gris. Il communique avec un microcontrôleur à l’aide d’une transmission à 2 fils (données et horloge). Cette transmission à 2 fils peut être utilisée pour cascader des modules LED Grove : "Chainable RGB" supplémentaires. La régénération d’horloge intégrée améliore la distance de transmission.</div>

Caractéristiques techniques :
- Alimentation : 5 V
- Consommation : 20 mA
- Couleur : RVB

![33112](/img/L-33112.jpg)

# Installation des fichiers dans IDE Arduino:
<div style="text-align: justify">Créer un nouveau répertoire nommé "Pierron..." dans le dossier "libraries" de votre dossier Arduino.
Y placer tous les fichiers.</div>
Ou
<div style="text-align: justify">télécharger le dépôt en ZIP et dans l'IDE Arduino : Croquis / inclure bibliothèque / ajouter la bibliothèque ZIP.</div>

<div style="text-align: justify">Pour utiliser la librairie dans votre propre projet, importez-la avec  *Sketch > Import Library*.</div>

# Usage :
Pour l’utilisation de ce module référez-vous aux indications présentes sur le circuit imprimé GROVE.

![P-33112](/img/P-33112.jpg)


# RESSOURCES À TÉLÉCHARGER :

Ressource utilisation : [P9813](https://github.com/pierron-asco-celda/Pierron_33188/blob/master/src/Pierron-33188-Datasheet.pdf)

# Schémas :

![SCH-33112](/img/SCH-33112.jpg)
![BRD-33112](/img/BRD-33112.jpg)

# Exemple :
### Arduino / C++
```cpp
#include <ChainableLED.h>

#define NUM_LEDS  5

ChainableLED leds(7, 8, NUM_LEDS);

void setup()
{
  leds.init();
}

float hue = 0.0;
boolean up = true;

void loop()
{
  for (byte i=0; i<NUM_LEDS; i++)
    leds.setColorHSL(i, hue, 1.0, 0.5);
    
  delay(50);
    
  if (up)
    hue+= 0.025;
  else
    hue-= 0.025;
    
  if (hue>=1.0 && up)
    up = false;
  else if (hue<=0.0 && !up)
    up = true;
}
```
## À propos :

PIERRON ASCO-CELDA (https://www.pierron.fr).
