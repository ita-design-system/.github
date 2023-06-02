# Symfony forms

Aide-mémoire de personnalisation des formulaires Symfony complément de https://symfony.com/doc/current/form/form_customization.html.

## Form Types

Les formulaires sont définis dans `src/Form/Type` [doc Symfony](https://symfony.com/doc/current/reference/forms/types.html). Si besoin, on peut paramétrer les attributs dans les Form Types.

## Base

```twig
{{  form(form) }}
```
![Capture d’écran 2023-04-04 à 09 00 31](https://user-images.githubusercontent.com/13103047/229713350-c87ba22c-b4aa-4a5e-87c1-0b3016fd1690.png)

## form_start et form_end

```twig
{{  form_start(form) }}

{{  form_end(form) }}
```
![Capture d’écran 2023-04-04 à 09 00 31](https://user-images.githubusercontent.com/13103047/229713350-c87ba22c-b4aa-4a5e-87c1-0b3016fd1690.png)

## form_start et form_end + attribut class sur `form`

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
{{  form_end(form) }}
```
![Capture d’écran 2023-04-04 à 09 03 25](https://user-images.githubusercontent.com/13103047/229714419-8545c44f-0af6-414d-bdb2-0d038f36ff2b.png)


## form_start et form_end + attribut class sur `form` + 1 input personnalisé

`reference` est le nom du champ

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
    </div>
{{ form_end(form) }}
```
![Capture d’écran 2023-04-04 à 09 13 25](https://user-images.githubusercontent.com/13103047/229716140-87006895-b033-4df3-8169-f8d7c16c0e0e.png)

## form_start et form_end + attribut class sur `form` + 1 input + 1 textarea personnalisés

`reference` et `description` sont les noms des champs

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
    </div>

    {# description #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.description, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.description, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.description) }}
    </div>
{{ form_end(form) }}
```
![Capture d’écran 2023-04-04 à 09 30 25](https://user-images.githubusercontent.com/13103047/229720054-c97d9912-78d0-42fa-99f6-36171e614349.png)

## form_start et form_end + attribut class sur `form` + 1 input + 1 textarea + 1 select personnalisés

`reference`, `description`, `type` sont les noms des champs

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
    </div>

    {# description #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.description, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.description, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.description) }}
    </div>
                
    {# type #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.type, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.type, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.type) }}
    </div>
{{ form_end(form) }}
```

![Capture d’écran 2023-04-04 à 09 34 15](https://user-images.githubusercontent.com/13103047/229721171-65dafd65-dd09-40b2-b609-48e79665f83d.png)


## form_start et form_end + attribut class sur `form` + 1 input + 1 textarea + 1 select + 1 checkbox personnalisés

`reference`, `description`, `type`, `isHomepage` sont les noms des champs

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
    </div>

    {# description #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.description, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.description, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.description) }}
    </div>
                
    {# type #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.type, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.type, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.type) }}
    </div>
                
    {# isHomePage #}
    <div class="c-dis m-flex">
        {{  form_widget(form.isHomePage, { 
                attr: {
                    class: 'c-dis c-dim c-pos m-absolute c-skin m-checkbox-1 m-opa-0'
                }
            })
        }}
        {{  form_label(form.isHomePage, null, { 
                label_attr: {
                    class: 'c-dis m-flex m-cross-center m-gap-3
                    c-txt m-ff-lead-400'
                }
            })
        }}
        {{ form_errors(form.isHomePage) }}
    </div>
{{ form_end(form) }}
```
![Capture d’écran 2023-04-04 à 09 37 33](https://user-images.githubusercontent.com/13103047/229721825-e7424f74-e551-4b3a-b345-c6a498410d5f.png)



## form_start et form_end + attribut class sur `form` + 1 input + 1 textarea + 1 select + 1 checkbox personnalisés + boucle `for` avec nombre indéterminé d'items

`reference`, `description`, `type`, `isHomepage` sont les noms des champs. `slugs` contient une liste indéterminée d'items.

```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
    </div>

    {# description #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.description, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.description, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.description) }}
    </div>

    {# type #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.type, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.type, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.type) }}
    </div>

    {# isHomePage #}
    <div class="c-dis m-flex">
        {{  form_widget(form.isHomePage, { 
                attr: {
                    class: 'c-dis c-dim c-pos m-absolute c-skin m-checkbox-1 m-opa-0'
                }
            })
        }}
        {{  form_label(form.isHomePage, null, { 
                label_attr: {
                    class: 'c-dis m-flex m-cross-center m-gap-3
                    c-txt m-ff-lead-400'
                }
            })
        }}
        {{ form_errors(form.isHomePage) }}
    </div>

    {# Slugs #}
    {% for slug in form.slugs %}
        {# slug value #}
        <div class="c-dis m-flex m-column m-gap-1">
            {{  form_widget(slug.value, { 
                    attr: {
                        class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                        c-txt m-ff-lead-400 m-fs-5
                        c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                    }
                })
            }}
            {{  form_label(slug.value, 'page.label.slug'|trans({}, 'builder_form') ~ ' ' ~ slug.locale.vars.value ~ '/', { 
                    label_attr: {
                        class: 'c-dim m-order--1 
                        c-txt m-ff-lead-600
                        c-skin m-c-blue-700'
                    }
                })
            }}
            {{ form_errors(slug.value) }}
        </div>
    {% endfor %}
{{ form_end(form) }}
```

![Capture d’écran 2023-04-04 à 09 45 24](https://user-images.githubusercontent.com/13103047/229723509-d5aa2d2f-39d7-4019-bbe3-e2fffe4238b0.png)



## Formulaire complet


```twig
{{  form_start(form, {
        attr: {
            class: 'c-dis m-flex m-column m-gap-6
            c-dim m-p-10 m-pt-6 m-w-100'
        }
    }) 
}}
    {# reference #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.reference, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.reference, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.reference) }}
        {% if 'common.hint.reference'|trans({}, 'builder_form') != 'common.hint.reference' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.reference'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# Slugs #}
    {% for slug in form.slugs %}
        {{  form_widget(slug.locale, { 
                attr: {
                    class: 'u-d-none'
                }
            })
        }}
        {{  form_label(slug.locale, null, { 
                label_attr: {
                    class: 'u-d-none'
                }
            })
        }}
        {# slug value #}
        <div class="c-dis m-flex m-column m-gap-1">
            {{  form_widget(slug.value, { 
                    attr: {
                        class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                        c-txt m-ff-lead-400 m-fs-5
                        c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                    }
                })
            }}
            {{  form_label(slug.value, 'page.label.slug'|trans({}, 'builder_form') ~ ' ' ~ slug.locale.vars.value ~ '/', { 
                    label_attr: {
                        class: 'c-dim m-order--1 
                        c-txt m-ff-lead-600
                        c-skin m-c-blue-700'
                    }
                })
            }}
            {{ form_errors(slug.value) }}
        </div>
    {% endfor %}

    {# status #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.status, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.status, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.status) }}
        {% if 'common.hint.status'|trans({}, 'builder_form') != 'common.hint.status' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.status'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# type #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.type, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.type, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.type) }}
        {% if 'common.hint.type'|trans({}, 'builder_form') != 'common.hint.type' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.type'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# uiModel #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.uiModel, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-10 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1 m-appearance-none m-bg-2'
                }
            })
        }}
        {{  form_label(form.uiModel, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.uiModel) }}
        {% if 'common.hint.ui_model'|trans({}, 'builder_form') != 'common.hint.ui_model' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.ui_model'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# publicationDate #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.publicationDate, { 
                attr: {
                    placeholder: 'dd/MM/yyyy',
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.publicationDate, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.publicationDate) }}
        {% if 'common.hint.publication_date'|trans({}, 'builder_form') != 'common.hint.publication_date' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.publication_date'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# description #}
    <div class="c-dis m-flex m-column m-gap-1">
        {{  form_widget(form.description, { 
                attr: {
                    class: 'c-dim m-pt-3 m-pr-4 m-pb-3 m-pl-4 
                    c-txt m-ff-lead-400 m-fs-5
                    c-skin m-bwidth-2 m-bstyle-solid m-color-scheme-2 m-color-scheme-2-ext-1 m-color-scheme-2-ext-2 m-brad-2 m-transition-1'
                }
            })
        }}
        {{  form_label(form.description, null, { 
                label_attr: {
                    class: 'c-dim m-order--1 
                    c-txt m-ff-lead-600
                    c-skin m-c-blue-700'
                }
            })
        }}
        {{ form_errors(form.description) }}
        {% if 'common.hint.description'|trans({}, 'builder_form') != 'common.hint.description' %}
            <span class="hint
                c-txt m-fs-4
                c-skin m-c-grey-dark-500">
                {{ 'common.hint.description'|trans({}, 'builder_form') }}
            </span>
        {% endif %}
    </div>

    {# isHomePage #}
    <div class="c-dis m-flex">
        {{  form_widget(form.isHomePage, { 
                attr: {
                    class: 'c-dis c-dim c-pos m-absolute c-skin m-checkbox-1 m-opa-0'
                }
            })
        }}
        {{  form_label(form.isHomePage, null, { 
                label_attr: {
                    class: 'c-dis m-flex m-cross-center m-gap-3
                    c-txt m-ff-lead-400'
                }
            })
        }}
        {{ form_errors(form.isHomePage) }}
    </div>

    {# isEditable #}
    <div class="c-dis m-flex">
        {{  form_widget(form.isEditable, { 
                attr: {
                    class: 'c-dis c-dim c-pos m-absolute c-skin m-checkbox-1 m-opa-0'
                }
            })
        }}
        {{  form_label(form.isEditable, null, { 
                label_attr: {
                    class: 'c-dis m-flex m-cross-center m-gap-3
                    c-txt m-ff-lead-400'
                }
            })
        }}
        {{ form_errors(form.isEditable) }}
    </div>

    {# bouton submit #}
    <div class="c-dis m-flex m-main-end">
        {{  form_widget(form.submit, { 
                attr: {
                    class: 'c-dis m-flex m-main-center m-cross-center m-gap-1 
                    c-dim m-p-3 m-pl-6 m-pr-6 m-mt-3
                    c-txt m-ff-lead-700 m-fs-5 m-lh-4 m-td-none 
                    c-skin m-color-scheme-1 m-cur-pointer m-b-0 m-brad-1 m-transition-1'
                }
            })
        }}
    </div>
{{ form_end(form) }}
```

![Capture d’écran 2023-04-04 à 09 49 57](https://user-images.githubusercontent.com/13103047/229724702-731815c4-5fa6-44f3-93ae-3c32e07fd505.png)



## Séparer des éléments de formulaires imbriqués

Un `form.name` contient plusieurs éléments de formulaires

```twig
{% for child in form.name %}
        {{ form_widget(child) }}
        {{ form_label(child) }}
        {{ form_errors(child) }}
{% endfor %}
```
