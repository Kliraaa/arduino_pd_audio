# Tutoriel - Les étapes à faire
Copie de prof de l'example de cours 4: https://t-o-f.info/aide/#/logiciels/pd/serie/ascii/audio/
## VSCode
- Clonner le repository
- Installer Platformio (https://t-o-f.info/aide/#/fabrication/platformio/nouveau/)
- Ajouter plugin C++
- Configuration Nano R4 PlatformIO (https://t-o-f.info/aide/#/fabrication/arduino/nano/r4/platformio/)
- Ajouter ce lien de la bibliothèque Bounce2 pour les boutons dans lib_deps = :  https://github.com/thomasfredericks/Bounce2.git (et Chrono si besoin https://t-o-f.info/aide/#/fabrication/arduino/chrono/)
- https://t-o-f.info/aide/#/logiciels/pd/serie/ascii/audio/
- Nour:
#include <Arduino.h>
#include <Bounce2.h>
 
#define BROCHE_BOUTON 2
#define BROCHE_BOUTON2 4
 
#define BROCHE_DEL 3
#define BROCHE_DEL2 5
 
Bounce2::Button bouton;
Bounce2::Button bouton2;
 
bool etatDel = LOW;
bool etatDel2 = LOW;
 
void setup()
{
  Serial.begin(115200);
 
  // Bouton 1
  bouton.attach(BROCHE_BOUTON, INPUT_PULLUP);
  bouton.setPressedState(LOW);
  bouton.interval(5);
 
  // Bouton 2
  bouton2.attach(BROCHE_BOUTON2, INPUT_PULLUP);
  bouton2.setPressedState(LOW);
  bouton2.interval(5);
 
  // DEL 1
  pinMode(BROCHE_DEL, OUTPUT);
  digitalWrite(BROCHE_DEL, etatDel);
 
  // DEL 2
  pinMode(BROCHE_DEL2, OUTPUT);
  digitalWrite(BROCHE_DEL2, etatDel2);
}
 
void loop()
{
  // Mettre à jour les deux boutons à chaque tour
  bouton.update();
  bouton2.update();
 
  if (bouton.pressed())
  {
    etatDel = !etatDel;
    digitalWrite(BROCHE_DEL, etatDel);
 
    Serial.print("bouton1 ");
    Serial.println(etatDel ? 1 : 0);
  }
 
  if (bouton2.pressed())
  {
    etatDel2 = !etatDel2;
    digitalWrite(BROCHE_DEL2, etatDel2);
 
    Serial.print("bouton2 ");
    Serial.println(etatDel2 ? 1 : 0);
  }
}
## Pure Data
- Installer pdchoco (https://t-o-f.info/aide/#/logiciels/pd/pdchoco/)
- Installer comport (https://t-o-f.info/aide/#/logiciels/pd/serie/comport/)
- Copier coller le 2_boutons_play / commencer par ça (https://t-o-f.info/aide/#/logiciels/pd/serie/ascii/)
- pour le chanel dans "close, *open 8*, baud 115200, dtr 1" - Gestionnaire de périphériques/Ports (COM et LPT)/ pérépherique série USB (*number*)
## Cercuit
- D2 → bouton 1
  D3 → DEL 1
- D4 → bouton 2
  D5 → DEL 2
<img width="1119" height="420" alt="image" src="https://github.com/user-attachments/assets/013d9040-6f69-48c2-80d4-44d208353e17" />
https://wokwi.com/projects/475911927798973441
