# Housing Price Prediction – Analyse et Modélisation de Données Immobilières

## Description du projet

Ce projet consiste à analyser et modéliser un dataset immobilier afin de prédire le **prix des maisons** en fonction de leurs caractéristiques.  
Le dataset contient des informations sur la surface, le nombre de chambres, de salles de bain, les équipements disponibles et le statut de mobilier.

**Objectifs :**

- Nettoyer et préparer le dataset  
- Effectuer une exploration des données (EDA)  
- Créer de nouvelles features pertinentes (Feature Engineering)  
- Construire un modèle de régression linéaire pour prédire le prix  
- Évaluer la performance du modèle et visualiser les résultats  

---

## Étapes du projet

### 1️⃣ Exploration des données (EDA)
- Inspection des données avec `head()`, `info()` et `describe()`  
- Identification des colonnes avec valeurs manquantes  
- Visualisation de la distribution du prix et corrélations initiales  

### 2️⃣ Nettoyage des données
- Remplacement des valeurs manquantes (numériques → médiane, catégorielles → "Missing")  
- Encodage des colonnes catégorielles `yes/no` → 1/0  
- One-Hot Encoding pour `furnishingstatus`  

### 3️⃣ Feature Engineering
- Création de nouvelles colonnes :  
  - `total_rooms` = bedrooms + bathrooms  
  - `luxury_score` = score basé sur équipements et caractéristiques  
  - `area_per_room` = surface / total_rooms  
  - `is_furnished` = 1 si furnished ou semi-furnished, 0 sinon  
- Identification des features les plus importantes :  
  - `luxury_score`, `area`, `bathrooms`, `total_rooms`  

### 4️⃣ Analyse de corrélation
- Heatmap pour visualiser les relations entre les features et le prix  
- Les nouvelles features montrent un impact significatif sur le prix  

### 5️⃣ Modélisation
- Régression linéaire avec `scikit-learn`  
- Séparation en train/test (80% / 20%)  
- Standardisation des features  

**Résultats :**  
- RMSE : 1,435,757 → erreur moyenne acceptable compte tenu des valeurs en millions  
- R² : 0.592 → 59% de variance expliquée par le modèle  

**Coefficients :**  
- `luxury_score` : 748,819  
- `area` : 550,678  
- `bathrooms` : 489,006  
- `total_rooms` : 176,347  

### 6️⃣ Visualisation
- Scatter plot : valeurs réelles vs prix prédit  
- Histogramme des erreurs : distribution centrée autour de 0  
- Barplot des coefficients : importance des features  

### 7️⃣ Insights clés
- Les maisons avec un `luxury_score` élevé, une grande `area` et plusieurs `bathrooms` se vendent plus cher  
- Le Feature Engineering a permis de créer des variables plus explicatives pour le modèle  
- Le modèle simple capture déjà les tendances principales mais peut être amélioré  

### 8️⃣ Perspectives et amélioration
- Ajouter des features supplémentaires (année de construction, localisation, proximité des commodités)  
- Tester des modèles plus avancés : Random Forest, Gradient Boosting, XGBoost  
- Faire des transformations log ou polynomial sur certaines variables pour réduire la variance  
- Identifier et traiter les outliers  

---

## Technologies utilisées
- Python 3  
- Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn
