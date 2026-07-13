# Bento — Paul Guttin

Une page one-page façon Linktree/Bento.me pour présenter Paul Guttin, art director freelance basé à Caen. Construite en HTML/CSS pur, sans framework ni build step.

<p align="center">
  <img src="assets/mascotte.png" width="120" alt="Mascotte Paul Guttin">
</p>

## Aperçu

La page reprend la direction artistique de la carte de visite de Paul :

- **Palette** — bleu `#2e4ea8`, noir `#231f1e`, blanc `#ececec`
- **Typographies** — Montserrat (titres) / BC Novatica CYR (corps de texte, avec repli système)
- **Layout** — une grille bento : profil, réseaux (LinkedIn, Behance, GitHub, contact) et une carte de localisation sur Caen

## Structure du projet

```
Bento/
├── index.html      # Structure de la page
├── styles.css       # Mise en page, couleurs, typographies
├── assets/
│   └── mascotte.png  # Illustration de Paul
└── README.md
```

## Lancer le projet en local

Aucune dépendance à installer. Il suffit de servir le dossier en statique, par exemple :

```bash
python3 -m http.server 8080
```

puis d'ouvrir [http://localhost:8080](http://localhost:8080).

> Ouvrir `index.html` directement en double-clic fonctionne aussi, mais certains navigateurs restreignent les requêtes locales (comme l'iframe de carte) en `file://`.

## Personnaliser

| Élément | Où le modifier |
|---|---|
| Nom, rôle, avatar | `.profile` dans `index.html` |
| Liens (LinkedIn, Behance, GitHub, email) | blocs `.bento-card` dans `index.html` |
| Localisation sur la carte | paramètre `bbox` de l'iframe OpenStreetMap dans `.card-map` |
| Couleurs des cartes | variables `--blue-tint`, `--amber-tint`, etc. et classes `.card-*` dans `styles.css` |
| Polices | règle `@font-face` et `font-family` en haut de `styles.css` |

### À propos de la police BC Novatica CYR

C'est une police commerciale, non disponible sur Google Fonts. Le CSS tente de l'utiliser si elle est installée localement (`local('BC Novatica CYR')`), sinon la page utilise un repli système. Pour un rendu garanti sur tous les navigateurs, ajouter les fichiers `.woff2` de la police et déclarer leur chemin dans la règle `@font-face` de `styles.css`.

## Déployer

La page est 100% statique : elle peut être publiée telle quelle sur GitHub Pages, Netlify, Vercel ou tout hébergeur statique, sans étape de build.

## Crédits

- Fond de carte : [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors
