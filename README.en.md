<p align="right" dir="ltr">
  <a href="./README.md" lang="fr" hreflang="fr" rel="alternate" title="Lire la doc en français" aria-label="Lire la doc en français">Français</a> · 🇬🇧 <strong>English</strong>
</p>

# Frontend Mentor – Product preview card component (solution)

[![Vite](https://img.shields.io/badge/Vite-⚡-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/) [![Tailwind CSS v4](https://img.shields.io/badge/Tailwind%20CSS-v4-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/) [![Netlify](https://img.shields.io/badge/Netlify-deploy-00C7B7?logo=netlify&logoColor=white)](https://www.netlify.com/) [![Live](https://img.shields.io/badge/Live-jb--fem--product--preview--card--component.netlify.app-brightgreen)](https://jb-fem-product-preview-card-component.netlify.app/)

This repo contains my solution to **[Product preview card component](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa)** by Frontend Mentor.

> 🎯 Personal goal: work on semantic HTML and improve accessibility of product components.

---

## 🔎 Overview

### The challenge

- Recreate the provided product card design.
- Make it responsive (mobile & desktop).
- Add hover/focus states.
- Ensure semantic and accessible HTML structure.

### Screenshot

![Solution screenshot](https://jb-fem-product-preview-card-component.netlify.app/og.jpg)

### Links

- Live: https://jb-fem-product-preview-card-component.netlify.app/

---

## 🚀 Running the project

```bash
npm install
npm run dev      # local server
npm run build    # production build (dist/)
npm run preview  # preview the build locally
```

---

## 🧱 Built with

- **Semantic HTML5** (`main`, `article`, `picture/img`, `dl/dt/dd` for prices)
- **Tailwind CSS v4** (_CSS‑first_ approach with `@theme` tokens)
- **Mobile‑first workflow**
- **Locally hosted WOFF2** fonts (Montserrat 500/700, Fraunces 700) + `font-display: swap`
- **Vite** (fast build, strips console/debugger, fingerprinted assets)
- **Netlify** (security & caching headers via `netlify.toml`)
- ***

## 🧭 Approach & implementation choices

### HTML structure

- A `<h1 class="sr-only">` provides a clear page title for screen readers without interfering with the design.
- Product card is wrapped in an `<article>` split into two columns (`picture` for image, text content on the right).
- Prices are represented using `<dl>` for proper semantics and screen reader support.

Representative snippet:

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

- Defined via `@theme` tokens: colors (`--color-green-500`, `--color-grey`, etc.) and fonts (`--font-montserrat`, `--font-fraunces`).
- Custom components: `.btn-primary`, `.focus-ring`, `.link`.

### Fonts

- **Montserrat** (500, 700) for body text.
- **Fraunces** (700) for headings and prices.

### Images

- Responsive with `picture` + `source`.
- Optimized `alt`: `alt="Gabrielle Essence Eau De Parfum by Chanel"`.

---

## ♿ Accessibility (a11y)

- Clear, concise alt text for the product image.
- Button with descriptive text and decorative icon (`alt=""`).
- `sr-only` content provides extra context for screen readers.
- Prices associated with hidden `dt` elements for better context.

## ⚡ Performance

- **Tailwind v4 JIT** → minimal CSS.
- **WOFF2 fonts** + targeted `preload` + `swap`.
- **Vite**: `sourcemap: false`, `drop: ["console","debugger"]`, `assetsInlineLimit: 0` to avoid useless inlining.
- **Netlify**: long‑term caching for fingerprinted assets/fonts, production security headers.

---

## 🧪 My process

### Technologies used

- **Semantic HTML5 markup**
- **CSS custom properties** (via Tailwind v4 tokens in @theme)
- **Mobile‑first workflow**
- **Vite** (bundler/build)
- **Tailwind CSS v4**
- **Netlify** (hosting & headers)
-

### What I learned

- How to use `<dl>` and `<data>` to represent prices semantically and accessibly.
- Techniques to make a product card fully accessible while staying true to the design.

### Continued development

- Add microdata/JSON-LD (`schema.org/Product`) for SEO.
  Set up a Tailwind V4 class for an auto-responsive grid (to avoid using media queries as much as possible)

### Useful resources

- Tailwind v4 – `@theme` & tokens : https://tailwindcss.com/docs/theme
- MDN – Responsive images (`<picture>`, `srcset`, `sizes`) : https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
- MDN – `<dl>` element : [https://developer.mozilla.org/docs/Web/HTML/Element/dl](https://developer.mozilla.org/docs/Web/HTML/Element/dl)

## 👤 Author

- Website (preview) — https://www.julienborgeon.fr

---

## 🙌 Acknowledgments

Thanks to **Frontend Mentor** for the design and the community for feedback.
Shout‑out to MDN & Tailwind for their excellent documentation.

---

## 📁 Project structure

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
