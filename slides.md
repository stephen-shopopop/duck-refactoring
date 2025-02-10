---
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to duck refactoring
titleTemplate: '%s - Duck Refactoring'
info: |
  ## Duck refactoring
  Presentation slides for developers.
author: stephen deletang
keywords: code-smell, refactoring
presenter: true
browserExporter: build
download: true,
exportFilename: ducker-refactoring-exported
export:
  format: pdf
  timeout: 30000
  dark: false
  withClicks: false
  withToc: false
twoslash: true
selectable: true
record: dev
contextMenu: true
wakelock: true
overviewSnapshots: false
colorSchema: auto
routerMode: history
aspectRation: 16/9
canvasWidth: 980
themeConfig:
  primary: '#5d8392'
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# Duck refactoring

Presentation slides for developers

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/stephen-shopopop/duck-refactoring" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: intro
---

## Tout logiciel est constitué de code, et c’est la qualité de ce code qui va faire d’une application une application de qualité.

---
layout: center
---

## Définitions

Le réusinage de code est l’opération consistant à retravailler le code source d’un programme informatique, sans toutefois y ajouter des fonctionnalités ni en corriger les bogues, de façon à en améliorer la lisibilité et par voie de conséquence la maintenance, ou à le rendre plus générique.

[Wikipedia](https://fr.wikipedia.org/wiki/Réusinage_de_code)

---
src: ./pages/clean-code-bad-code.md
---

---
src: ./pages/dette-technique.md
---

---
src: ./pages/refactoring.md
---

---

# Quelques liens

- [9 anti-patterns que tout développeur devrait connaitre](https://sahandsaba.com/nine-anti-patterns-every-programmer-should-be-aware-of-with-examples.html)
- [Robert C.Martin blog](https://blog.cleancoder.com)
- [Livre Robert C. MARTIN](https://www.amazon.fr/Coder-proprement-Robert-C-Martin/dp/232600227X/ref=asc_df_232600227X?mcid=7371465f06fa3a9e8297ecf922d7c604&tag=googshopfr-21&linkCode=df0&hvadid=701538268227&hvpos=&hvnetw=g&hvrand=10969840272883976773&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9111056&hvtargid=pla-682551885055&psc=1&gad_source=1)
- [Livre Martin fowlers sur refactoring](https://www.amazon.fr/Refactoring-Comment-améliorer-code-existant/dp/2100801163)

---

# Les extensions vscode indispensable pour le refactoring

- [Abracadabra](https://marketplace.visualstudio.com/items?itemName=nicoespeon.abracadabra&ssr=false#overview)
- [Javascript booster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster)
- [SonarCube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode)
- [Better comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
- [Code metrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Todo tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
- [Vscode react refactor](https://marketplace.visualstudio.com/items?itemName=planbcoding.vscode-react-refactor)

---

# Les packages node

- [Knip finds and fixes unused files, dependencies and exports](https://www.npmjs.com/package/knip)
- [eslint](https://eslint.org)
- [biome](https://biomejs.dev)
- [Oxlint](https://oxc.rs/docs/guide/usage/linter)

---

# Quelques liens utiles

- [20 ReactJS Best Practices](https://medium.com/@rana.adnanali/20-reactjs-best-practices-learned-from-code-reviews-9f846a132e52)
- [React Best Practice](https://medium.com/@onix_react/react-best-practices-to-improve-your-code-a4c68962d5dd)
- [Nodejs Best practice](https://github.com/goldbergyoni/nodebestpractices)

---
layout: end
---
