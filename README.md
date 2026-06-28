# Mario Clone

Un petit jeu de plateforme HTML5 inspiré de Super Mario Bros.

## Description

Ce projet est une démo de jeu Mario en HTML, CSS et JavaScript. Il utilise un moteur de jeu simple basé sur une grille 32x32, des sprites et des niveaux définis dans un fichier JavaScript.

## Contenu du projet

- `index.html` : page principale qui charge le jeu.
- `Content/style.css` : styles du jeu et des jauges de score/vie.
- `Content/backgrounds/` : images de fond utilisées par le niveau.
- `Content/fonts/` : police utilisée pour l'affichage du score.
- `Content/mario-enemies.png` : sprites des ennemis.
- `Content/mario-objects.png` : sprites des blocs, tuyaux, décorations et objets.
- `Content/mario-peach.png` : sprite de Peach.
- `Content/mario-sprites.png` : sprites de Mario.
- `Scripts/oop.js` : implementation de la classe de base et extension des classes.
- `Scripts/constants.js` : constantes du jeu, vitesse, gravité, chemins d'images.
- `Scripts/keys.js` : gestion des touches du clavier.
- `Scripts/testlevels.js` : définition des niveaux et des objets de niveau.
- `Scripts/main.js` : logique du jeu, entités, collisions, animation.

## Démarrage

1. Ouvrir `index.html` dans un navigateur compatible.
2. Si nécessaire, lancer un serveur local pour éviter les restrictions de chargement de fichiers locaux.

### Option serveur local (recommandé)

- Avec Python 3 :
  - `python -m http.server 8000`
- Puis ouvrir :
  - `http://localhost:8000`

## Contrôles

- Flèche gauche : déplacer Mario vers la gauche
- Flèche droite : déplacer Mario vers la droite
- Flèche bas : accroupir / descendre
- Barre d'espace : sauter
- Touche `A` ou `Ctrl` : accélérer (course / sprint)

## Fonctionnalités

- Niveau de jeu défini par une grille 2D dans `Scripts/testlevels.js`
- Gestion des collisions et du déplacement avec gravité
- Objets actifs : blocs de pièces, champignons, ennemis, tuyaux
- Interface affichant le nombre de pièces et les vies
- Animation en continu et défilement de niveau

## Architecture des entités

- `Level` : charge les niveaux, gère le monde, les entités, le rendu et la boucle de jeu.
- `Figure` : classe de base pour les entités mobiles.
- `Hero` / `Mario` : personnage principal contrôlé par le joueur.
- `Matter` et `Ground` : blocs et obstacles statiques.
- `Decoration` : éléments visuels non bloquants.
- `Item` : objets interactifs comme les blocs à pièces, champignons et étoiles.
- Ennemis : différents types sont définis dans `Scripts/main.js` et réagissent aux collisions et aux sauts.

## Structure des niveaux

- Chaque niveau est défini dans `Scripts/testlevels.js` via `definedLevels`.
- Un niveau contient : `width`, `height`, `id`, `background` et `data`.
- `data` est une grille 2D où chaque cellule indique une classe d'objet : `mario`, `coinbox`, `mushroombox`, `grass_top`, etc.
- Les niveaux utilisent des identifiants de sprite pour placer les objets et décorations.
- Le chargement parcourt la grille et instancie les classes correspondantes pour chaque cellule.

## Notes techniques

- Le jeu démarre automatiquement avec le niveau `definedLevels[0]`.
- La logique principale est dans `Scripts/main.js`, notamment la classe `Level` et les classes d'entités.
- La bibliothèque jQuery 1.7.2 est utilisée pour la manipulation DOM et les événements clavier.

## Améliorations possibles

- ajouter un menu de démarrage
- ajouter de la musique et des effets sonores
- rendre le jeu responsive
- séparer les niveaux dans des fichiers JSON externes
- moderniser le code avec ES6 / modules

## Auteur

Projet d'exemple basé sur un moteur de jeu Mario en HTML5.
