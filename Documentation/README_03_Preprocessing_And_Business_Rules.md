# Notebook 03 — Preprocessing & Business Rules

## Objectif

Ce notebook prépare les données issues de l’audit qualité pour le Feature Engineering et définit la population réellement exploitable.

## Fonctionnement

Deux niveaux de traitement sont séparés :

### Prétraitement technique

- nettoyage des variables textuelles ;
- conservation de l’EAN comme identifiant ;
- conversion des prix et des taux de marge ;
- validation des années et des mois ;
- contrôle final de la structure.

### Critères d’exploitabilité

Une observation est conservée si :

- au moins une mesure de marge de l’année N est disponible ;
- l’EAN est disponible.

## Résultat

Le dataset final est homogénéisé, trié chronologiquement et limité aux observations exploitables. Une synthèse de la population est également produite.

```text
data/processed/dataset_business.csv
data/results/preprocessing/business_summary.csv
```