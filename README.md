1. Objectif du projet

Le but est de créer un convoyeur autonome capable de :
Piloter un moteur Nema17 (via module GRBL)
Piloter un servo SG90 (via GoPlus2)
Lire un badge RFID I2C pour identifier des objets
Communiquer en Wi-Fi avec Dolibarr, récupérer des produits, envoyer des informations
Afficher les informations sur l’écran du M5Stack
Le projet inclut firmware, électronique et intégration API.


2. Architecture générale

                 +--------------------------+
                 |   Convoyeur_physique     |
                 |                          |
                 |   +--------+   +-------+ |
Utilisateur ---> |   |   M5   |-->| GRBL  |--> Moteur Nema17
(boutons M5)     |   | Stack  |   +-------+ |
                 |   |        |            |
                 |   |        |-->| GoPlus2 |--> Servo SG90
                 |   |        |            |
                 |   |        |-->| RFID    |
                 +--------------------------+

                   M5Stack ---> API Dolibarr ---> Base MariaDB

3. Matériel utilisé

Composant	                            Rôle
-------------------------------------------------------------------
M5Stack Core	                        Microcontrôleur principal
GRBL Module 13.2	                    Pilotage moteur Nema17
Moteur Nema17	                        Entraînement du convoyeur
GoPlus2	                                Pilotage servo + GPIO
Servo SG90	                            Flap de redirection
RFID Grove I2C	                        Lecture des tags RFID
Alimentation 5V	                        Puissance modules
Structure de convoyeur	                Partie mécanique

4. Installation du projet

