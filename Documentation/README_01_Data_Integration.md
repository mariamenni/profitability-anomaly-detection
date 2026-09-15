# Notebook 01 — Data Integration

## Objectif

Ce notebook constitue la première étape du pipeline. Il regroupe les différentes sources CSV du projet afin de construire un dataset analytique unique.

## Fonctionnement

Le traitement suit quatre étapes principales :

1. identification des fichiers sources ;
2. lecture et harmonisation des données ;
3. fusion verticale des jeux de données ;
4. contrôle de la provenance puis export du résultat.


## Résultat

Le dataset intégré contient **74 888 observations et 15 colonnes**. Les jeux de données sources sont regroupés dans une même structure et la provenance de chaque observation est conservée.

Le résultat principal est :

```text
data/processed/dataset_raw.csv
```

## Entrée / sortie

**Entrée :** fichiers CSV placés dans `data/raw/`.

**Sortie :** `dataset_raw.csv`, utilisé par le Notebook 02.

