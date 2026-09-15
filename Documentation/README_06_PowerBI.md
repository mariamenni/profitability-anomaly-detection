# Notebook 06 — Power BI

## Objectif

Ce notebook constitue la dernière étape du pipeline. Il prépare le dataset final destiné à la restitution dans Power BI.

Il ne réalise **aucune nouvelle détection** : les résultats proviennent du Notebook 05.

## Fonctionnement

Le notebook :

1. charge les résultats de la détection ;
2. harmonise les informations temporelles nécessaires au reporting ;
3. vérifie les variables indispensables ;
4. contrôle les identifiants et la structure ;
5. vérifie les signaux et les priorités ;
6. contrôle la population finale ;
7. exporte le dataset destiné à Power BI ;


## Résultat

La table finale conserve les informations nécessaires à l’analyse métier : dimensions produit et période, données économiques, contexte d’analyse et résultats de détection.

Le dataset est destiné à servir de source au reporting Power BI.

## Sortie

```text
data/results/anomaly_detection/anomaly_detection_powerbi.csv
```

## Contrôles finaux

Le notebook vérifie notamment :

- la présence des champs nécessaires ;
- la cohérence des identifiants ;
- la présence des scores et rangs ML ;
- la cohérence des signaux ;
- la répartition des priorités ;
- la cohérence de la population finale ;
- l’existence et la lisibilité du fichier exporté.

## Utilisation

Le fichier final peut ensuite être chargé dans Power BI afin de permettre une analyse progressive des observations, depuis une vision globale jusqu’au détail d’un produit ou d’une période.

