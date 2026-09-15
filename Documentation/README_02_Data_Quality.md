# Notebook 02 — Data Quality

## Objectif

Ce notebook réalise l’audit qualité du dataset intégré avant les traitements analytiques.

## Contrôles réalisés

L’audit porte notamment sur :

- la structure et les types de données ;
- les valeurs manquantes ;
- les doublons exacts et les doublons métier ;
- les prix et taux de marge ;
- les périodes disponibles ;
- la couverture historique des EAN ;
- la cohérence de la hiérarchie produit.

## Résultats

L’audit confirme la structure du dataset intégré et met en évidence principalement :

- des valeurs manquantes, notamment sur certaines informations historiques ;
- l’absence de doublons exacts et de doublons métier ;
- une couverture historique variable selon les EAN ;
- une cohérence globale des périodes et de la hiérarchie produit.

Une synthèse d’audit est produite pour documenter ces contrôles.

## Sortie

```text
data/results/data_quality/audit_summary.csv
```