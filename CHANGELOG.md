# Changelog

Toutes les modifications notables de MaturIA sont documentées ici.
Format : [Keep a Changelog](https://keepachangelog.com/fr/1.0.0/).

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
