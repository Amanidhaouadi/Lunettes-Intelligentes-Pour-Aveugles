# Lunettes intelligentes pour aveugles


## Objectif
L'objectif de ce projet de fin d'études est de concevoir et réaliser des lunettes intelligentes, 
ainsi que de développer un circuit électronique composé de composants électroniques et d'outils 
de pointe tels que TinyML. Ces technologies nous permettront de créer différentes fonctionnalités 
dans nos lunettes en utilisant Arduino, Edge Impulse, Audacity, etc.


<img width="261" height="184" alt="image1" src="https://github.com/user-attachments/assets/618e4208-8c27-48f4-a07d-70e66394c756" />


## Fonctionnalités principales
  - **Détection en temps réel** : Identification automatique d’objets autour de l’utilisateur grâce à une caméra et un modèle IA.
  - **Assistance vocale** : Transmission d’informations via synthèse vocale en arabe pour décrire les objets détectés.
  - **Autonomie locale** : Déploiement complet sur des modules ESP32, sans dépendance à Internet.

## Technologie utilisée
  - **Hardware** : ESP32-CAM, ESP32 DevKit, haut-parleur, capteurs. 
  - **Logiciel** : Edge Impulse pour l’entraînement du modèle, Arduino IDE pour le développement, Audacity pour le traitement audio, HxD pour la conversion hexadécimale.
  - **Modèle IA** : TinyML, optimisé pour la détection d’objets légère et efficace.

<img width="580" height="272" alt="image2" src="https://github.com/user-attachments/assets/de13ffe4-78b6-4381-bd31-69d0c51ff072" />



## Réalisation 
### Etape 1 :  Formation du modele de detection d'objet avec Edge Impulse

<img width="397" height="267" alt="image" src="https://github.com/user-attachments/assets/0096e96c-ecf6-44a2-a02c-77b2d98fbc4c" />

---
### Etape 2 : Détection d'objet ( ESP32 CAM )

**1. Mise en place de la bibliothèque Edge Impulse**
  - Importer le fichier ZIP de la bibliothèque via le menu "Sketch" dans l'IDE Arduino.
  - Charger l’exemple "static buffer" de la librairie Edge Impulse.
  
**2. Installation de la carte ESP32-CAM**
  - Ajouter le lien de la carte ESP32 dans le Gestionnaire de cartes Arduino.
  - Installer les cartes ESP32 via le Gestionnaire de cartes.
  
**3. Configuration de la carte ESP32-CAM**
  - Sélectionner le port de communication approprié (par exemple, COM3).
  - Activer la PSRAM pour la carte ESP32-CAM AI-Thinker.
  - Paramètres de configuration :
    * Modèle : ESP32 Wrover Module
    * Partition : Par défaut 4MB avec SPIFFS
    * Vitesse : 115200
      
**4. Test de détection d’objets**
  - Utiliser le modèle FOMO avec l’ESP32-CAM pour la détection d’objets en temps réel.
  - Afficher les résultats via la communication série avec activation d’une LED lors de la détection.


<img width="593" height="281" alt="Capture d'écran 2025-07-21 225521" src="https://github.com/user-attachments/assets/67b16b56-c274-4e39-87f5-eb43db85be3c" />


---
### Etape 3 : Synthèse vocale ( ESP32 DEV KIT )

**1. Vérification du fonctionnement de l’ESP32-CAM**
  - S’assurer que la détection d’objets fonctionne correctement avant de développer la fonctionnalité TTS.

**2. Configuration de la carte ESP32 DevKit**
  - Sélectionner le modèle "DOIT ESP32 DEVKIT V1" et le port dans l’IDE Arduino.

**3. Traitement audio avec Audacity**
  - Importer les fichiers audio et ajuster :
    * Fréquence d’échantillonnage : 48 000 Hz
    * Canal : Mono
    * Résolution : 32 bits
  - Convertir le fichier audio en code hexadécimal avec HxD et l’intégrer dans le code Arduino.


<img width="661" height="256" alt="image 12" src="https://github.com/user-attachments/assets/15e69f9d-5435-4fb3-be2b-cb41ba6b6af2" />


**4. Test de la synthèse vocale**
  - Générer des signaux audio via GPIO 25 de l’ESP32 connecté à un haut-parleur.
  - Utiliser la fonction "audio()" déclenchée par des mots-clés reçus (par ex., "table") pour produire le son correspondant.


<img width="584" height="303" alt="Capture d'écran 2025-07-21 225602" src="https://github.com/user-attachments/assets/bdf0f2b4-96f6-4b4c-bd96-a261e0628990" />


---
### Etape 4 : Conception 3D

<img width="566" height="322" alt="Capture d'écran 2025-07-21 225641" src="https://github.com/user-attachments/assets/6cf0aaf4-8b55-4262-9a53-4ec3bf2412d3" />



## Résultats
  - Détection précise et en temps réel d’un ensemble d’objets courants.
  - Interaction vocale fiable pour informer l’utilisateur (en arabe).
  - Dispositif portable, économique et facile à utiliser.

## Impact
  - Amélioration de la mobilité et de la sécurité des personnes aveugles.
  - Solution accessible, respectueuse de la vie privée, et adaptable à différents environnements.

## Perspectives :
  - la reconnaissance vocale pour aider les utilisateurs à interagir avec leur environnement de manière plus efficace .
  - la reconnaissance faciale pour améliorer encore davantage l'expérience de l'utilisateur.


<img width="400" height="320" alt="Capture d'écran 2025-07-21 230528" src="https://github.com/user-attachments/assets/1b5f7d6c-7955-4b46-bc1a-e27860f5f571" />

