# ITADS

Présentation et généralités du système de design de IT Automotive

## C'est quoi un Design System ?

> Développer des sites et applications en utilisant des composants prêts à l'emploi, accessibles et ergonomiques <br><sub>[Source : Système de Design du Gouvernement](https://www.systeme-de-design.gouv.fr/)</sub>

Des exemples de Design Systems [https://designsystemsrepo.com/](https://designsystemsrepo.com/)

## [CSS] Généralités

Le framework UI CSS s'appelle **briks.scss** et permet de générer des fichiers composants CSS. Les composants CSS sont placés dans des dépôts indépendants à partir de l'organisation [ITADS](https://github.com/orgs/ita-design-system/)

### [CSS] Méthodologie

La méthodologie utilisée est une hybridation de [Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/), [BEM](https://getbem.com/) comme [Bootstrap](https://getbootstrap.com/) et Utility first comme [Tailwind.css](https://tailwindcss.com/). Les grands principes sont :

* **Pas de HTML associé** : chaque classe CSS n'est associée ni à une balise, ni à une arborescence HTML. 
* **Pas d'héritage** : Sauf exceptions, les sélecteurs n'utilisent pas l'héritage mais affectent uniquement les propriétés de l'élément spécifié.

### [CSS] Composant

Un composant `c-` ou `my-` est une classe CSS qui contient zéro ou plusieurs propriétés CSS. Le composant peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe et d'un nom, souvent abrégé, qui désigne une fonctionnalité. Exemples : 
* `c-txt` n'applique aucune propriété sur l'élément spécifié.
  * `c-` : préfixe composant.
  * `txt` : nom du composant dédié au texte.
* `c-flex` applique uniquement la propriété `display: flex` sur l'élément spécifié.
  * `c-` : préfixe composant.
  * `flex` : nom du composant de grille.
* `c-btn` applique de multiples propriétés sur l'élément spécifié.
  * `c-` : préfixe composant.
  * `btn` : nom du composant bouton.

### [CSS] Modifieur

Un modifieur `m-` ou `mod-` est directement associé à un composant. Il n'a aucun effet s'il est utilisé seul. C'est une classe CSS qui vient ajouter ou surcharger une ou plusieurs propriétés CSS à son composant. Le modifieur peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe `m-` et d'un nom, un abrégé qui désigne la ou les propriétés qu'il affecte (`ta-` pour text-align par ex.) et la valeur (`center` par ex.). Exemples :
* Le modifieur `m-main-space-between` associé à son composant `c-flex` applique la propriété `justify-content: space-between`. `m-main-space-between` appliqué seul n'a aucun effet.
  * `m-` : préfixe modifieur
  * `main-` : nom de la propriété affectée (ici l'axe main `justify-content` du composabnt flex)
  * `space-between` : valeur associée (`space-between`).
* Le modifieur `m-ta-center` associé à son composant `c-txt` applique la propriété `text-align: center`. `m-ta-center` appliqué seul n'a aucun effet.
  * `m-` : préfixe modifieur
  * `ta-` : nom de la propriété affectée
  * `center` : valeur associée (`center`).

### [CSS] Utilitaire

Un utilitaire `u-`est une classe qui affecte une et une seule propriété en la surchargeant (si elle est déjà définie) et en forçant son usage. L'utilitaire peut affecter des [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) et des [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements). Le nom de cette classe est composé d'un préfixe et d'un nom, souvent abrégé, qui désigne la fonctionnalité du modifieur. Exemples :
* L'utilitaire `u-bc-primary-500` applique et force la propriété `background-color` à la valeur associée à `primary-500`.
  * `u-` : préfixe utilitaire.
  * `bc-` : nom de la propriété affectée.
  * `primary-500` : nom de la valeur
* L'utilitaire `u-ta-center` applique et force la propriété `text-align` à la valeur associée à `center`.
  * `u-` : préfixe utilitaire.
  * `ta-` : nom de la propriété affectée.
  * `center` : nom de la valeur.

## [TOKENS] Fondamentaux

Les fondamentaux, également appelés *design tokens*, sont les parties élémentaires indivisibles du Design System à partir desquelles les composants, modifieurs et utilitaires sont créés.

### [TOKENS] Couleurs

Le nombre de couleurs est illimité mais il doit respecter les règles suivantes&nbsp;: les couleurs s'organisent en familles, une famille de couleurs complète doit contenir 9 nuances de la plus sombre à la plus claire comme dans l'exemple ci-dessous. *Important&nbsp;: plus le nombre de familles de couleurs est élevé, plus les performances du framework sont impactées.*

La couleur principale de chaque famille est représentée par la **convention de désignation `<NOM_DE_LA_COULEUR>-500`**. Les valeurs abstraites `-400`, `-300`, `-200` et `-100` sont les nuances sombres de la couleur principale et les valeurs `-600`, `-700`, `-800` et `-900` sont des nuances plus claires.

* `<NOM_DE_LA_COULEUR>-100` nuance la plus sombre 
* `<NOM_DE_LA_COULEUR>-200` nuance sombre 
* `<NOM_DE_LA_COULEUR>-300` nuance sombre 
* `<NOM_DE_LA_COULEUR>-400` nuance sombre 
* **`<NOM_DE_LA_COULEUR>-500` couleur principale**
* `<NOM_DE_LA_COULEUR>-600` nuance claire
* `<NOM_DE_LA_COULEUR>-700` nuance claire 
* `<NOM_DE_LA_COULEUR>-800` nuance claire 
* `<NOM_DE_LA_COULEUR>-900` nuance la plus claire 

| Nom de la famille | Nuance | Token | Variable CSS |
|:-|:-|:-|:-|
| primary | 100 | `primary-100` | `--ita-color-primary-100` |
| primary | 200 | `primary-200` | `--ita-color-primary-200` |
| primary | 300 | `primary-300` | `--ita-color-primary-300` |
| primary | 400 | `primary-400` | `--ita-color-primary-400` |
| **primary** | **500** | **`primary-500`** | **`--ita-color-primary-500`** |
| primary | 600 | `primary-600` | `--ita-color-primary-600` |
| primary | 700 | `primary-700` | `--ita-color-primary-700` |
| primary | 800 | `primary-800` | `--ita-color-primary-800` |
| primary | 900 | `primary-900` | `--ita-color-primary-900` |
| neutral | 100 | `neutral-100` | `--ita-color-neutral-100` |
| neutral | 200 | `neutral-200` | `--ita-color-neutral-200` |
| neutral | 300 | `neutral-300` | `--ita-color-neutral-300` |
| neutral | 400 | `neutral-400` | `--ita-color-neutral-400` |
| **neutral** | **500** | **`neutral-500`** | **`--ita-color-neutral-500`** |
| neutral | 600 | `neutral-600` | `--ita-color-neutral-600` |
| neutral | 700 | `neutral-700` | `--ita-color-neutral-700` |
| neutral | 800 | `neutral-800` | `--ita-color-neutral-800` |
| neutral | 900 | `neutral-900` | `--ita-color-neutral-900` |

Exemple de table de couleurs valide
![Exemple de table de couleurs valide](/profile/css-colors-requirements-example-1.webp)

Exemple de table de couleurs invalide
![Exemple de table de couleurs invalide](/profile/css-colors-requirements-example-2-invalid.webp)


### [TOKENS] Espacements

Les espacements sont utilisés dans les marges, les positionnements ainsi que de nombreux composants, modifieurs et uttilitaires. Le nombre d'espacements doit respecter une échelle d'incréments désignés comme suit. *Important&nbsp;: plus le nombre d'espacements est élevé, plus les performances du framework sont impactées.*

Les espacements sont classés par ordre croissant et nommés par une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* L'espacement `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. 
* `1` désigne l'espacement le plus petit fourni par le client.
* `n` désigne le plus grand espacement fourni par le client. 
* `n - 1` correspond à un espacement toujours plus petit que `n`.
* **`<VALEUR>`** chaîne de caractères définissant une longueur dans une unité CSS valide.

Exemple de table d'espacements valides, les différentes valeurs sont fournies par le client.

| Index / nom de l'espacement | Valeur |
|:-|:-|
| 14 | 112px |
| 13 | 96px |
| 12 | 80px |
| 11 | 64px |
| 10 | 56px |
| 9 | 48px |
| 8 | 40px |
| 7 | 32px |
| 6 | 24px |
| 5 | 20px |
| 4 | 16px |
| 3 | 12px |
| 2 | 8px |
| 1 | 4px |
| **0** <sup>1</sup> | **0px** <sup>1</sup> |

<sub>(1) L'espacement `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. <sub>

### [TOKENS] Polices de caractères

Une police de caractères est un ensemble de styles composé de 1 à 9 variations de graisses qui peuvent chacune être déclinées en italique. Une police de caractères peut donc regrouper 1 à 18 styles. 1 style = 1 graisse + italique oui ou non. Le nombre de polices de caractères est illimité, cependant *il est important de noter que plus le nombre de polices est élevé, plus les performances du framework sont impactées.* 

La convention d'appellation du design token pour une police de caractère est la suivante&nbsp;: **`<NOM_D_USAGE>-<GRAISSE>(-i)`**

* **Le `<NOM_D_USAGE>` est défini par l'équipe de développement, il doit être explicite par rapport à la fonction typographique qu'il occupe au sein du Design System.**
* **La `<GRAISSE>` de la police est définie sous forme de centaine comme dans le tableau de correspondance ci-dessous.**
* **-i est ajouté au design token si la police de caractère est italique**

Tableau d'équivalences nom des graisses / centaines CSS `font-weight`.

| Nom de la graisse | Équivalent en centaine CSS `font-weight` |
|:-|:-:|
| Thin | 100 |
| Extra-light | 200 |
| Light | 300 |
| Normal, ou regular | 400 |
| Medium | 500 |
| Semi-bold | 600 |
| Bold | 700 |
| Extra-bold | 800 |
| Black | 900 |

On différencie le nom d'usage du nom de la police afin d'éviter les écueils en cas de changement de police de caractères.

Par exemple `<NOM_D_USAGE>` est `lead` (personnalisation de l'équipe de développement) et `<NOM_DE_LA_POLICE>` est `Montserrat`. Si un jour la police lead doit être changée, sa fonction reste la même empêche la confusion au sein du Design System.

Par exemple pour une police dont le nom est "Montserrat Thin 100 Italic", on utilise un nom d'usage différent du nom de la police, par exemple "lead"

Exemple de design tokens de polices&nbsp;:

| Nom de la police | Nom d'usage | Graisse | Italique | Design token | Variable CSS |
|:-|:-|:-|:-|:-|:-|
| Montserrat | lead | Thin | non | `lead-100` | `--ita-font-family-lead-100` |
| Montserrat | lead | Light | non | `lead-300` | `--ita-font-family-lead-300` |
| Montserrat | lead | Regular | non | `lead-400` | `--ita-font-family-lead-400` |
| Montserrat | lead | Regular | oui | `lead-400-i` | `--ita-font-family-lead-400-i` |
| Montserrat | lead | Semi-bold | non | `lead-600` | `--ita-font-family-lead-600` |
| Montserrat | lead | Bold | non | `lead-700` | `--ita-font-family-lead-700` |
| Montserrat | lead | Black | non | `lead-900` | `--ita-font-family-lead-900` |
| Montserrat | lead | Black | oui | `lead-900-i` | `--ita-font-family-lead-900-i` |

Autre exemple de design tokens de polices&nbsp;:

| Nom de la police | Nom d'usage | Graisse | Italique | Design token | Variable CSS |
|:-|:-|:-|:-|:-|:-|
| Open Sans | lead | Regular | non | `lead-400` | `--ita-font-family-lead-400` |
| Open Sans | lead | Semi-bold | non | `lead-600` | `--ita-font-family-lead-600` |
| Open Sans | headline | Bold | non | `headline-700` | `--ita-font-family-headline-700` |
| Montserrat | headline | Black | non | `headline-900` | `--ita-font-family-headline-900` |
| Montserrat | headline | Black | oui | `headline-900-i` | `--ita-font-family-headline-900-i` |

### [TOKENS] Tailles de texte

Affectations de la taille des éléments textuels de type inline, principalement `font-size`. Le nombre de tailles de texte doit respecter une échelle d'incréments désignés comme suit. *Important&nbsp;: plus le nombre de tailles de texte est élevé, plus les performances du framework sont impactées.*

Les tailles de texte sont classés par ordre croissant et nommées par une **convention de désignation sous forme d'index `<1 à n>`**. 

* `1` désigne la taille de texte la plus petite fournie par le client.
* `n` désigne la plus grande tailler de texte fournie par le client. 
* `n - 1` correspond à une taille de texte toujours plus petite que `n`.

Exemple de tableau de correspondance de tailles de texte valides, les différentes valeurs sont fournies par le client.

| Index / nom de la taille de texte | Valeur | Variable CSS |
|:-|:-|:-|
| 15 | 60px | `--ita-font-size-15` |
| 14 | 54px | `--ita-font-size-14` |
| 13 | 48px | `--ita-font-size-13` |
| 12 | 42px | `--ita-font-size-12` |
| 11 | 36px | `--ita-font-size-11` |
| 10 | 32px | `--ita-font-size-10` |
| 9 | 28px | `--ita-font-size-9` |
| 8 | 24px | `--ita-font-size-8` |
| 7 | 20px | `--ita-font-size-7` |
| 6 | 18px | `--ita-font-size-6` |
| 5 | 16px | `--ita-font-size-5` |
| 4 | 14px | `--ita-font-size-4` |
| 3 | 12px | `--ita-font-size-3` |
| 2 | 10px | `--ita-font-size-2` |
| 1 | 8px | `--ita-font-size-1` |

### [TOKENS] Points de rupture

Également appelés "breakpoints" ou sous l'appellation "screen size", ils sont à base du design adaptif ou "responsive". Les points de ruptures sont des design tokens, des noms personnalisés associés à des valeurs qui forment des intervalles entre lesquels les composants, modifieurs et utilitaires peuvent se comporter différemment. Ils sont directement liés à la taille du terminal de l'utilisateur. 

Le nombre de points de rupture n'est pas limité. *Cependant, plus le nombre de points de rupture est élevé, plus les performances du framework sont impactées.*

Les points de rupture sont nommés selon une **convention de désignation `<NOM_DU_POINT_DE_RUPTURE>` -> `<valeur>`**. 

Exemple de tableau de correspondance de points de rupture

| Nom du point de rupture | Intervalle affecté |
|:-|:-|
| xs | de 0 à 608 px |
| sm | de 608 px à 896 px |
| md | de 896 px à 1288 px |
| lg | de 1288 px à 1576 px |
| xl | de 1576 px à l'infini |


### [TOKENS] Bordures

Une bordure est définie par une épaisseur de trait, un type de trait et une couleur. Les bordures sont classées par ordre croissant de visibilité selon une **convention de désignation sous forme d'index `<1 à n>`**. *Important&nbsp;: plus le nombre de bordures est élevé, plus les performances du framework sont impactées.*

* L'épaisseur désigne la valeur CSS [border-width](https://developer.mozilla.org/fr/docs/Web/CSS/border-width).
* Le trait désigne la valeur CSS [border-style](https://developer.mozilla.org/fr/docs/Web/CSS/border-style).
* La couleur de la bordure est un [design token couleur](#tokens-couleurs).
* `1` désigne la bordure la moins visible fournie par le client.
* `n` désigne la bordure la plus visible fournie par le client. 
* `n - 1` correspond à une bordure moins visible que `n`.

Exemple de tableau de correspondance de bordures valides, les différentes valeurs sont fournies par le client.

| Index / nom de la bordure | Épaisseur | Trait | Token couleur | Variable CSS |
|:-|:-|:-|:-|:-|
| **0** <sup>1</sup> | **0px** <sup>1</sup> | - | - | `--ita-border-0` <sup>1</sup> |
| 1 | 1px | solid | transparent-800 | `--ita-border-1` |
| 2 | 1px | solid | transparent-500 | `--ita-border-2` |
| 3 | 1px | dashed | neutral-500 | `--ita-border-3` |
| 4 | 1px | solid | neutral-900 | `--ita-border-4` |
| 5 | 1px | solid | neutral-500 | `--ita-border-5` |
| 6 | 1px | solid | primary-500 | `--ita-border-6` |
| 7 | 1px | solid | support-success-500 | `--ita-border-7` |
| 8 | 1px | solid | support-warning-500 | `--ita-border-8` |
| 9 | 1px | solid | support-danger-500 | `--ita-border-9` |
| 10 | 1px | solid | neutral-200 | `--ita-border-10` |
| 11 | 2px | solid | neutral-900 | `--ita-border-11` |
| 12 | 2px | solid | neutral-500 | `--ita-border-12` |
| 13 | 2px | solid | neutral-200 | `--ita-border-13` |
| 14 | 3px | solid | neutral-500 | `--ita-border-14` |
| 15 | 3px | solid | primary-500 | `--ita-border-15` |
| 16 | 3px | double | neutral-500 | `--ita-border-16` |

<sub>(1)</sub> Le token `--ita-border-0` est réservé au ITADS. Le client ne doit pas fournir de design token dont l'épaisseur est nulle.

### [TOKENS] Coins arrondis

Un coin arrondi est défini par un ou deux rayons de courbure. Le nombre de coins arrondis n'est pas limité. *Cependant, plus le nombre de coins arrondis est élevé, plus les performances du framework sont impactées.* Les différentes valeurs/combinaisons de valeurs sont fournies par le client.

Les coins arrondis sont classés par ordre croissant et nommés par une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* Le coin arrondi `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. 
* `1` désigne le coin arrondi le plus petit fourni par le client.
* `n` désigne le plus grand coin arrondi fourni par le client. 
* `n - 1` correspond à un coin arrondi toujours plus petit que `n`.
* **`<VALEUR>`** chaîne de caractères directement liée à la valeur CSS comme décrite sur [cette page](https://developer.mozilla.org/fr/docs/Web/CSS/border-top-left-radius) et fournie par le client. Par exemple `10px`, `20%`, `15px 20%`.

Exemple de table coins arrondus valides, les différentes valeurs sont fournies par le client.

| Index / nom de l'arrondi | Valeur | Variable CSS |
|:-|:-|:-|
| 4 | 64px | `--ita-border-radius-4` |
| 3 | 32px | `--ita-border-radius-3` |
| 2 | 8px | `--ita-border-radius-2` |
| 1 | 4px | `--ita-border-radius-1` |
| **0** <sup>1</sup> | **0px** <sup>1</sup> | `--ita-border-radius-0` |

<sub>(1) Le coin arrondi `0` -> `0px` est réservé à l'équipe de développement front-end du ITADS, il n'est pas demandé au client. <sub>

### [TOKENS] Ombres portées ou Élévation

Également appelées **élévation**, les ombres portées sont de simples abstractions de la propriété CSS `box-shadow`. Le nombre d'ombres portées n'est pas limité. *Cependant, plus le nombre d'ombres portées est élevé, plus les performances du framework sont impactées.* Les valeurs des ombres portées sont fournies par le client.

Les ombres portées sont classées par ordre croissant d'élévation selon une **convention de désignation sous forme d'index `<0 à n>` -> `<VALEUR>`**. 

* L'élévation/ombre portée `0` -> `none` est réservé à l'équipe de développement front-end du ITADS, elle n'est pas demandée au client. 
* `1` désigne l'élévation/ombre portée la plus petite fournie par le client.
* `n` désigne la plus grande élévation/ombre portée fournie par le client. 
* `n - 1` correspond à une élévation/ombre portée toujours plus petite que `n`.
* **`<VALEUR>`** chaîne de caractères directement liée à la valeur CSS [box-shadow](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow) et fournie par le client. Les couleurs utilisées doivent être choisies parmi les design tokens de couleurs. Par exemple `10px 5px 5px 0px primary-100`.

| Index / nom de l'élévation | Valeur | Variable CSS |
|:-|:-|:-|
| 3 | 5px 3px 12px 0px neutral-100 | `--ita-shadow-3` |
| 2 | 2px 2px 8px 0px neutral-100 | `--ita-shadow-2` |
| 1 | 1px 1px 5px 0px neutral-100 | `--ita-shadow-1` |
| **0** <sup>1</sup> | **none** <sup>1</sup> | `--ita-shadow-0` |

<sub>(1) L'élevation nulle `0` -> `none` est réservée à l'équipe de développement front-end du ITADS, elle n'est pas demandée au client. <sub>
