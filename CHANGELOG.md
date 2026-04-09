# Changelog

Toutes les modifications notables de MaturIA sont documentées ici.
Format : [Keep a Changelog](https://keepachangelog.com/fr/1.0.0/).

---

## [0.4.0] — 2026-04-09

### Ajouté

- **Écran rapport groupe** (`rapport-groupe.html`) — vue consolidée multi-entités
  - Filtres chips "Toutes les Entités / Direction IT / RH" avec état actif
  - Bouton "Exporter PDF" (`window.print()`)
  - Carte recommandation stratégique (icône cible, texte, tag "Programme Découverte")
  - Donut chart SVG (4 segments : Explorateurs, Praticiens, Avancés, Leaders) + légende + total centré
  - Radar SVG pentagonal "Moyenne du Groupe" avec toggle Groupe / Individuel
  - Tableau anonymisé des répondants (initiales, ID, département, mini barre de score colorée)
  - 🎮 **Easter egg** — Konami Code (↑↑↓↓←→←→BA) ou 7 taps sur le logo :
    activation du "Mode Légendaire" avec overlay, score animé 0→100, confetti 5 couleurs domaines

---

## [0.3.0] — 2026-04-09

### Ajouté

- **Écran rapport individuel** (`rapport-individuel.html`) — profil de maturité personnel
  - Score global 74/100 avec niveau "Praticant" et barre de progression animée
  - Radar chart SVG pentagonal (5 axes domaines, anneaux de fond, points colorés par domaine)
  - Barres de score par domaine (5 lignes, couleur + valeur X/5, animation au chargement)
  - Section "Points forts" (2 items avec bullet vert ✓)
  - Section "Axes de progression" (2 items avec bullet orange !)
  - Boutons "Exporter en PDF" (`window.print()`) et "Partager"
  - Carte "Conseil de l'Expert" avec bordure accent usage
  - Bottom nav 5 onglets (Knowledge → Strategy), Mastery actif

---

## [0.2.0] — 2026-04-09

### Ajouté

- **Écran questionnaire** (`questionnaire.html`) — 20 questions réparties sur 5 domaines
  - Domain nav : 5 onglets avec barre de progression colorée par domaine
  - Navigation complète Précédent / Suivant avec persistance des réponses en mémoire
  - Radio-choices animés (cercle vide → cercle plein couleur domaine, outline card)
  - Couleur domaine dynamique via CSS custom property `--couleur-domaine`
  - Image canvas procédurale (bureau sombre + lampe + accent couleur domaine)
  - Compteur global `QUESTION XX / 20`
  - Corpus complet : 4 questions × 5 domaines, 5 choix chacune

---

## [0.1.0] — 2026-04-09

### Ajouté

- **Écran d'accueil** (`index.html`) — premier écran de l'application
  - Top bar avec logo Intellectual Curator et avatar utilisateur
  - Hero graphic animé (canvas — 5 dots flottants par domaine)
  - Titre H1 bicolore + description du diagnostic
  - Bouton CTA "Démarrer le diagnostic" + estimation de temps (~8 min)
  - Grille 2×2 des 4 scores de la session précédente (Knowledge, Usage, Mastery, Strategy)
  - Filet dégradé tricolore (bleu → ambre → menthe)
  - Liste des 5 domaines avec icônes SVG et descriptions
  - Footer avec référence produit
  - Bottom navigation 4 tabs avec état actif

- **Design system** (`SKILL.md`) — tokens CSS, typographie Avenir (3 graisses max),
  composants (boutons, cartes, barre de progression, tableaux, filet décoratif),
  catégorisation chromatique des 5 domaines, principes structurels (zéro bordure,
  élévation tonale, layout asymétrique)

- **README.md** — documentation projet, architecture, instructions de lancement
