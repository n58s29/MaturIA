# MaturIA — Design System

Ce fichier définit l'identité visuelle de MaturIA. **Applique systématiquement ces règles** pour tout fichier HTML, composant UI ou écran produit dans ce projet.

---

## 1. Palette de couleurs

Mode **clair** (outil applicatif / formulaire).

```css
:root {
  /* === Surfaces === */
  --surface: #f7f9ff;                 /* Fond principal */
  --surface-basse: #f1f4fa;           /* Zones secondaires, sidebar */
  --surface-haute: #dfe3e8;           /* États inactifs, champs */
  --surface-flottante: #ffffff;       /* Cartes, modules actifs */

  /* === Texte === */
  --sur-surface: #181c20;             /* Texte principal */
  --sur-surface-secondaire: #44474e;  /* Texte secondaire */

  /* === Identité === */
  --primaire: #001b44;                /* Titres, en-tête, boutons */
  --primaire-conteneur: #123062;      /* Sidebar, zones profondes */
  --sur-primaire: #ffffff;            /* Texte sur fond primaire */

  /* === Accents par domaine === */
  --connaissance: #0088cc;            /* Domaine 1 — bleu vif */
  --usage: #00b388;                   /* Domaine 2 — menthe */
  --maitrise: #eed484;                /* Domaine 3 — ambre */
  --satisfaction: #8374d1;            /* Domaine 4 — lavande */
  --vision: #dc582a;                  /* Domaine 5 — ocre */

  /* === Fonctionnels === */
  --succes-fond: #d3e9e5;
  --ombre-ambiante: rgba(0, 26, 66, 0.06);
  --bordure-fantome: rgba(116, 119, 128, 0.15);

  /* === Filet décoratif === */
  --filet: linear-gradient(90deg, #0088cc, #eed484, #00b388);
}
```

### Règles d'utilisation

