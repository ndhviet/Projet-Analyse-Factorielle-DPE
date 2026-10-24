
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


# Projet-Analyse-Factorielle-DPE

# Analyse de la consommation énergétique et des émissions de GES des logements



<div align="center">
  <h1>Projet Analyse Factorielle DPE</h1>
  <p><em>Analyse statistique de la consommation énergétique et des émissions de GES des logements</em></p>

  <a href="#"><img src="https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white&style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white&style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Statistics-ANOVA%20%7C%20Chi--Square-blue?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square"></a>
  <a href="https://github.com/Hoangviet1810/Projet-Analyse-Factorielle-DPE">
    <img src="https://img.shields.io/badge/GitHub-Repository-black?logo=github&style=flat-square">
  </a>
  <a href="https://ndhviet.github.io/DPE/">
    <img src="https://img.shields.io/badge/Demo-Live%20Website-brightgreen?style=for-the-badge&logo=googlechrome&logoColor=white">
  </a>
</div>
<br>

## 1. Introduction

L'étude porte sur la performance énergétique de **1000 logements individuels** construits entre **1900 et 2020** en **Haute-Garonne**, pour lesquels un **DPE** a été réalisé avant **juillet 2021**.

**Objectifs :**
- Étudier les relations entre variables quantitatives et qualitatives
- Identifier les corrélations entre consommation d'énergie et émissions de GES
- Visualiser les profils de logements et l'impact du type de chauffage
- Réaliser des tests statistiques (Chi-deux, ANOVA, t-tests)

📄 [Rapport complet (PDF)](ProjetDPE.pdf) · 👉 [Voir le site en ligne](https://hoangviet1810.github.io/DPE/)

Deux codes accompagnent ce projet : un fichier **Python** pour les visualisations et un fichier **R** pour les tests statistiques.

---

## 2. Installation

```sh
git clone https://github.com/Hoangviet1810/Projet-Analyse-Factorielle-DPE.git
cd Projet-Analyse-Factorielle-DPE
```

---

## 3. Logiciels utilisés

- **Python** (visualisations) : Pandas, NumPy, Matplotlib, Seaborn, Prince
- **R** (tests statistiques) : `FactoMineR`, `factoextra`

---

## 4. Structure des données

| Variable                | Type      | Description                                    |
|-------------------------|-----------|------------------------------------------------|
| type_logement           | Catégorie | Appartement ou Maison                          |
| type_energie_chauffage  | Catégorie | Gaz, Électricité, Autre                        |
| classe_conso_energie    | Catégorie | Classe énergétique (A à G)                     |
| annee_construction      | Numérique | Année de construction                          |
| surface_habitable       | Numérique | Surface habitable (m²)                         |
| conso_energie           | Numérique | Consommation énergétique (kWh/m²/an)           |
| emission_ges            | Numérique | Émissions de GES (kg CO2/m²)                   |

---

## 5. Analyses réalisées

- **Statistiques descriptives** : moyenne, médiane, variance, coefficient de variation ; barplots pour les variables catégorielles
- **Visualisations** : histogrammes, boxplots, cercle de corrélation (ACP), MCA plots (ACM)
- **Corrélations** : positive entre *conso_energie* et *emission_ges* ; négative entre *annee_construction* et consommation/émissions ; *surface_habitable* peu corrélée aux autres variables
- **Tests statistiques** :
  1. **Chi-deux** : dépendance entre *classe_conso_energie* et *type_energie_chauffage* (p-value < 0.05)
  2. **ANOVA** : *conso_energie* selon *type_logement*
  3. **ANOVA / Welch** : *emission_ges* selon *type_energie_chauffage*
  4. **Tests t par paires** : comparaison des émissions entre types de chauffage

---

## 6. Résultats

### 6.1 Test ANOVA

| Test | H0 | Statistique | p-value | Conclusion | Moyenne(s) |
|------|----|-------------|---------|------------|------------|
| Conso énergie vs type_logement | Pas de différence entre Maison et Appartement | F = 11.1 | 0.000894 | H0 rejetée → différence significative | Maison: 197.63<br>Appartement: 176.48 kWh/m²/an |
| Émissions GES vs type_energie_chauffage (Welch) | Moyennes égales | F = 219.53 | < 2.2e-16 | H0 rejetée → émissions dépendent du chauffage | Gaz: 33.6<br>Électricité: 11.1<br>Autre: 55.5 |

### 6.2 Tests t de Student par paires

| Comparaison | p-value | Conclusion |
|-------------|---------|------------|
| Gaz vs Électricité | < 2e-16 | Extrêmement significative |
| Gaz vs Autre | 0.0053 | Significative |
| Électricité vs Autre | 1.8e-06 | Extrêmement significative |

### 6.3 Interprétation

- Les **maisons** consomment plus que les **appartements** et se retrouvent plus souvent dans les classes D, E, F.
- Les logements chauffés à l'**électricité** ont de meilleures performances (classes B, C) et émettent le moins de GES.
- Les logements chauffés au **gaz** consomment et émettent davantage ; la catégorie **« Autre »** est la plus polluante.
- L'ACM met en évidence les profils de logements et leur association avec les classes énergétiques et les types de chauffage.

---

## 7. Visualisations

1. **Distribution du type de logement** : barplot appartements / maisons
2. **Classe énergétique par type de chauffage** : barplot groupé (A à G)
3. **ACM** : carte factorielle des variables catégorielles
4. **ACP** : cercle de corrélation (surface, consommation, GES)
5. **Tests et émissions** : tableaux (ANOVA, t-tests) et boxplots par type de chauffage

### Dashboard interactif

[![Dashboard](images/Dashboard_DPE.png)](https://ndhviet.github.io/Projet-Analyse-Factorielle-DPE/images/dpe_dashboard.html)

➡️ Cliquez sur l'image pour ouvrir le dashboard interactif.
