# VPX Config Switcher v1.0.0

Gestionnaire de profils de configuration pour **Visual Pinball X**.  
Basculez instantanément entre vos configs 2D, VR et custom — sans toucher au moindre fichier manuellement.

---

## Ce que ça fait

Sur un pincab ou un PC de simulation de flipper, changer de mode (2D vers VR, ou entre plusieurs versions de VPX) implique de remplacer le fichier `VPinballX.ini` à la main. VPX Config Switcher automatise ça en un clic.

- **Profils illimités** — un profil par mode : pincab 2D, VR Quest, test de perfs, etc.
- **Activation en un clic** — remplace le `.ini` actif et bascule la sortie audio Windows en même temps
- **Backup automatique** — sauvegarde horodatée du `.ini` avant chaque changement, avec restauration depuis l'interface
- **Éditeur .ini intégré** — coloration syntaxique par sections, clés et valeurs
- **Lancement de VPX depuis l'app** — ouvre directement l'exe de ton choix pour configurer VPX, puis capture le `.ini` résultant dans un profil
- **Détection automatique** des exécutables VPX installés sur le PC
- **Partage de profils** — exporte/importe des fichiers `.vpxprofile` pour partager ta config avec la communauté
- **Changement audio automatique** — bascule la sortie son Windows (casque VR, haut-parleurs cabinet...) à l'activation du profil
- **Mise à jour automatique** — notification et installation depuis GitHub Releases au démarrage

---

## Installation

Télécharge `VPXConfigSwitcher.exe` ci-dessous et double-clique dessus. Aucune installation requise.

> **Windows 10 / 11 — 64 bits**  
> Aucun prérequis. Python, PyQt6 et les outils audio sont embarqués dans l'exe.

---

## Premier lancement

L'app détecte automatiquement tes exécutables VPX et te guide en deux étapes :

1. Coche les versions de VPX à utiliser (détectées automatiquement dans les dossiers courants)
2. Crée ton premier profil à partir de ta config `.ini` actuelle

---

## Changement de sortie audio

Le basculement audio utilise l'API Windows native (IPolicyConfig) — aucun outil tiers requis. Les périphériques disponibles sont détectés en temps réel à chaque ouverture du dialogue de profil.

---

## Données locales

Tout reste sur ton PC :

- Profils : `%APPDATA%\VPXConfigSwitcher\profiles.json`
- Backups : `%APPDATA%\VPXConfigSwitcher\backups\`
- Exécutables configurés : `%APPDATA%\VPXConfigSwitcher\executables.json`

---

## Contribuer / signaler un bug

→ [Ouvrir une issue](https://github.com/Nesta78/VPXConfigSwitcher/issues)
