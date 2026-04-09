# MaturIA — Diagnostic de Maturité IA Générative

Outil de diagnostic interne permettant d'évaluer, positionner et accompagner la transformation des entités du Groupe ABCD dans l'ère de l'intelligence artificielle générative.

## Contexte

MaturIA est un questionnaire structuré en 5 domaines d'évaluation qui produit un profil de maturité IA pour chaque répondant, ainsi qu'une vue consolidée pour les responsables RH, IT et stratégie.

## Domaines évalués

| # | Domaine | Couleur |
|---|---------|---------|
| 1 | **Knowledge** — Compréhension des fondamentaux et culture IA | `#0088cc` |
| 2 | **Usage** — Degré d'adoption et outils déployés au quotidien | `#00b388` |
| 3 | **Mastery** — Niveau d'expertise technique et d'optimisation | `#eed484` |
| 4 | **Satisfaction** — Impact sur l'engagement et le bien-être collaborateur | `#8374d1` |
| 5 | **Strategy** — Gouvernance, éthique et vision à long terme | `#dc582a` |

## Architecture

Single-file HTML — aucune dépendance, aucun build, zéro backend.

```
index.html    — Application complète (HTML + CSS + JS inline)
SKILL.md      — Design system MaturIA (tokens, typo, composants)
CHANGELOG.md  — Historique des versions
```

Données stockées en mémoire (objet JS). Export PDF via `window.print()`.

## Écrans

- **Accueil** (`index.html`) — Présentation du diagnostic, scores de la dernière session, liste des 5 domaines
- **Questionnaire** — 20 questions réparties par domaine, progression visuelle
- **Rapport individuel** — Radar de performance, niveau global, recommandations
- **Rapport groupe** — Vue consolidée multi-entités, distribution par niveau, export PDF

## Design system

Voir [SKILL.md](SKILL.md) pour la palette complète, la typographie (Avenir, 3 graisses uniquement), les composants et les règles structurelles.

## Lancement

Ouvrir `index.html` dans un navigateur. Aucune installation requise.
