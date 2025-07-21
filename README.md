# Lunettes intelligentes pour aveugles

## Objectif
L'objectif de ce projet de fin d'études est de concevoir et réaliser des lunettes intelligentes, 
ainsi que de développer un circuit électronique composé de composants électroniques et d'outils 
de pointe tels que TinyML. Ces technologies nous permettront de créer différentes fonctionnalités 
dans nos lunettes en utilisant Arduino, Edge Impulse, Audacity, etc.

## Fonctionnalités principales
  - **Détection en temps réel** : Identification automatique d’objets autour de l’utilisateur grâce à une caméra et un modèle IA.
  - **Assistance vocale** : Transmission d’informations via synthèse vocale en arabe pour décrire les objets détectés.
  - **Autonomie locale** : Déploiement complet sur des modules ESP32, sans dépendance à Internet.

## Technologie utilisée
  - **Hardware** : ESP32-CAM, ESP32 DevKit, haut-parleur, capteurs. 
  - **Logiciel** : Edge Impulse pour l’entraînement du modèle, Arduino IDE pour le développement, Audacity pour le traitement audio, HxD pour la conversion hexadécimale.
  - **Modèle IA** : TinyML, optimisé pour la détection d’objets légère et efficace.

[image2.png](https://github.com/Amanidhaouadi/Lunettes-Intelligentes-Pour-Aveugles/blob/main/images/image2.png)
  

## Réalisation 
### Etape 1 :  Formation du modele de detection d'objet avec Edge Impulse

image.png

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

**4. Test de la synthèse vocale**
  - Générer des signaux audio via GPIO 25 de l’ESP32 connecté à un haut-parleur.
  - Utiliser la fonction "audio()" déclenchée par des mots-clés reçus (par ex., "table") pour produire le son correspondant.




---
### Etape 4 : Conception 3D







## Résultats
  - Détection précise et en temps réel d’un ensemble d’objets courants.
  - Interaction vocale fiable pour informer l’utilisateur (en arabe).
  - Dispositif portable, économique et facile à utiliser.

## Impact
  - Amélioration de la mobilité et de la sécurité des personnes aveugles.
  - Solution accessible, respectueuse de la vie privée, et adaptable à différents environnements.
