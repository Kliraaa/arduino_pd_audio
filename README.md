# Tutoriel - Les étapes à faire
Copie de prof de l'example de cours 4: https://t-o-f.info/aide/#/logiciels/pd/serie/ascii/audio/
## VSCode
- Clonner le repository
- Installer Platformio (https://t-o-f.info/aide/#/fabrication/platformio/nouveau/)
- Ajouter plugin C++
- Configuration Nano R4 PlatformIO (https://t-o-f.info/aide/#/fabrication/arduino/nano/r4/platformio/)
- Ajouter ce lien de la bibliothèque Bounce2 pour les boutons dans lib_deps = :  https://github.com/thomasfredericks/Bounce2.git (et Chrono si besoin https://t-o-f.info/aide/#/fabrication/arduino/chrono/)
- https://t-o-f.info/aide/#/logiciels/pd/serie/ascii/audio/
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
