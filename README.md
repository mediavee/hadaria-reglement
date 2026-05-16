# 📖 Wiki Hadaria — Guide de contribution

Bienvenue dans le dépôt du wiki officiel de Hadaria. Ce guide explique comment modifier les pages, comprendre la structure du projet et utiliser le Markdown correctement.

---

## 📁 Structure du projet

```
hadaria-reglement/
├── docs/                        ← 📝 Toutes les pages du wiki
│   ├── index.md                 ← Page d'accueil
│   ├── reglement-general.md
│   ├── reglement-events-pvp.md
│   ├── reglement-farm.md
│   ├── reglement-pillage.md
│   └── stylesheets/
│       └── extra.css            ← 🎨 Style personnalisé
├── mkdocs.yml                   ← ⚙️  Configuration du site
└── README.md                    ← 📖 Ce fichier
```

---

## ✏️ Modifier une page existante

Chaque page est un fichier `.md` dans le dossier `docs/`. Ouvre le fichier correspondant, modifie son contenu, et enregistre. Le site se met à jour automatiquement lors du prochain déploiement.

> 💡 Pour prévisualiser ton Markdown avant de commit :
> **[markdownlivepreview.com](https://markdownlivepreview.com/)**

---

## ➕ Ajouter une nouvelle page

**1.** Crée un fichier `.md` dans `docs/`, par exemple `docs/reglement-commerce.md`

**2.** Ajoute-le dans `mkdocs.yml` sous la clé `nav` :

```yaml
nav:
  - Règlements:
    - Règlement général: reglement-general.md
    - Règlement Commerce: reglement-commerce.md   # ← ici
```

**3.** Commence ton fichier avec un titre H1 :

```markdown
# Règlement Commerce 🛒
```

---

## 📝 Syntaxe Markdown — Référence rapide

### 🔤 Titres

Les titres créent automatiquement des entrées dans la **table des matières** à droite.

```markdown
# Titre principal (H1)     ← affiché en haut de page, un seul par fichier
## Section (H2)            ← entre dans la table des matières
### Sous-section (H3)      ← entre dans la table des matières
#### Niveau 4 (H4)         ← pas dans la table des matières
```

---

### 💬 Texte

```markdown
Texte normal

**Gras**
*Italique*
~~Barré~~
**_Gras et italique_**
`code inline`
```

Rendu :

Texte normal · **Gras** · *Italique* · ~~Barré~~ · **_Gras et italique_** · `code inline`

---

### 📋 Listes

```markdown
- Élément A
- Élément B
  - Sous-élément (2 espaces d'indentation)
  - Sous-élément

1. Premier
2. Deuxième
3. Troisième
```

---

### 🔗 Liens

```markdown
[Texte du lien](https://example.com)              ← lien externe
[Autre page](reglement-general.md)                ← lien interne
[Section précise](reglement-general.md#section)   ← ancre interne
```

---

### 🖼️ Images

```markdown
![Description de l'image](https://example.com/image.png)
```

---

### 📊 Tableaux

```markdown
| Colonne A    | Colonne B    | Colonne C    |
|--------------|:------------:|-------------:|
| Aligné gauche| Centré       | Aligné droite|
| Valeur       | Valeur       | Valeur       |
```

> ℹ️ `:---` = gauche · `:---:` = centré · `---:` = droite

---

### 📦 Blocs de code

````markdown
```python
def bonjour():
    print("Bienvenue sur Hadaria !")
```
````

````markdown
```yaml
nom: exemple
valeur: 42
```
````

Les langages supportés incluent : `python`, `yaml`, `json`, `bash`, `java`, `javascript`, `css`, `html`, `text`…

---

### ⚠️ Admonitions (encadrés colorés)

Ce sont les blocs colorés qui apparaissent sur le wiki. Syntaxe :

```markdown
!!! note "Titre personnalisé"
    Contenu de la note. L'indentation (4 espaces) est obligatoire.

!!! warning "Attention !"
    Ce comportement peut entraîner une sanction.

!!! danger "Interdit"
    Action totalement prohibée sur le serveur.

!!! tip "Conseil"
    Astuce pour les joueurs.

!!! success "Autorisé"
    Ce cas de figure est permis.

!!! info
    Note informative sans titre personnalisé.
```

Pour rendre un encadré **dépliable/collapsible** :

```markdown
??? note "Cliquez pour voir"
    Contenu caché par défaut.

???+ warning "Ouvert par défaut"
    Contenu visible mais repliable.
```

---

### 📐 Blocs HTML dans le Markdown

MkDocs Material supporte du HTML inline pour des cas particuliers :

```markdown
<div style="color: red;">Texte en rouge</div>

Texte normal avec <span style="font-weight:bold;">mot en gras HTML</span>
```

---

## ⚙️ Modifier la configuration (`mkdocs.yml`)

### 🗺️ Modifier la navigation

```yaml
nav:
  - Accueil: index.md
  - Règlements:
      - Règlement général: reglement-general.md
      - Règlement Évents PvP: reglement-events-pvp.md
```

> 🚨 L'indentation YAML est **stricte** : utilise toujours des espaces (jamais des tabulations).

### 🏷️ Modifier le nom du site

```yaml
site_name: Wiki Hadaria
site_description: Règlement officiel du serveur Hadaria
```

### 🌐 Ajouter un lien externe dans la nav

```yaml
nav:
  - Boutique: https://www.hadaria.fr/boutique
```

---

## 🎨 Modifier le style (`docs/stylesheets/extra.css`)

Le fichier CSS surcharge le thème Material. Les variables principales sont définies en haut :

```css
:root {
  --had-purple:       #322d50;   /* Couleur principale (header, titres) */
  --had-purple-light: #7c6fe0;   /* Violet clair (hover, accents) */
  --had-accent:       #5b4fc9;   /* Liens, éléments actifs */
  --had-bg:           #ffffff;   /* Fond général */
  --had-surface:      #f9f8fd;   /* Fond des surfaces (tableaux, code) */
}
```

Pour changer les couleurs du site, **modifie uniquement ces variables** — tout le reste s'adapte automatiquement.

---

## 🚀 Déploiement

Le site est déployé automatiquement via **GitHub Pages** à chaque push sur la branche principale.

Pour prévisualiser en local :

```bash
# Installer MkDocs Material
pip install mkdocs-material

# Lancer le serveur local (http://localhost:8000)
mkdocs serve

# Construire le site statique
mkdocs build
```

---

## 🔍 Ressources utiles

| Ressource | Lien |
|-----------|------|
| 📝 Prévisualiser du Markdown | [markdownlivepreview.com](https://markdownlivepreview.com/) |
| 📚 Doc MkDocs Material | [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/) |
| 🧩 Admonitions | [Types d'admonitions disponibles](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types) |
| 🎨 Icônes & Emojis Material | [Icônes supportées](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/) |
| 🌐 Site Hadaria | [hadaria.fr](https://www.hadaria.fr) |

---

*Wiki Hadaria — Toute modification doit être validée par un administrateur avant d'être fusionnée.*
