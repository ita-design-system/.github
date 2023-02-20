# ITA Design System

*En cours d'écriture*. 

**Prérequis clients et fonctionnalités du système de design IT Automotive (ITADS).**

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

## Liens

* [Prérequis clients ITA](https://github.com/ita-design-system/.github/blob/main/prerequis.md) Liste des spécifications que le client d'ITA doit retourner à l'équipe de développement avant de commencer le projet
* [Starter Template ITA](https://github.com/ita-design-system/starter-template) Point de départ pour tout nouveau projet web utilisant le système de design de IT Automotive. 
* [ITA Jekyll LibDoc](https://github.com/ita-design-system/jekyll-libdoc) Générateur de documentation et compilateur SASS
* CSS
  * [c-dis.scss](https://github.com/ita-design-system/c-dis.scss) Composant CSS dédié aux dimensions et comportements liés à la taille des éléments.
  * [c-dim.scss](https://github.com/ita-design-system/c-dim.scss) Composant CSS dédié à la propriété display des éléments. 
  * [c-pos.scss](https://github.com/ita-design-system/c-pos.scss) Composant CSS dédié aux positionnements des éléments. 
  * [c-txt.scss](https://github.com/ita-design-system/c-txt.scss) Composant CSS dédié aux textes.
  * [c-skin.scss](https://github.com/ita-design-system/c-skin.scss) Composant CSS dédié aux aspects et apparences des éléments.
* JS
  * [c-toggle.js](https://github.com/ita-design-system/c-toggle.js) Librairie JS dédiée à la bascule d’état des classes CSS d’un élément.
  * [c-tabs.js](https://github.com/ita-design-system/c-tabs.js) Librairie JS dédiée à la gestion d'onglets et tabulations.
  
## Changelog

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

