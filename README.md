# Détection et contextualisation des comportements atypiques

Projet de fin d’études réalisé dans le cadre du **Master 2 AI & Big Data**.

L’objectif est de détecter, contextualiser et prioriser des comportements économiquement atypiques pouvant nécessiter une investigation dans le cadre du pilotage de la **Profitability**.

L’approche combine des **règles métier**, des **comparaisons statistiques robustes**, du **Machine Learning non supervisé** et une restitution dans **Power BI**.

---

## Pipeline

```text
Données sources
      │
      ▼
01 — Data Integration
      │
      ▼
02 — Data Quality
      │
      ▼
03 — Preprocessing & Business Rules
      │
      ▼
04 — Feature Engineering
      │
      ▼
05 — Anomaly Detection
      │
      ▼
06 — Power BI
      │
      ▼
Analyse et investigation métier
```

## Organisation du projet

```text
project/
├── README.md
├── notebooks/
│   ├── 01_Data_Integration.ipynb
│   ├── 02_Data_Quality.ipynb
│   ├── 03_Preprocessing_And_Business_Rules.ipynb
│   ├── 04_Feature_Engineering.ipynb
│   ├── 05_Anomaly_Detection.ipynb
│   └── 06_PowerBI.ipynb
├── data/
│   ├── raw/
│   ├── processed/
│   └── results/
├── figures/
├── powerbi/
├── documentation/
│   ├── README_01_Data_Integration.md
│   ├── README_02_Data_Quality.md
│   ├── README_03_Preprocessing_And_Business_Rules.md
│   ├── README_04_Feature_Engineering.md
│   ├── README_05_Anomaly_Detection.md
│   └── README_06_PowerBI.md
└── requirements.txt
```

Les données professionnelles et confidentielles de l'entreprise ne sont pas destinées à être publiées.

---

## Description des étapes

### 01 — Data Integration
Intégration des différentes sources CSV dans un dataset analytique unique, avec conservation de la provenance des observations.

### 02 — Data Quality
Audit de la structure, des valeurs manquantes, des doublons, des variables numériques et de la cohérence temporelle et hiérarchique.

### 03 — Preprocessing & Business Rules
Préparation technique des données et définition de la population exploitable avant les étapes analytiques. Les valeurs économiquement atypiques sont conservées pour la détection.

### 04 — Feature Engineering
Construction d’une représentation comportementale combinant situation courante, évolutions, comparaison familiale et historique propre à l’EAN.

### 05 — Anomaly Detection
Détection hybride combinant règles métier, contexte familial, contexte temporel et Machine Learning non supervisé. Isolation Forest et LOF sont comparés sur une validation synthétique.

### 06 — Power BI
Contrôle et préparation de la table finale destinée à la restitution décisionnelle dans Power BI.

---

## Résultats principaux

Sur la population réelle analysée :

- **68 324 observations** ;
- **1 663 signaux issus des règles métier** ;
- **3 417 observations dans le Top 5 % ML** ;
- **222 doubles signaux** règle métier + ML ;
- **4 858 observations dans le périmètre d’attention**, soit **7,11 %** de la population.

La priorisation finale distingue les observations **Critiques**, **À surveiller** et **Normales**. Le périmètre d’attention est destiné à faciliter l’investigation et ne constitue pas un taux d’anomalies avérées.

---

## Machine Learning

Deux méthodes non supervisées ont été comparées :

- **Isolation Forest** ;
- **Local Outlier Factor (LOF)**.

La comparaison est réalisée sur une validation synthétique contrôlée à partir de comportements perturbés selon plusieurs scénarios et niveaux d’amplitude. L’**Average Precision** est utilisée comme métrique principale, complétée par la ROC-AUC et une analyse de stabilité des classements.

La configuration retenue pour l’application aux données réelles est **LOF avec 50 voisins**, avec mise à l’échelle robuste des variables utilisées par LOF.

---

## Exécution

Les notebooks doivent être exécutés dans l’ordre :

```text
01 → 02 → 03 → 04 → 05 → 06
```

Les dépendances Python principales sont :

```text
pandas
numpy
scikit-learn
scipy
matplotlib
seaborn
jupyter
```

Installation :

```bash
pip install -r requirements.txt
```

---

## Technologies

Python · Pandas · NumPy · Scikit-learn · SciPy · Matplotlib · Seaborn · Jupyter Notebook · Power BI

---

## Limites

Les données réelles ne disposent pas d’un étiquetage exhaustif permettant de distinguer automatiquement les anomalies confirmées des comportements simplement atypiques. La validation du Machine Learning repose donc sur des anomalies synthétiques contrôlées.

---

## Perspectives

- élargissement du périmètre d’analyse ;
- enrichissement des données et des attributs produits ;
- comparaison avec d’autres méthodes de détection ;
- suivi temporel des scores d’atypicité ;
- validation progressive des signaux par les équipes métier.

---

