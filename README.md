# Stage G1 - Centrale Lille
Projet : Contribution à la conception et la fabrication d’objets connectés pour la commande de systèmes industriels

1 Présentation du projet

Ce projet a pour objectif de valider la faisabilité d’une transmission sans fil rapide d’un événement entre deux systèmes embarqués.

L’architecture repose sur :
- Deux Raspberry Pi
- Deux modules XBee
- Une communication par transmission de niveau logique (0/1)
- Une détection basée sur interruptions GPIO

Le système permet de transmettre un événement détecté sur une Raspberry Pi vers une seconde Raspberry Pi via radio, puis de générer une décision en sortie.

La latence mesurée bout en bout est comprise approximativement entre 4 ms et 8 ms, selon les conditions du canal radio (2.4 GHz).

2 Principe de l’architecture

- Un événement est détecté sur une entrée GPIO de la Raspberry Pi A.
- Une interruption est générée (edge detection).
- La Raspberry Pi A modifie immédiatement un GPIO connecté au module XBee.
- Le XBee transmet le niveau logique par radio.
- La Raspberry Pi B reçoit le niveau sur son GPIO d’entrée.
- Une interruption est déclenchée et une décision est appliquée en sortie.

L’architecture ne repose pas sur un échange de messages UART, mais uniquement sur la transmission d’un état logique.

3 Documentation complète

La documentation détaillée est disponible aux liens suivants :
- Architecture finale : https://docs.google.com/document/d/16QQZv4-3iy9L4u33UKcT2Kcy0yCkg-m2pc2IIzh2Lv4/edit?usp=sharing
- Guide d’installation et de configuration : https://docs.google.com/document/d/1d8mQuYU8x__8xgblVNenOg8umQQmWyAqzHOV3-UrAXM/edit?usp=sharing