- **Fond de page** : `--surface` (#f7f9ff)
- **Cartes actives** : `--surface-flottante` (#ffffff) sur fond `--surface`
- **Sidebar / rail domaines** : `--surface-basse` (#f1f4fa) ou `--primaire` (#001b44) pour un rail sombre
- **Texte principal** : `--sur-surface` (#181c20) — jamais de noir pur (#000)
- **Texte secondaire** : `--sur-surface-secondaire` (#44474e)
- **Titres** : `--primaire` (#001b44)

---

## 2. Typographie

### Police : Avenir

```css
:root {
  --police-display: 'Avenir', 'Avenir Next', sans-serif;
  --police-corps: 'Avenir', 'Avenir Next', Arial, sans-serif;
}
```

### Règle absolue sur les graisses

> **JAMAIS** de `font-weight: 600`, `700`, `800` ou `900`.
> Trois graisses autorisées uniquement :

| Graisse | Usage |
|---------|-------|
| **Medium (500)** | Titres (H1, H2), eyebrow labels, badges, emphase |
| **Regular (400)** | Sous-titres (H3), boutons, navigation, interface |
| **Light (300)** | Corps de texte, descriptions, paragraphes, listes |

### Hiérarchie typographique

| Niveau | Graisse | Taille | Détails |
|--------|---------|--------|---------|
| **Display** | 500 | `clamp(2.5rem, 5vw, 4.5rem)` | `line-height: 1.05`, `letter-spacing: -0.02em` |
| **H1** | 500 | `clamp(1.8rem, 3vw, 2.6rem)` | `line-height: 1.15` |
| **H2** | 500 | `clamp(1.3rem, 2vw, 1.8rem)` | `line-height: 1.2` |
| **H3** | 400 | `1.1rem` | `line-height: 1.3` |
| **Eyebrow** | 500 | `11px` | `uppercase`, `letter-spacing: 0.1em`, couleur accent domaine |
| **Body** | 300 | `1rem` | `line-height: 1.65` |
| **Body small** | 300 | `0.875rem` | `line-height: 1.5` |
| **Caption** | 400 | `0.75rem` | `letter-spacing: 0.02em` |
| **Badge** | 500 | `11px` | `uppercase`, `letter-spacing: 0.08em` |

### Règle de saut d'échelle

Ne JAMAIS différencier deux informations en changeant uniquement la graisse à la même taille. Toujours sauter d'échelle (ex: titre H2 + texte Body small).

---

## 3. Principes structurels

### Zéro bordure

Ne JAMAIS utiliser `border: 1px solid` pour séparer des zones. Les frontières se définissent **par changement de couleur de fond** (marches de luminosité).

**Exception unique :** bordure fantôme `outline: 1px solid var(--bordure-fantome)` quand deux zones ont le même hex.

### Élévation par empilement tonal

- Carte `#ffffff` sur fond `#f7f9ff` → le décalage de luminosité crée l'élévation naturellement
- Ombre ambiante teintée marine (pas noire) : `box-shadow: 0 12px 40px var(--ombre-ambiante)`
- Pas d'ombres Material Design, pas de glow

### Layout asymétrique

Privilégier les compositions **1/3 + 2/3** pour créer du rythme (sidebar domaines 1/3, contenu principal 2/3).

---

## 4. Composants

### Boutons

```css
.btn-primaire {
  background: var(--primaire);
  color: var(--sur-primaire);
  border: none;
  border-radius: 0.375rem;
  padding: 0.75rem 1.5rem;
  font-family: var(--police-corps);
  font-weight: 400;
  font-size: 0.9rem;
  cursor: pointer;
  transition: opacity 0.2s;
}
.btn-primaire:hover { opacity: 0.9; }
```

Pas de pills (pas de `border-radius: 2rem`). Pas de glow au hover.

### Cartes

```css
.card {
  background: var(--surface-flottante);
  border-radius: 0.75rem;
  padding: 1.5rem;
  box-shadow: 0 12px 40px var(--ombre-ambiante);
  transition: transform 0.2s;
}
.card:hover {
  transform: translateY(-2px);
}
```

Pas de `border`. L'élévation vient de l'ombre ambiante + contraste de fond.

### Cards de réponse (choix cliquables)

```css
.choix {
  background: var(--surface-flottante);
  border-radius: 0.5rem;
  padding: 1rem 1.25rem;
  cursor: pointer;
  outline: 1px solid var(--bordure-fantome);
  transition: all 0.2s;
}
.choix:hover {
  background: var(--surface-basse);
}
.choix.active {
  outline: 2px solid var(--primaire);
  background: rgba(0, 27, 68, 0.04);
}
```

### Barre de progression

```css
.progress-bar {
  height: 6px;
  background: var(--surface-haute);
  border-radius: 3px;
  overflow: hidden;
}
.progress-fill {
  height: 100%;
  border-radius: 3px;
  transition: width 0.3s;
  /* background: couleur accent du domaine actif */
}
```

### Tableaux

```css
table { width: 100%; border-collapse: collapse; font-size: 0.875rem; }
th {
  padding: 0.75rem 1rem;
  font-weight: 500;
  font-size: 11px;
  letter-spacing: 0.04em;
  text-align: left;
  color: var(--sur-surface-secondaire);
}
td {
  padding: 0.65rem 1rem;
  font-weight: 300;
}
tbody tr:nth-child(even) td { background: var(--surface-basse); }
```

Pas de bordures sur les tableaux. L'alternance de lignes suffit.

### Filet décoratif

```css
.filet {
  height: 3px;
  background: var(--filet);
  border-radius: 2px;
}
```

Utilisé sous le hero et au-dessus du footer.

### Eyebrow pill

```css
.eyebrow {
  display: inline-block;
  font-size: 11px;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  /* couleur = accent du domaine */
}
```

---

## 5. Catégorisation chromatique des 5 domaines

Chaque domaine a sa couleur attitrée. L'appliquer systématiquement sur :
- L'eyebrow label du domaine
- La bordure top ou accent latéral des cartes liées à ce domaine
- Le remplissage du radar chart
- La barre de progression du score par domaine
- Les icônes et numéros associés

| Domaine | Variable | Hex |
|---------|----------|-----|
| 1. Connaissance & culture IA | `--connaissance` | #0088cc |
| 2. Usage & fréquence | `--usage` | #00b388 |
| 3. Maîtrise & qualité | `--maitrise` | #eed484 |
| 4. Satisfaction & perception | `--satisfaction` | #8374d1 |
| 5. Vision stratégique | `--vision` | #dc582a |

---

## 6. Ce qu'il faut faire / éviter

### Faire

- Embrasser le vide — l'espace blanc est fonctionnel
- Utiliser `--primaire` pour les titres sur fond clair
- Séparer les zones par le fond, pas par des traits
- Catégoriser par la couleur : 1 domaine = 1 couleur, partout
- Garder un ton visuel institutionnel et sobre

### Éviter

- Pas de `border: 1px solid` pour séparer du contenu
- Pas de noir pur `#000000`
- Pas de glow, halo, blur sur les boutons
- Pas de `font-weight` > 500
- Pas de `border-radius` > 0.75rem sur les cartes, > 0.375rem sur les boutons
- Pas d'esthétique "SaaS joyeux" ou "startup colorée"
- Pas de bordures décoratives sur les tableaux

---

## 7. Architecture technique

- **Single-file HTML** (vanilla JS/CSS, zéro dépendance, zéro build)
- Radar chart en SVG ou Canvas natif
- Export PDF via `window.print()` ou html2canvas
- Données stockées en mémoire (objet JS), pas de backend
- Responsive : grilles en `1fr` sous 900px
