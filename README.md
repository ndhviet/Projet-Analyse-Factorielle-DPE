
<div align="center">
  <h1>Projet Analyse Factorielle DPE</h1>
  <p><em>Analyse statistique de la consommation énergétique et des émissions de GES des logements</em></p>

  <a href="#"><img src="https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white&style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white&style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Data-Analysis-orange?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Statistics-ANOVA%20%7C%20Chi--Square-blue?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/DPE-Energy%20%26%20GES-green?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square"></a>
  <a href="https://github.com/Hoangviet1810/Projet-Analyse-Factorielle-DPE">
    <img src="https://img.shields.io/badge/GitHub-Repository-black?logo=github&style=flat-square">
  </a>
  <a href="#"><img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square"></a>
  <a href="https://ndhviet.github.io/DPE/">
  <img src="https://img.shields.io/badge/Demo-Live%20Website-brightgreen?style=for-the-badge&logo=googlechrome&logoColor=white">
</a>
</div>
<br>

# Analyse de la consommation énergétique et des émissions de GES des logements
 
## 1. Introduction
 
Étude de la performance énergétique de **1000 logements individuels** construits entre **1900 et 2020** en **Haute-Garonne**, avec un **DPE** réalisé avant **juillet 2021**.
 
**Objectifs :** relier variables quantitatives et qualitatives, mesurer la corrélation consommation / émissions de GES, et évaluer l'impact du type de chauffage (Chi-deux, ANOVA, t-tests).
 
**Outils :** Python (Pandas, NumPy, Matplotlib, Seaborn, Prince) pour les visualisations · R (`FactoMineR`, `factoextra`) pour les tests.
 
📄 [Rapport complet (PDF)](https://ndhviet.github.io/Projet-Analyse-Factorielle-DPE/ProjetDPE.pdf) · 👉 [Voir le site en ligne](https://ndhviet.github.io/DPE/)
 
---
 
## 2. Données
 
| Variable                | Type      | Description                          |
|-------------------------|-----------|--------------------------------------|
| type_logement           | Catégorie | Appartement ou Maison                |
| type_energie_chauffage  | Catégorie | Gaz, Électricité, Autre              |
| classe_conso_energie    | Catégorie | Classe énergétique (A à G)           |
| annee_construction      | Numérique | Année de construction                |
| surface_habitable       | Numérique | Surface habitable (m²)               |
| conso_energie           | Numérique | Consommation (kWh/m²/an)             |
| emission_ges            | Numérique | Émissions de GES (kg CO2/m²)         |
 
---
 
## 3. Résultats
 
| Test | Résultat | p-value | Moyennes |
|------|----------|---------|----------|
| Chi-deux : classe énergétique × chauffage | Dépendance significative | < 0.05 | — |
| ANOVA : conso vs type de logement | F = 11.1, différence significative | 0.000894 | Maison 197.63 · Appartement 176.48 kWh/m²/an |
| ANOVA Welch : GES vs chauffage | F = 219.53, différence significative | < 2.2e-16 | Gaz 33.6 · Électricité 11.1 · Autre 55.5 |
 
**Tests t par paires (émissions GES) :** Gaz vs Électricité (< 2e-16), Gaz vs Autre (0.0053), Électricité vs Autre (1.8e-06) → toutes les paires diffèrent significativement.
 
**Interprétation :**
- Les **maisons** consomment plus que les **appartements** (classes D, E, F plus fréquentes).
- L'**électricité** donne les meilleures performances (classes B, C) et le moins de GES ; le **gaz** est intermédiaire ; **« Autre »** est le plus polluant.
- Corrélations : conso et GES positives ; année de construction négative ; surface peu corrélée.
---
 
## 4. Visualisations
 
Barplots (type de logement, classe par chauffage), ACM, ACP (cercle de corrélation) et boxplots des émissions par type de chauffage.
 
[![Dashboard](images/Dashboard_DPE.png)](https://ndhviet.github.io/Projet-Analyse-Factorielle-DPE/images/dpe_dashboard.html)
 
➡️ Cliquez sur l'image pour ouvrir le dashboard interactif.
