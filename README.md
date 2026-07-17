# VPX Config Switcher

> 🇫🇷 [Français](#français) | 🇬🇧 [English](#english)

---

<a name="français"></a>
# 🇫🇷 Français

Gestionnaire de profils de configuration pour **Visual Pinball X**.  
Basculez instantanément entre vos configs 2D, VR et custom — sans toucher au moindre fichier manuellement.

---

## Ce que ça fait

Sur un pincab ou un PC de simulation de flipper, changer de mode (2D vers VR, ou entre plusieurs versions de VPX) implique de remplacer plusieurs fichiers de configuration à la main. VPX Config Switcher automatise tout ça en un clic.

### Profils
- **Profils illimités** — un profil par mode : pincab 2D, VR Quest, test de perfs, etc.
- **Activation en un clic** — applique tous tes fichiers de config simultanément
- **Modification auto** — si tu édites le profil actif, les fichiers sont ré-appliqués instantanément
- **Partage de profils** — exporte/importe des fichiers `.vpxprofile` pour partager ta config avec la communauté

### Fichiers gérés par profil
- `VPinballX.ini` — config principale de VPX (résolution, rendu, mode VR...)
- `DMDDevice.ini` — config du DMD virtuel, avec mise à jour automatique après fermeture de VPX si une calibration a été faite
- `ScreenRes.txt` — résolution et position des fenêtres (playfield, backglass, DMD)
- **Sortie audio Windows** — bascule le périphérique audio par défaut (casque VR, haut-parleurs cabinet...)
- **Liens symboliques (Symlinks)** — redirige instantanément des dossiers entiers, idéal pour switcher les PuPVideos entre 2D et VR sans copier les fichiers
- **Commandes personnalisées** — exécute n'importe quel script `.bat`, `.exe` ou commande Windows à l'activation du profil (utile par exemple pour Future Pinball)

### Outils
- **Éditeur .ini intégré** — coloration syntaxique par sections, clés et valeurs
- **Lancement de VPX depuis l'app** — ouvre directement l'exe de ton choix, puis capture le `.ini` résultant
- **Détection automatique** des exécutables VPX et des fichiers de config sur le PC
- **Backup automatique** — sauvegarde horodatée avant chaque changement, restauration depuis l'interface (VPX .ini, DMD, ScreenRes)
- **Gestionnaire PuPPacks** — détecte les packs présents en 2D/VR, duplique les manquants, ouvre les dossiers pour configurer les .bat
- **Interface EN / FR** — langue détectée automatiquement, changeable dans les Préférences
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

## Liens symboliques (PuPVideos)

Pour switcher les PuPVideos entre 2D et VR sans dupliquer des centaines de Go :

1. Renomme `PUPVideos` → `PUPVideos_2D`
2. Crée `PUPVideos_VR` avec ta config VR
3. Dans l'onglet **Symlinks** de chaque profil, configure :
   - Profil 2D : `C:\...\PUPVideos` → `C:\...\PUPVideos_2D`
   - Profil VR : `C:\...\PUPVideos` → `C:\...\PUPVideos_VR`

L'app crée une Junction NTFS — aucun droit admin requis, switch instantané.

---

## Commandes personnalisées

L'onglet **Commandes personnalisées** dans chaque profil permet d'exécuter n'importe quelle commande Windows à l'activation du profil :

- Lancer un fichier `.bat` : `C:\scripts\mon_script.bat`
- Lancer un `.exe` : `C:\tools\mondoutil.exe`
- Commande reg : `reg add "HKCU\..." /v "MaClé" /t REG_DWORD /d 1 /f`
- Toute autre commande Windows valide

Les commandes s'exécutent silencieusement en arrière-plan, après que tous les autres fichiers ont été appliqués.

---

## Données locales

Tout reste sur ton PC, rien n'est envoyé sur internet :

| Données | Emplacement |
|---------|-------------|
| Profils | `%APPDATA%\VPXConfigSwitcher\profiles.json` |
| Backups VPX .ini | `%APPDATA%\VPXConfigSwitcher\backups\` |
| Backups DMD | `%APPDATA%\VPXConfigSwitcher\backups_dmd\` |
| Backups ScreenRes | `%APPDATA%\VPXConfigSwitcher\backups_screenres\` |
| Exécutables VPX | `%APPDATA%\VPXConfigSwitcher\executables.json` |
| Langue | `%APPDATA%\VPXConfigSwitcher\language.txt` |
| Config PuPPacks | `%APPDATA%\VPXConfigSwitcher\puppack_settings.json` |

---

## Contribuer / signaler un bug

→ [Ouvrir une issue](https://github.com/Nesta78/VPXConfigSwitcher/issues)

---
---

<a name="english"></a>
# 🇬🇧 English

Profile manager for **Visual Pinball X**.  
Instantly switch between your 2D, VR and custom configs — without touching any file manually.

---

## What it does

On a pinball cabinet or a pinball simulation PC, switching modes (2D to VR, or between VPX versions) requires manually replacing several configuration files. VPX Config Switcher automates all of this in one click.

### Profiles
- **Unlimited profiles** — one profile per mode: 2D cabinet, VR Quest, perf testing, etc.
- **One-click activation** — applies all your config files simultaneously
- **Auto re-apply** — if you edit the active profile, files are instantly re-applied on disk
- **Profile sharing** — export/import `.vpxprofile` files to share your config with the community

### Files managed per profile
- `VPinballX.ini` — main VPX config (resolution, rendering, VR mode...)
- `DMDDevice.ini` — virtual DMD config, with automatic update after VPX closes if a table calibration was made
- `ScreenRes.txt` — window resolution and position (playfield, backglass, DMD)
- **Windows audio output** — switches the default audio device (VR headset, cabinet speakers...)
- **Symbolic links (Symlinks)** — instantly redirects entire folders, ideal for switching PuPVideos between 2D and VR without copying files
- **Custom commands** — run any `.bat`, `.exe` or Windows command when the profile is activated (can be useful for Future Pinball for example)

### Tools
- **Built-in .ini editor** — syntax highlighting for sections, keys and values
- **Launch VPX from the app** — opens your chosen exe directly, then captures the resulting `.ini`
- **Auto-detection** of VPX executables and config files on the PC
- **Automatic backups** — timestamped backup before each change, restore from the interface (VPX .ini, DMD, ScreenRes)
- **PuPPack manager** — detects packs available in 2D/VR, duplicates missing ones, opens folders to configure .bat files
- **EN / FR interface** — language auto-detected, changeable in Preferences
- **Auto-update** — notification and installation from GitHub Releases at startup

---

## Installation

Download `VPXConfigSwitcher.exe` below and double-click it. No installation required.

> **Windows 10 / 11 — 64-bit**  
> No prerequisites. Python, PyQt6 and audio tools are bundled in the exe.

---

## First launch

The app automatically detects your VPX executables and guides you through two steps:

1. Check the VPX versions to use (auto-detected in standard folders)
2. Create your first profile from your current `.ini` config

---

## Symbolic links (PuPVideos)

To switch PuPVideos between 2D and VR without duplicating hundreds of GB:

1. Rename `PUPVideos` → `PUPVideos_2D`
2. Create `PUPVideos_VR` with your VR config
3. In the **Symlinks** tab of each profile, configure:
   - 2D profile: `C:\...\PUPVideos` → `C:\...\PUPVideos_2D`
   - VR profile: `C:\...\PUPVideos` → `C:\...\PUPVideos_VR`

The app creates an NTFS Junction — no admin rights required, instant switch.

---

## Custom commands

The **Custom commands** tab in each profile lets you run any Windows command when the profile is activated:

- Launch a `.bat` file: `C:\scripts\my_script.bat`
- Launch an `.exe`: `C:\tools\mytool.exe`
- Registry command: `reg add "HKCU\..." /v "MyKey" /t REG_DWORD /d 1 /f`
- Any other valid Windows command

Commands run silently in the background, after all other files have been applied.

---

## Local data

Everything stays on your PC, nothing is sent over the internet:

| Data | Location |
|------|----------|
| Profiles | `%APPDATA%\VPXConfigSwitcher\profiles.json` |
| VPX .ini backups | `%APPDATA%\VPXConfigSwitcher\backups\` |
| DMD backups | `%APPDATA%\VPXConfigSwitcher\backups_dmd\` |
| ScreenRes backups | `%APPDATA%\VPXConfigSwitcher\backups_screenres\` |
| VPX executables | `%APPDATA%\VPXConfigSwitcher\executables.json` |
| Language | `%APPDATA%\VPXConfigSwitcher\language.txt` |
| PuPPack settings | `%APPDATA%\VPXConfigSwitcher\puppack_settings.json` |

---

## Contributing / reporting a bug

→ [Open an issue](https://github.com/Nesta78/VPXConfigSwitcher/issues)
