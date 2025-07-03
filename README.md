# 📦 Stage Institut Agro – Nettoyage et Analyse des Données Produits en Circuits Courts

## 🏛️ Contexte

Ce projet de stage, réalisé à **l’Institut Agro** entre mai et juin 2025, s’inscrit dans l’initiative **Pricco** – l’Observatoire des Prix des produits en Circuits Courts. L’objectif général est d’améliorer la qualité des données fournies par quatre grandes plateformes françaises de vente directe en ligne :

- **Cagette**
- **La Ruche qui dit Oui**
- **Socleo**
- **CoopCircuits**

Ces bases de données contiennent des informations hétérogènes concernant les produits, notamment au niveau des unités de mesure et des noms des produits. Ce projet visait donc à uniformiser les unités, identifier les produits bruts, nettoyer les libellés, et permettre l’analyse des prix au kilo des denrées.

---

## 🔍 Objectifs

- Identifier les unités exprimées en grammes et les convertir en kilogrammes ;
- Homogénéiser les noms de produits pour mieux les regrouper ;
- Identifier et exclure les produits transformés ;
- Extraire des données fiables pour visualiser l’évolution des prix au kilo dans le temps ;
- Rendre possible des comparaisons entre plateformes et périodes.

---

## 🧹 Méthodes de Nettoyage

Le projet s'est décliné en **trois méthodes de nettoyage complémentaires**, chacune intégrée dans un dossier spécifique :

### 1. 📂 `nettoyage_par_expressions_regulieres/`

Utilisation d'expressions régulières pour :
- Repérer les déclinaisons de noms de produits ;
- Nettoyer les unités de mesure dans les champs dédiés ou dans le nom du produit ;
- Séparer les jeux de données en sous-ensembles monoproduits ;
- Calculer des indicateurs pour s'assurer qu'aucune donnée n'est perdue.

### 2. 🤖 `nettoyage_par_LLM/` (modèle LLaMA)

Utilisation d’un modèle de langage (LLM) pour :
- Identifier les noms de produits transformés ;
- Ne conserver que les produits **bruts** dans les jeux de données nettoyés ;
- Affiner automatiquement les typologies de produits.

### 3. 🧪 `application_shiny/`

Développement d’une application interactive avec :
- Interface de chargement et visualisation des bases ;
- Conversion automatique des unités (g → kg) ;
- Visualisation des transformations effectuées ;
- Export des données nettoyées pour analyse.

---

## 📊 Objectif final

> **Visualiser les prix au kilo des produits bruts, par plateforme et dans le temps.**

Deux types de visualisations sont envisagés :
- Des **moyennes de prix** par produit et période ;
- Un **indice d’évolution des prix**, à la manière de l’indice INSEE (glissement annuel), afin d’illustrer les tendances sans exposer les données brutes.

---

## 🛠️ Technologies utilisées

- **R** : prétraitement, nettoyage regex, analyse
- **LLM (LLaMA)** : classification automatique des produits
- **R / Shiny** : application interactive
- **tidyverse (dplyr, stringr)**

---

## 📁 Arborescence

```
stage_institut_agro/
├── nettoyage_par_expressions_regulieres/
│   └── scripts_regex.py / fichiers nettoyés
├── nettoyage_par_LLM/
│   └── classification_llm.py / résultats
├── application_shiny/
│   └── app.R / README.md / ui.R / server.R / global.R
└── README.md  ← (ce fichier)
```

---

## 🤝 Partenaires et Confidentialité

Les données utilisées sont **confidentielles**, fournies dans le cadre de partenariats avec les plateformes citées. Toute diffusion de résultats doit respecter l’anonymisation des producteurs et points de distribution.

Pour toute question :
- **Sébastien Lê** – sebastien.le@agrocampus-ouest.fr
- **Manon Pradère** – manon.pradere@inrae.fr
- **Laurence Delattre** – laurence.delattre@univ-lille.fr

---

© 2025 – Projet Pricco, France 2030 – ANR-23-PESA-005
