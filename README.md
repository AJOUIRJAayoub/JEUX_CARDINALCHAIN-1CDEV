# Cardinal Chain - Puzzle Game Terminal

![C](https://img.shields.io/badge/c-%2300599C.svg?style=flat&logo=c&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=flat&logo=windows&logoColor=white)

![Cardinal Chain](/cardinal-chain.png "Cardinal Chain")

## Description

Cardinal Chain est un puzzle game minimaliste en version terminal centré sur le concept de suites croissantes. Le joueur doit relier les nombres dans un ordre croissant en commençant par les cellules marquées 'X', jusqu'à ce que toute la grille soit entièrement colorée. Ce jeu de réflexion développé en C offre une expérience de puzzle unique directement dans votre terminal.

### Caractéristiques principales :
- Interface terminal colorée avec gestion des couleurs Windows
- 12 niveaux de difficulté progressive
- Système de chaînes multiples avec codes couleur
- Contrôles au clavier intuitifs
- Sauvegarde des niveaux dans un fichier externe
- Possibilité de recommencer ou supprimer des chaînes
- Navigation libre entre les niveaux

## Prérequis

- Compilateur C (GCC, MinGW, ou Visual Studio)
- Windows (utilise l'API Windows pour les couleurs)
- Terminal supportant les couleurs

## Installation

1. **Cloner le repository**
   ```bash
   git clone https://github.com/AJOUIRJAayoub/cardinal-chain.git
   cd cardinal-chain
   ```

2. **Compiler le programme**
   ```bash
   gcc main.c -o cardinal-chain.exe
   ```
   
   Ou avec MinGW :
   ```bash
   mingw32-gcc main.c -o cardinal-chain.exe
   ```

3. **Lancer le jeu**
   ```bash
   cardinal-chain.exe
   ```

## Comment jouer

1. **Menu principal**
   - **Z** : Niveau suivant
   - **S** : Niveau précédent
   - **E** : Démarrer le niveau sélectionné
   - **F** : Fermer le jeu

2. **Gameplay**
   - Les cellules 'X' sont les points de départ des chaînes
   - Reliez les nombres dans un ordre croissant (ex: 0→1→2→3...)
   - Chaque chaîne a sa propre couleur
   - La grille est complète quand toutes les cases sont colorées

3. **Contrôles en jeu**
   - **Z** : Déplacer vers le haut
   - **S** : Déplacer vers le bas
   - **Q** : Déplacer vers la gauche
   - **D** : Déplacer vers la droite
   - **C** : Changer de chaîne active
   - **R** : Supprimer la chaîne actuelle
   - **A** : Recommencer le niveau (supprime toutes les chaînes)
   - **P** : Retour au menu de sélection des niveaux

4. **Règles**
   - Vous ne pouvez vous déplacer que vers des nombres égaux ou supérieurs
   - Les cases déjà occupées par une chaîne ne peuvent pas être traversées
   - Toutes les cases de la grille doivent être remplies pour gagner

## Structure du projet

```
cardinal-chain/
├── main.c              # Code source principal
├── level.txt           # Fichier contenant les 12 niveaux
├── cardinal-chain.png  # Image du jeu
├── .gitattributes     # Configuration Git
└── README.md          # Ce fichier
```

## Format des niveaux

Les niveaux sont stockés dans `level.txt` avec le format suivant :
- Premier nombre : nombre de lignes
- Deuxième nombre : nombre de colonnes
- Nombres suivants : valeurs de chaque case (0 = point de départ 'X')

Exemple : `3 3 0 1 2 1 2 3 2 3 0` crée une grille 3x3

## Personnalisation

### Couleurs des chaînes
Dans `main.c`, modifiez le tableau `list_color` :
```c
int list_color[5] = {1, 2, 10, 12, 14}; // Bleu, vert, vert fluo, rouge, jaune
```

### Ajout de niveaux
Ajoutez une ligne dans `level.txt` en respectant le format décrit ci-dessus.

## Structure du code

- **Structures** : `OBJET` représente chaque case de la grille
- **Fonctions de mouvement** : `move_haut()`, `move_bas()`, `move_gauche()`, `move_droite()`
- **Gestion des chaînes** : `choose_chain()`, `del_chain()`, `del_all_chain()`
- **Affichage** : `display()` avec gestion des couleurs Windows
- **Logique de jeu** : `turn()` gère la boucle principale du jeu
- **Vérification** : `win_level()` vérifie si le niveau est complété

## Dépannage

### Le jeu ne compile pas
- Vérifiez que vous utilisez un compilateur compatible Windows
- Assurez-vous d'avoir les headers Windows : `#include <windows.h>`

### Les couleurs ne s'affichent pas
- Utilisez un terminal compatible (cmd.exe, PowerShell)
- Vérifiez que votre terminal supporte les séquences ANSI

### Le fichier level.txt n'est pas trouvé
- Assurez-vous que `level.txt` est dans le même dossier que l'exécutable

## Améliorations possibles

- Portage Linux/Mac (remplacement de l'API Windows)
- Éditeur de niveaux intégré
- Système de score et chronomètre
- Sauvegarde de progression
- Mode tutoriel interactif
- Support des grilles plus grandes

## Remerciements

- Développé en langage C
- Utilisation de l'API Windows pour la gestion des couleurs
- Inspiré des jeux de puzzle minimalistes

## Contexte

Ce projet a été réalisé dans le cadre d'un projet de programmation C à SUPINFO.

## Contact

Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue sur GitHub.

---
Projet SUPINFO - Cardinal Chain
