# Changelog

Toutes les modifications notables de Guitar Trainer Pro seront documentées dans ce fichier.

## [1.0.0] - 2024-12-25

### Ajouté
- Mode "Notes individuelles" avec 12 notes chromatiques
- Mode "Accords" avec 108 accords
- Détection audio en temps réel via microphone
- Diagrammes interactifs pour tous les accords
- Navigation entre positions multiples (flèches ← →)
- Sélection des types d'accords (9 types disponibles)
- Défilement automatique avec timer configurable
- Affichage optionnel des notes et diagrammes
- Notation française et internationale
- Design moderne avec thème sombre
- Interface responsive (mobile et desktop)

### Positions multiples
- C, Cm, C7 : 2-3 positions
- D, Dm, D7 : 2-3 positions
- E, Em, E7 : 2-3 positions
- F, Fm : 2-3 positions
- G, Gm, G7 : 2-3 positions
- A, Am, A7 : 2-3 positions
- B, Bm, B7 : 2-3 positions

### Technique
- Algorithme d'autocorrélation pour détection de pitch
- Pool de notes sans répétition
- Pool d'accords avec filtrage par type
- Génération dynamique de diagrammes SVG
- Web Audio API pour analyse audio

### Design
- Polices : JetBrains Mono + DM Sans
- Couleurs : thème sombre avec accents cyan/vert
- Animations fluides
- Indicateurs visuels de validation
- Navigation intuitive

## Notes de version

### Fonctionnalités principales
1. **Entraînement aux notes** : Système de rotation garantissant que toutes les 12 notes sont présentées avant répétition
2. **Entraînement aux accords** : 108 accords avec diagrammes complets
3. **Détection audio** : Validation en temps réel des notes jouées
4. **Positions multiples** : Apprentissage des mêmes accords à différents endroits du manche

### Améliorations futures envisagées
- Plus de positions pour tous les types d'accords
- Mode gammes
- Statistiques de progression
- Sauvegarde des préférences
- Mode progression graduée
