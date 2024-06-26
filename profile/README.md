# ITA Design System

**Documentation du du système de design IT Automotive (ITADS).**


## Liens

* **[Tableau d’abréviations](https://github.com/ita-design-system/starter-template/tree/main#dev-tableau-des-abr%C3%A9viations-modifieurs)** <br>Correspondances entre abréviations et propriétés CSS.
* **[Starter Template ITA](https://github.com/ita-design-system/starter-template)** <br>Point de départ pour tout nouveau projet web utilisant le système de design de IT Automotive. 
* **[ITA Jekyll LibDoc](https://github.com/ita-design-system/jekyll-libdoc)** <br>Générateur de documentation et compilateur SASS
* CSS
  * **[c-dis.scss](https://github.com/ita-design-system/c-dis.scss)** <br>Composant CSS dédié aux dimensions et comportements liés à la taille des éléments.
  * **[c-dim.scss](https://github.com/ita-design-system/c-dim.scss)** <br>Composant CSS dédié à la propriété display des éléments. 
  * **[c-pos.scss](https://github.com/ita-design-system/c-pos.scss)** <br>Composant CSS dédié aux positionnements des éléments. 
  * **[c-txt.scss](https://github.com/ita-design-system/c-txt.scss)** <br>Composant CSS dédié aux textes.
  * **[c-skin.scss](https://github.com/ita-design-system/c-skin.scss)** <br>Composant CSS dédié aux aspects et apparences des éléments.
  * **[utilities.scss](https://github.com/ita-design-system/utilities.scss)** <br>Utilitaires génériques.
* Javascript
  * **[c-toggle.js](https://github.com/ita-design-system/c-toggle.js)** <br>Librairie JS dédiée à la bascule d’état des classes CSS d’un élément.
  * **[c-tabs.js](https://github.com/ita-design-system/c-tabs.js)** <br>Librairie JS dédiée à la gestion d'onglets et tabulations.
  * **[c-scrollsyncbar.js](https://github.com/ita-design-system/c-scrollsyncbar.js)** <br>Librairie JS permettant d'afficher/masquer des éléments HTML progressivement en fonction du sens de défilement de la fenêtre.
  * **[c-scrollspy.js](https://github.com/ita-design-system/c-scrollspy.js)** <br>Librairie JS dédiée à la détection de la position d'un élément DOM dans la fenêtre de visualisation.
  * **[c-preview.js](https://github.com/ita-design-system/c-preview.js)** <br>Librairie JS dédiée à l'affichage et des fichiers sélectionnés sur un input type="file"
* **[Workflow édition d'un composant générique](https://github.com/ita-design-system/.github/blob/main/workflow-edition-composant-generique.md)** <br>Déroulement des opérations à effectuer lors de la modification d'un composant générique.
* **[Prérequis clients ITA](https://github.com/ita-design-system/.github/blob/main/prerequis.md)** <br>Liste des spécifications que le client d'ITA doit retourner à l'équipe de développement avant de commencer le projet


## But du projet

- [ ] **Fournir au client un design sur-mesure** tout en assurant une compatibilité  d'usage et une bonne [expérience développeur (DX)](https://search.brave.com/search?q=developer+experience) entre les différent projets d'ITA.
- [ ] **Créer un ensemble d'outils front-end, UI et UX** prêts à l'emploi, accessibles, ergonomiques et réutilisables compatibles avec la pile technologique d'ITA.
- [ ] **Obtenir l'adhésion** de toute l'équipe de développement sur méthodologie front-end commune.
- [ ] **Coordonner les attentes et besoins front-end** des différentes équipes de développement au sein d'ITA.
- [ ] **Regrouper les prérequis** (spécifications, données, fichiers) que ITA attend du client dans une documentation claire, concise et explicite.
- [ ] **Développer des composants front-end** (HTML CSS et JS) génériques, réutilisables et paramétrables.
- [ ] **Rendre l'usage de ces composants simple**, accessible et paramétrable.
- [ ] **Documenter l'usage et le développement** des composants.
- [ ] **Donner envie de l'utiliser** à l'ensemble de l'équipe de développement.

<details>
  <summary><strong>Changelog</strong></summary>
 
### 2024.04.19

* [FEAT] Ajout utilitaire box-shadow sur utilitaires [démo](https://ita-design-system.github.io/utilities.scss/#utility-box-shadow):
  * `u-bs-0` -> `box-shadow: none !important`
 

### 2023.11.30

* [FEAT] Ajout modifieurs dédiés aux césures tirets sur c-txt [démo](https://ita-design-system.github.io/c-txt.scss/content/word-break.html):
  * `m-hy-auto` -> `hyphens: auto`
  * `m-hy-manual` -> `hyphens: manual`
  * `m-hy-none` -> `hyphens: none`
 

### 2023.10.13

* [FEAT] Ajout modifieurs dédiés à la graisse des textes sur c-txt [démo](https://ita-design-system.github.io/c-txt.scss/):
  * `m-fw-100` -> `font-weight: 100`
  * `m-fw-200` -> `font-weight: 200`
  * `m-fw-300` -> `font-weight: 300`
  * `m-fw-400` -> `font-weight: 400`
  * `m-fw-500` -> `font-weight: 500`
  * `m-fw-600` -> `font-weight: 600`
  * `m-fw-700` -> `font-weight: 700`
  * `m-fw-800` -> `font-weight: 800`
  * `m-fw-900` -> `font-weight: 900`

### 2023.04.27

[RELEASE] [c-scrollsyncbar.js v0.1.0](https://github.com/ita-design-system/c-scrollsyncbar.js/releases/tag/v0.1.0)

### 2023.04.25

[RELEASE] [c-scrollspy.js v0.1.0](https://github.com/ita-design-system/c-scrollspy.js/releases/tag/v0.1.0)

### 2023.04.18

[RELEASE] [c-toggle.js v0.1.2](https://github.com/ita-design-system/c-toggle.js/releases/tag/v0.1.2)

### 2023.04.17

[RELEASE] [c-toggle.js v0.1.1](https://github.com/ita-design-system/c-toggle.js/releases/tag/v0.1.1)

### 2023.04.14

[FEAT] Release [c-preview.js](https://github.com/ita-design-system/c-preview.js) Librairie JS dédiée à l'affichage et des fichiers sélectionnés sur un input type="file"

### 2023.03.16

* [FEAT] Ajout modifieurs dédiés au background sur c-skin [démo](https://ita-design-system.github.io/c-skin.scss/):
  * background: `m-bg-0` et `m-bg-none` (équivalents) -> `background: none`
  * background-size: 
    * `m-bsize-cover` -> `background-size: cover`
    * `m-bsize-contain` -> `background-size: contain`
  * background-repeat: 
    * `m-brep-no-repeat` -> `background-repeat: no-repeat`
    * `m-brep-repeat-x` -> `background-repeat: repeat-x`
    * `m-brep-repeat-y` -> `background-repeat: repeat-y`
  * background-position: 
    * `m-bpos-center` -> `background-position: center`

### 2023.03.14

* [FEAT] Ajout modifieurs
  * `m-maxw-80vw` `m-maxw-100vw` [c-dim width](https://ita-design-system.github.io/c-dim.scss/content/width.html)  
  * `m-maxh-80vh` `m-maxh-100vh` [c-dim height](https://ita-design-system.github.io/c-dim.scss/content/height.html) 

### 2023.03.02

* [FEAT] Ajout `m-lh-7` `m-lh-8` et `m-lh-9` line height 1.7em 1.8em et 1.9em sur [c-txt](https://ita-design-system.github.io/c-txt.scss/) 

### 2023.02.27

* [FEAT] Ajout `m-pe-auto` (pointer-events: auto) sur [c-skin](https://ita-design-system.github.io/c-skin.scss/) 

### 2023.02.23

* [FEAT] Ajout [scroll-snap](https://ita-design-system.github.io/c-dim.scss/content/scroll-snap.html) et [scroll-behavior](https://ita-design-system.github.io/c-dim.scss/content/scroll-behavior.html) sur [c-dim](https://ita-design-system.github.io/c-dim.scss/) 

### 2023.02.20

* [FEAT] Ajout de la vérification de la portée des propriétés CSS de chaque composant c-dis, c-dim, c-pos, c-txt et c-skin. Si une propriété CSS déclarée n'est pas associée au scope du composant, un @warn SASS s'affiche dans la console.
  * `WARNING: PROPERTY_NAME is not supported in c-COMPONENT_NAME scope`
  * Par exemple `WARNING: transform is not supported in c-skin scope`
* [DOC] [Liste complète](https://github.com/ita-design-system/starter-template#css-composant) de la portée des propriétés des composants. 

### 2023.02.15

* [DOC] Réorganisation de la documentation.
* [DOC] Mise à jour de la documentation dans [Starter Template ITA](https://github.com/ita-design-system/starter-template).
* [FEAT] Dépréciation des $briks-borders qui ne sont plus des design tokens et donc plus demandés au client. 
  * Les `border-width` et les `border-style` sont factorisés dans [c-skin_generic](https://github.com/ita-design-system/c-skin.scss/blob/main/_sass/_skin_generic.scss):
   * `border-width` 3 épaisseurs disponibles dans c-skin générique: 1px, 2px et 3px. Pour plus d'épaisseurs, les renseigner dans [c-skin extension](https://github.com/ita-design-system/starter-template/blob/main/_sass/_skin_extension.scss).
   * `border-style` 1 style disponible dans c-skin générique: solid.  Pour plus de styles de bordures, les renseigner dans [c-skin extension](https://github.com/ita-design-system/starter-template/blob/main/_sass/_skin_extension.scss).
   * `border-color` les couleurs de bordures sont à renseigner selon les besoins, dans [c-skin extension](https://github.com/ita-design-system/starter-template/blob/main/_sass/_skin_extension.scss)
* [FEAT] Retrait des tokens bordures du [Starter Template ITA](https://github.com/ita-design-system/starter-template) et des [tokens génériques](https://github.com/ita-design-system/jekyll-libdoc/blob/main/_sass/briks/settings/tokens/_generic.scss)
* [FEAT] Ajout de l'affichage automatique en JS des variables CSS et valeurs CSS sur les pages dédiées aux design tokens:
  * [Couleurs](https://ita-design-system.github.io/starter-template/content/doc/1.colors.html)
  * [Fontes](https://ita-design-system.github.io/starter-template/content/doc/3.font-families.html)
  * [Tailles de fontes](https://ita-design-system.github.io/starter-template/content/doc/4.font-sizes.html)
  * [Espacements](https://ita-design-system.github.io/starter-template/content/doc/5.spacings.html)
  * [Arrondis](https://ita-design-system.github.io/starter-template/content/doc/6.border-radii.html)
  * [Élévations](https://ita-design-system.github.io/starter-template/content/doc/7.shadows.html)
* [DOC] Mise à jour [Prérequis clients ITA](https://github.com/ita-design-system/.github/blob/main/prerequis.md).


</details>

