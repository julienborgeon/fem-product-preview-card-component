<p align="right" dir="ltr">
  🇫🇷 <strong>Français</strong> ·
  <a href="./README.en.md" lang="en" hreflang="en" rel="alternate" title="Read this doc in English" aria-label="Read this doc in English">English</a>
</p>

# Frontend Mentor – Product preview card component (solution)

[![Vite](https://img.shields.io/badge/Vite-⚡-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/) [![Tailwind CSS v4](https://img.shields.io/badge/Tailwind%20CSS-v4-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/) [![Netlify](https://img.shields.io/badge/Netlify-deploy-00C7B7?logo=netlify&logoColor=white)](https://www.netlify.com/) [![Live](https://img.shields.io/badge/Live-jb--fem--product--preview--card--component.netlify.app-brightgreen)](https://jb-fem-product-preview-card-component.netlify.app/)

Ce repo contient ma solution au défi **[Product preview card component](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa)** de Frontend Mentor.

> 🎯 Objectif personnel : travailler la sémantique HTML et améliorer l’accessibilité des composants produits.

---

## 🔎 Aperçu

### Le challenge

- Reproduire la carte produit donnée en design.
- Travailler la responsivité (mobile & desktop).
- Ajouter les hover/focus states.
- Utiliser du HTML sémantique et accessible.

### Capture

![Screenshot de la solution](https://jb-fem-product-preview-card-component.netlify.app/og.jpg)

### Liens

- Live : https://jb-fem-product-preview-card-component.netlify.app/

---

## 🚀 Lancer le projet

```bash
npm install
npm run dev      # serveur local
npm run build    # build de production (dossier dist/)
npm run preview  # prévisualisation du build
```

---

## 🧱 Construit avec

- **HTML5 sémantique** (`main`, `article`, `picture/img`, `dl/dt/dd` pour les prix)
- **Tailwind CSS v4** (approche _CSS-first_ avec `@theme` pour définir des tokens)
- **Mobile-first workflow**
- **Polices locales WOFF2** (Montserrat 500/700, Fraunces 700) + `font-display: swap`
- **Vite** (build performant, purge console/debugger, assets fingerprintés)
- **Netlify** (headers de sécurité & cache via `netlify.toml`)
- ***

## 🧭 Démarche & choix d’implémentation

### Structure HTML

- Utilisation d’un `<h1 class="sr-only">` pour fournir un titre de page clair aux lecteurs d’écran sans gêner le design.
- Carte produit structurée en `<article>` avec deux colonnes (`picture` pour l’image et contenu texte).
- Gestion des prix avec `<dl>` pour une meilleure sémantique et accessibilité.

Extrait représentatif :

```html
<dl class="mb-6 flex items-center gap-4">
  <div>
    <dt class="sr-only">Discounted price</dt>
    <dd>
      <data
        value="149.99"
        class="font-fraunces text-[32px] font-bold text-green-500"
      >
        $149.99
      </data>
    </dd>
  </div>
  <div>
    <dt class="sr-only">Original price</dt>
    <dd>
      <del class="font-montserrat text-grey text-sm">$169.99</del>
    </dd>
  </div>
</dl>
```

### Design System (Tailwind v4)

- Utilisation de `@theme` pour définir couleurs (`--color-green-500`, `--color-grey`, etc.) et polices (`--font-montserrat`, `--font-fraunces`).
- Composants custom (`.btn-primary`, `.focus-ring`, `.link`).

### Polices

- **Montserrat** (500, 700) pour le texte de base.
- **Fraunces** (700) pour les titres et prix.

### Images

- `picture` + `source` pour gérer mobile/desktop.
- Texte alternatif optimisé : `alt="Gabrielle Essence Eau De Parfum by Chanel"`.

---

## ♿ Accessibilité (A11y)

- Texte alternatif précis et concis pour l’image produit.
- Bouton clair avec icône décorative `alt=""`.
- Utilisation de `sr-only` pour fournir du contexte sans impacter le visuel.
- Association des prix avec des `dt` masqués pour les lecteurs d’écran.

## ⚡ Performance

- **Tailwind v4 JIT** → CSS minimal.
- **Polices WOFF2** + `preload` ciblé + `swap`.
- **Vite** : `sourcemap: false`, `drop: ["console","debugger"]`, `assetsInlineLimit: 0` pour éviter l’inlining d’assets.
- **Netlify** : cache long sur assets fingerprintés/polices, en-têtes de sécurité pour la version en prod publiée pour la preview.

---

## 🧪 Ma démarche

### Technologies utilisées

- **Semantic HTML5 markup**
- **CSS custom properties** (via tokens Tailwind v4 dans `@theme`)
- **Mobile-first workflow**
- **Vite** (bundler/build)
- **Tailwind CSS v4**
- **Netlify** (hébergement & headers)
-

### Ce que j'ai appris

- L’importance d’utiliser `<dl>` et `<data>` pour représenter correctement des valeurs comme les prix.
- Comment rendre une carte produit accessible tout en respectant le design fourni.

### Pistes d’amélioration

- Ajouter du microdata/JSON-LD pour marquer le produit (schema.org/Product).
- Paramétrer une classe Tailwind V4 pour une grille auto-responsive (afin d'éviter l'usage des media queries un maximum)

### Ressources utiles

- Tailwind v4 – `@theme` & tokens : https://tailwindcss.com/docs/theme
- MDN – Images responsives (`<picture>`, `srcset`, `sizes`) : https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
- MDN – `<dl>` : https://developer.mozilla.org/docs/Web/HTML/Element/dl

## 👤 Auteur

- Website (preview) — https://www.julienborgeon.fr

---

## 🙌 Remerciements

Merci à **Frontend Mentor** pour le design du challenge et à la communauté pour les retours.  
Un clin d’œil aux ressources MDN & Tailwind pour la clarté de leur doc.

---

## 📁 Structure du projet

```bash
└── 📁fem-product-preview-card-component
    └── 📁.vscode
        ├── settings.json
    └── 📁public
        └── 📁assets
            ├── favicon-32x32.png
            ├── icon-cart.svg
            ├── image-product-desktop.jpg
            ├── image-product-mobile.jpg
        └── 📁fonts
            ├── fraunces-v37-latin-700.woff2
            ├── montserrat-v31-latin-500.woff2
            ├── montserrat-v31-latin-700.woff2
        ├── og.jpg
    └── 📁src
        ├── main.css
    ├── .gitattributes
    ├── .gitignore
    ├── .prettierrc
    ├── index.html
    ├── netlify.toml
    ├── package-lock.json
    ├── package.json
    ├── README.en.md
    ├── README.md
    └── vite.config.js
```
