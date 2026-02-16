# Analyse des Prix Immobiliers : Du Modèle Linéaire à la Régularisation

##  Présentation du Projet
L'objectif est d'analyser les facteurs influençant le prix de vente de 150 maisons (données 2015-2023) en utilisant une panoplie d'outils économétriques, allant de la régression linéaire classique aux méthodes de machine learning (Ridge/Lasso).

##  Étapes de l'Analyse

### 1. Statistiques Descriptives & Analyse Préliminaire
- Calcul des moments (moyenne, écart-type, skewness, kurtosis pour le prix).
- Visualisation (histogrammes, boxplots) et détection de besoin de transformations logarithmiques.
- Matrice de corrélation et heatmap pour identifier les relations fortes.

### 2. Modélisation Linéaire (MCO)
- **Régression simple :** Impact de la surface sur le prix.
- **Régression multiple :** Inclusion de toutes les variables et interprétation des impacts marginaux.
- **Formes fonctionnelles :** Comparaison des modèles Log-Log et Semi-Log.

### 3. Diagnostics & Tests
- **Multicolinéarité :** Calcul des VIF (Variance Inflation Factor).
- **Inférence :** Tests de significativité (t-tests, F-test) et test de Chow pour la stabilité structurelle (impact du COVID).
- **Hétéroscédasticité & Autocorrélation :** Tests de détection et corrections (écarts-types robustes de Newey-West, WLS).

### 4. Endogénéité & Variables Instrumentales (IV)
- Discussion sur l'endogénéité potentielle de la variable `Qualite_ecole`.
- Utilisation de `Distance_universite` comme instrument.
- Estimation par **Double Moindre Carré (2SLS)** et test de validité des instruments.

### 5. Méthodes de Régularisation
- Standardisation des données.
- Implémentation de **Ridge** et **Lasso**.
- Optimisation du paramètre $\lambda$ par **validation croisée (10-fold)**.
- Comparaison des performances (RMSE) sur échantillon de test (split 80/20).

### 6. Prévisions
- Prédiction ponctuelle pour une maison type (ex: $120~m^{2}$, 3 chambres, centre-ville).
- Calcul de l'intervalle de confiance à 95% et discussion sur la fiabilité du modèle.
