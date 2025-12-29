# Guitar Trainer Pro 🎸

Application web d'entraînement pour guitare avec détection audio en temps réel.

## Fonctionnalités

### 🎵 Modes d'exercice
- **Notes individuelles** : Entraînement à la reconnaissance des 12 notes chromatiques
- **Accords** : 108 accords avec diagrammes interactifs et positions multiples

### 🎸 Diagrammes d'accords
- Représentation visuelle du manche de guitare
- Positions des doigts clairement indiquées
- Multiples positions alternatives pour les accords principaux
- Navigation par flèches entre les positions
- Repères de frettes (1, 3, 5)
- Notation française et internationale

### 🎤 Détection audio
- Analyse en temps réel via microphone
- Algorithme d'autocorrélation pour détection de fréquence
- Validation visuelle des notes jouées (correct/incorrect)
- Affichage de la fréquence en Hz

### ⚙️ Personnalisation
- **Défilement automatique** : timer configurable (1-60 secondes)
- **Sélection des types d'accords** : choisir parmi 9 types (Majeur, Mineur, 7, Maj7, m7, dim, aug, sus4, sus2)
- **Affichage optionnel** : notes de l'accord et diagrammes

### 📊 Base de données
- **108 accords** au total (12 notes × 9 types)
- **Positions multiples** pour les accords principaux (C, D, E, F, G, A, B et leurs variantes)
- Diagrammes pour tous les accords incluant les notes altérées (C#, D#, F#, G#, A#)

## Types d'accords disponibles

1. **Majeur** - Accords majeurs de base
2. **Mineur (m)** - Accords mineurs
3. **Septième (7)** - Accords de dominante
4. **Septième Majeure (Maj7)** - Accords majeurs 7
5. **Mineur Septième (m7)** - Accords mineurs 7
6. **Diminué (dim)** - Accords diminués
7. **Augmenté (aug)** - Accords augmentés
8. **Suspendu 4 (sus4)** - Accords suspendus 4
9. **Suspendu 2 (sus2)** - Accords suspendus 2

## Positions multiples

Les accords suivants disposent de plusieurs positions sur le manche :

### Majeurs (2-3 positions)
- C, D, E, F, G, A, B

### Mineurs (2-3 positions)
- Cm, Dm, Em, Fm, Gm, Am, Bm

### Septièmes (2 positions)
- C7, D7, E7, G7, A7, B7

Utilisez les flèches ← → pour naviguer entre les positions alternatives.

## Utilisation

### Mode Notes individuelles
1. Sélectionner le mode "Notes individuelles"
2. Une note aléatoire s'affiche (parmi les 12 notes chromatiques)
3. Jouer la note sur votre guitare
4. Si la détection audio est activée, l'application valide votre réponse
5. Cliquer sur "Suivant" ou activer le défilement automatique

### Mode Accords
1. Sélectionner le mode "Accords"
2. Choisir les types d'accords à travailler
3. Un accord aléatoire s'affiche
4. Cocher "Afficher les notes de l'accord" pour voir le diagramme
5. Utiliser les flèches pour voir les positions alternatives
6. Jouer l'accord et passer au suivant

### Défilement automatique
1. Activer "Passer automatiquement"
2. Définir la durée d'affichage (1-60 secondes)
3. Le chronomètre démarre et change automatiquement d'exercice

### Détection audio
1. Activer "Activer le microphone"
2. Autoriser l'accès au microphone dans le navigateur
3. Jouer les notes/accords
4. L'application affiche la note détectée et valide si c'est correct

## Caractéristiques techniques

- **Framework** : Vanilla JavaScript (pas de dépendances)
- **Audio API** : Web Audio API pour la détection de fréquence
- **Algorithme** : Autocorrélation pour la détection de pitch
- **Design** : Interface moderne avec thème sombre
- **Responsive** : Adapté mobile et desktop
- **Police** : JetBrains Mono (monospace) + DM Sans

## Structure du code

### Système de notes
- Pool de 12 notes chromatiques
- Aucune répétition avant d'avoir vu toutes les notes
- Ordre aléatoire à chaque cycle

### Système d'accords
- Pool de 108 accords (ou moins selon sélection)
- Format tableau pour positions multiples
- Navigation par index entre les positions
- Génération dynamique des diagrammes

### Détection audio
- Échantillonnage : 4096 samples (fftSize)
- Algorithme : Autocorrélation pour fréquence fondamentale
- Seuil RMS : 0.01 pour filtrer le bruit
- Conversion fréquence → note

## Navigation du diagramme

- **← Flèche gauche** : Position précédente
- **→ Flèche droite** : Position suivante
- **Indicateur** : Affiche la position actuelle (ex: "2/3")
- Les flèches sont désactivées aux extrémités

## Personnalisation du design

### Variables CSS principales
```css
--accent-primary: #00d4aa  /* Vert/cyan principal */
--accent-secondary: #00a8ff /* Bleu */
--bg-primary: #0a0e14     /* Fond sombre */
--success: #3fb950        /* Vert validation */
--accent-danger: #ff3366  /* Rouge erreur */
```

## Compatibilité navigateur

- Chrome/Edge : ✅ Support complet
- Firefox : ✅ Support complet
- Safari : ✅ Support complet (nécessite HTTPS pour microphone)
- Mobile : ✅ Responsive (interface adaptée)

## Améliorations futures possibles

- [ ] Ajouter plus de positions pour les accords Maj7, m7, dim, aug, sus
- [ ] Mode "gammes" pour travailler les gammes
- [ ] Statistiques de progression
- [ ] Sauvegarde des préférences utilisateur
- [ ] Mode entraînement par progression (débutant → avancé)
- [ ] Métronome intégré
- [ ] Export des sessions d'entraînement

## Licence

Application créée pour l'apprentissage de la guitare.

---

**Version** : 1.0  
**Dernière mise à jour** : Décembre 2024
