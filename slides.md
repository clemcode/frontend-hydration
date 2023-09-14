---
theme: apple-basic
highlighter: shiki
colorSchema: 'light'
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: Hydratation front-end
mdc: true
layout: intro-image
image: './assets/cover.jpeg'
---

# Brown Bag Lunch - HelloAsso{.mix-blend-difference}

Hydratation front-end: évitez de boire la tasse !{.drop-shadow-md}

<div class="absolute bottom-10 left-10 text-xs">
Photo de <a href="https://unsplash.com/fr/@aaronburden?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Aaron Burden</a> sur <a href="https://unsplash.com/fr/photos/dXYE1d08BiY?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
</div>

<!--
Présentation Clem
Hydratation : processus appliqué dans le cadre du rendu côté serveur d'une appli JS
Peut s'appliquer à React, Vue, Angular, Svelte, etc.
Je vais utiliser Vue / Nuxt comme exemple
Sujet "transparent" pour les devs front, c'est le framework qui s'en occupe
Mieux comprendre l'hydration permet d'éviter des bugs et d'optimiser les performances
- Un peu de théorie rapide
- Exemples de bugs ou problèmes perf / UX
- Le futur de l'hydration
-->
---

# Sommaire

- Rendering modes
- L'hydratation en détails
- Performance et UX
- Démos
- Le futur de l'hydratation

---

# CSR

Source: [nuxt.com](https://nuxt.com)

![CSR](/assets/csr.svg){.w-4/5}


---

# SSR

Source: [nuxt.com](https://nuxt.com)

![SSR](/assets/ssr.svg){.w-4/5}

---
transition: none
---

![Static HTML](/assets/hydration/1.png){.w-3/5 .mx-auto}

---
transition: none
---

![Links](/assets/hydration/2.png){.w-3/5 .mx-auto}

---
transition: none
---

![Links](/assets/hydration/3.png){.w-3/5 .mx-auto}

---
transition: none
---

![Links](/assets/hydration/4.png){.w-3/5 .mx-auto}

---

![Links](/assets/hydration/5.png){.w-4/5 .mx-auto .mt-24}

---

# Les inconvénients de l'hydratation

<v-clicks>

- Faire le travail "deux fois"
- Page non interactive pendant l'hydratation
- Risque de bugs ou de dégradation des performances
- "Flash" de contenu ou de styles

</v-clicks>

---

# Le futur de l'hydratation

---

# Scripts plus légers

Utiliser des méthodes de compilation plus agressives pour diminuer la taille des scripts
- Svelte, Solid...
- Vue Vapor mode

---

# Lazy / Partial hydration

- Vue 3 : Choisir une stratégie d'hydratation au niveau du composant

---

# Components Islands

- Une page statique par défaut avec des "îlots" d'interactivité

---

# Server Components (Nuxt)

- Une page dynamique par défaut avec des "îlots" statiques rendus uniquement côté serveur