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

<!-- 
A ce stade, on a une page statique, sans interactivité
Les scripts sont en train d'être téléchargés, parsés et exécutés
-->
---
transition: none
---

![Links](/assets/hydration/2.png){.w-3/5 .mx-auto}

<!-- 
Si les liens <a> sont cliqués, on  retrouve le comportement d'une MPA classique
D'où l'importance de ne pas utiliser de navigation programmatique pour les éléments de navigation importants.
-->
---
transition: none
---

![Forms](/assets/hydration/3.png){.w-3/5 .mx-auto}

<!-- 
Si les formulaires respectent les standards HTML, il fonctionneront même sans JS
method POST, action, validation HTML...
-->
---
transition: none
---

![Non-interactive](/assets/hydration/4.png){.w-3/5 .mx-auto}

---

![Hydration](/assets/hydration/5.png){.w-4/5 .mx-auto .mt-24}

<!-- 
Vue prend en charge la page en réconciliant le DOM statique et l'arbre de composants
On rajoute les event handlers etc... Le state utilisé pour générer la page en SSR est réutilisé. C'est le payload.
-->
---

# Payload

[Nuxt devtools](https://devtools.nuxt.com/)

![Payload](/assets/payload.png){.w-4/5}

---

# Les inconvénients de l'hydratation

<v-clicks>

- Faire le travail "deux fois"
- Page non interactive pendant l'hydratation
- Risque de bugs ou de dégradation des performances
- "Flash" de contenu ou de styles

</v-clicks>

---

# Takeaways

- Ecrire du HTML sémantique.
- Contrôler la taille du payload.
- Utiliser l'injection de scripts de pré-hydration pour éviter des flashs de contenu.

---

# Le futur de l'hydratation

---

# Scripts plus légers

Utiliser des méthodes de compilation plus agressives pour diminuer la taille des scripts.

- Svelte, [Solid](https://www.youtube.com/watch?v=hw3Bx5vxKl0)...
- [Vue Vapor mode](https://youtu.be/I5mGNB-4f0o?si=h617luElEgLETniF&t=1220)

---

# Lazy / Partial hydration

Vue 3 : Choisir une stratégie d'hydratation au niveau du composant.

*Feature annoncée pour le Q2 2023*

---
layout: image-right
image: '/assets/islands.png'
---
# Components Islands

Une page statique par défaut avec des "îlots" d'interactivité
- [Astro](https://astro.build/)

---

# Server Components (Nuxt)

- Une page dynamique par défaut avec des "îlots" statiques rendus uniquement côté serveur.

---

# Ressources

- [Ryan Carnito - Why hydration in JS frameworks is so challenging?](https://dev.to/this-is-learning/why-efficient-hydration-in-javascript-frameworks-is-so-challenging-1ca3)
- [Podcast Javascript Jabber - Front-end hydration](https://podcastaddict.com/javascript-jabber/episode/152420337)
- [Josh Comeau - Making sense of React server components](https://www.joshwcomeau.com/react/server-components)
- [Patterns.dev](https://www.patterns.dev/posts) > Rendering patterns
