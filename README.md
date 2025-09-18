# 🏢 Seattle Building Energy Consumption Prediction

Un projet de machine learning pour prédire la consommation énergétique et les émissions de GES des bâtiments de Seattle basé sur les données du programme de benchmarking énergétique de la ville.

## 📋 Contexte du Projet

Ce projet analyse les données du programme de benchmarking énergétique de Seattle pour développer des modèles prédictifs de consommation énergétique. Le dataset contient des informations détaillées sur plus de 3000 bâtiments de Seattle, incluant leurs caractéristiques physiques, leur usage, et leur performance énergétique.

### Objectifs Globaux du Système

-   **Prédiction énergétique** : Développer des modèles ML pour prédire la consommation énergétique des bâtiments
-   **Analyse des facteurs** : Identifier les caractéristiques des bâtiments qui influencent le plus la consommation
-   **Comparaison de modèles** : Évaluer plusieurs algorithmes (Linear Regression, SVR, Random Forest) pour déterminer le plus performant
-   **Optimisation** : Améliorer les performances du meilleur modèle via l'optimisation des hyperparamètres

## 🗂️ Structure du Projet

```
├── assets/                                    # Données et fichiers de ressources
│   ├── 2016_Building_Energy_Benchmarking.csv # Dataset original
│   ├── building_consumption_cleaned.csv      # Données nettoyées
│   └── ...                                   # Autres versions des données
├── notebooks/                                # Notebooks Jupyter d'analyse
│   ├── 1. EDA.ipynb                         # Analyse exploratoire
│   ├── 2. Feature Engineering.ipynb         # Ingénierie des features
│   ├── 3. Préparation des features.ipynb    # Préparation finale des données
│   ├── 4. Comparaison des différents modèles.ipynb # Comparaison de modèles
│   └── 5. Optimisation du modèle.ipynb      # Optimisation des hyperparamètres
├── src/                                      # Code source Python (si applicable)
├── config.py                                # Configuration (variable cible, etc.)
├── requirements.txt                          # Dépendances Python
└── README.md                                # Documentation du projet
```

## 🎯 Variables Cibles

Le projet explore deux variables cibles principales :

-   **`SiteEnergyUseWN(kBtu)`** : Consommation énergétique du site (normalisée météo)
-   **`TotalGHGEmissions`** : Émissions totales de gaz à effet de serre

_Variable actuellement configurée_ : `TotalGHGEmissions` (voir `config.py`)

## 📊 Dataset

**Source** : Seattle Building Energy Benchmarking Program 2016

-   **Taille** : ~3000+ bâtiments
-   **Features** : Caractéristiques des bâtiments (surface, âge, usage, etc.)
-   **Cible** : Consommation énergétique / Émissions GES

### Principales caractéristiques analysées :

-   Surface du bâtiment (`PropertyGFABuilding`)
-   Année de construction (`YearBuilt`)
-   Type d'usage (`PrimaryPropertyType`)
-   Score ENERGY STAR (`ENERGYSTARScore`)
-   Intensité énergétique (`SiteEnergyUseIntensity`)

## � Méthodologie

### 1. Analyse Exploratoire (EDA)

-   Distribution des variables
-   Corrélations entre features
-   Détection des valeurs aberrantes
-   Analyse des données manquantes

### 2. Feature Engineering

-   Nettoyage des données
-   Traitement des valeurs manquantes
-   Encodage des variables catégorielles
-   Normalisation des features numériques

### 3. Modélisation

**Modèles comparés :**

-   **Linear Regression** : Modèle de référence linéaire
-   **SVR (Support Vector Regressor)** : Modèle non-linéaire avec kernel RBF
-   **Random Forest** : Modèle d'ensemble basé sur les arbres

**Évaluation :**

-   Validation croisée 5-folds
-   Métriques : R², MAE, RMSE
-   Analyse du surapprentissage

### 4. Optimisation

-   Grid Search pour l'optimisation des hyperparamètres
-   Validation sur données de test
-   Analyse de l'importance des features

## ⚙️ Installation et Usage

### Prérequis

```bash
Python 3.8+
Jupyter Notebook
```

### Installation

```bash
# Cloner le repository
git clone https://github.com/XavierCoulon/OC_P3_Seattle_Buildings_Consumption.git
cd OC_P3_Seattle_Buildings_Consumption

# Installer les dépendances
pip install -r requirements.txt

# Lancer Jupyter
jupyter notebook
```

### Utilisation

1. **Commencer par l'EDA** : Ouvrir `1. EDA.ipynb` pour explorer les données
2. **Feature Engineering** : Suivre les notebooks 2 et 3 pour la préparation
3. **Modélisation** : Utiliser le notebook 4 pour comparer les modèles
4. **Optimisation** : Notebook 5 pour améliorer le meilleur modèle

## 📈 Résultats Principaux

### Comparaison des Modèles

| Modèle            | R² Test | MAE Test | RMSE Test |
| ----------------- | ------- | -------- | --------- |
| Linear Regression | 0.XXX   | XXX      | XXX       |
| SVR               | 0.XXX   | XXX      | XXX       |
| Random Forest     | 0.XXX   | XXX      | XXX       |

_Note : Résultats à compléter après exécution complète_

### Insights Clés

-   **Meilleur modèle** : Random Forest (généralement le plus performant)
-   **Features importantes** : Surface du bâtiment, score ENERGY STAR, intensité énergétique
-   **Performance** : R² > 0.8 attendu sur les données de test

## 🛠️ Technologies Utilisées

-   **Python 3.8+** : Langage principal
-   **Pandas** : Manipulation des données
-   **Scikit-learn** : Machine Learning
-   **NumPy** : Calculs numériques
-   **Matplotlib/Seaborn** : Visualisations
-   **Jupyter** : Environnement de développement

## 📝 Configuration

Le fichier `config.py` permet de configurer facilement la variable cible :

```python
# Changer la variable cible
TARGET = "SiteEnergyUseWN(kBtu)"  # ou "TotalGHGEmissions"
```

## 🤝 Contribution

Ce projet fait partie du parcours OpenClassrooms AI Engineer.
Pour contribuer :

1. Fork le projet
2. Créer une branche feature
3. Commit les changements
4. Push sur la branche
5. Créer une Pull Request

## 📄 Licence

Projet éducatif dans le cadre du parcours OpenClassrooms AI Engineer.

## 📞 Contact

**Xavier Coulon** - Étudiant AI Engineer

-   GitHub : [@XavierCoulon](https://github.com/XavierCoulon)

---

_Projet réalisé dans le cadre du Projet 3 - Parcours AI Engineering OpenClassrooms_
