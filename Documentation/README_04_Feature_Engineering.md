# Notebook 04 — Feature Engineering

## Objectif

Ce notebook transforme les données préparées en une représentation quantitative du comportement économique des produits.

## Fonctionnement

La représentation repose sur quatre dimensions :

1. **situation économique courante** ;
2. **évolutions entre N et N-1** ;
3. **comparaison avec les EAN comparables de la même famille et période** ;
4. **comparaison avec l’historique propre de l’EAN**.

Pour les comparaisons familiales et temporelles, des statistiques robustes sont utilisées afin de limiter l’influence des valeurs extrêmes.

La comparaison familiale est réalisée dans un contexte comparable de période et de hiérarchie produit. Un minimum de données valides est requis pour produire une référence robuste.


## Résultat

Le notebook produit un dataset enrichi contenant les variables économiques, les indicateurs d’évolution et les informations de contexte nécessaires à la détection.

La représentation utilisée par les modèles comprend **14 variables comportementales**.

```text
data/processed/dataset_features.csv
```

Les variables de contexte familial et temporel restent également disponibles pour l’interprétation des résultats.
