# Workflow édition d'un composant générique

Déroulement des opérations à effectuer lors de la modification d'un composant générique:

1. Effectuer les modifications dans le fichier `https://github.com/ita-design-system/c-NOM_DU_COMPOSANT.scss/blob/main/_sass/_NOM_DU_COMPOSANT_generic.scss`.
2. Mettre à jour la documentation markdown associée sur la fonctionnalité ajoutée/modifiée dans le répertoire `content/doc`.
3. Copier coller le contenu du fichier `_NOM_DU_COMPOSANT_generic.scss` dans le README du dépôt du composant à l'endroit dédié à cet effet.
4. Copier coller le fichier `_NOM_DU_COMPOSANT_generic.scss` dans [jekyll-libdoc](https://github.com/ita-design-system/jekyll-libdoc/tree/main/_sass/briks) en committant avec la mention `[FEAT] MAJ NOM_DU_COMPOSANT`
5. Mettre à jour le [changelog](https://github.com/ita-design-system/.github/blob/main/profile/README.md?plain=1) en décrivant les modifications/fonctionnalités apportées.
