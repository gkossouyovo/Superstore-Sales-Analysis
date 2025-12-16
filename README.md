# Superstore-Sales-Analysis
Analyse de performance commerciale (ETL Python + SQL + DataViz)

---

## 1. Contexte & Objectifs 🎯

**Le Contexte :**
La chaîne de distribution "Superstore" dispose d'un historique de ventes de 4 ans (2014-2018) mais manque de visibilité sur ses leviers de rentabilité. Les données étaient stockées dans des fichiers plats (CSV) non exploités.

**Les Objectifs de la mission :**
* **Centraliser la donnée :** Créer une architecture de base de données (SQL) robuste.
* **Diagnostiquer la performance :** Identifier les produits stars, les régions rentables et les saisonnalités.
* **Automatiser le reporting :** Mettre en place un script Python capable de générer des rapports visuels instantanés à chaque mise à jour des données.

**🛠 Stack Technique :**
* **ETL & Nettoyage :** Python (Pandas)
* **Base de Données :** MySQL (Moteur de stockage et requêtes analytiques)
* **Visualisation :** Python (Seaborn, Matplotlib)
* **Volume de données :** 9 994 transactions analysées.

---

## 2. Méthodologie (Pipeline de Données) ⚙️

Mon approche s'est découpée en 3 phases techniques :

### 🔹 Phase ETL (Extract, Transform, Load)
* Nettoyage des données brutes avec Pandas (gestion des types `float`/`int`, formatage des dates `datetime`).
* Connexion sécurisée à MySQL via `SQLAlchemy`.
* Chargement des données nettoyées dans une table structurée `orders`.

### 🔹 Phase Analytique (SQL)
* Utilisation de requêtes d'agrégation (`GROUP BY`, `SUM`, `ROUND`) pour calculer le Chiffre d'Affaires (CA) et le Profit.
* Classement des performances (`ORDER BY`, `LIMIT`) pour extraire les Tops Produits et Régions.

### 🔹 Phase DataViz (Python)
* Développement d'une fonction d'étiquetage intelligente (formatage automatique en K€ / M€).
* Génération automatique de 4 graphiques clés pour le comité de direction.

---

## 3. Analyse des Résultats & Data Storytelling 📊

Voici les 4 insights majeurs révélés par l'analyse des données :

### 📈 Insight 1 : Une croissance forte mais saisonnière
*(Insère ici ton image : 1_evolution_ventes_pro.png)*

* **Observation :** Le chiffre d'affaires montre une tendance haussière sur 4 ans. On note une saisonnalité marquée avec des pics systématiques en fin d'année (novembre/décembre), suivis d'une chute brutale en janvier/février.
* **Recommandation Business :** Prévoir les stocks et les campagnes marketing dès octobre pour maximiser le pic de fin d'année, et lancer des promotions agressives en janvier pour lisser la baisse.

### 🏆 Insight 2 : La dépendance à un "Produit Star"
*(Insère ici ton image : 2_top_produits_global_pro.png)*

* **Observation :** Le produit *"Canon imageCLASS 2200"* domine largement le classement avec plus de **61.6K €** de CA, soit plus du double du second produit (*Fellowes PB500*, 27.5K €).
* **Risque identifié :** Une trop grande dépendance à une seule référence technique.
* **Recommandation Business :** Diversifier l'offre Premium pour ne pas risquer une chute de CA si le Canon imageCLASS est en rupture de stock.

### 🌍 Insight 3 : Disparité de rentabilité par Région
*(Insère ici ton image : 3_profit_region_pro.png)*

* **Observation :** La région **Ouest (West)** est la locomotive du groupe avec **108.4K €** de profit net. À l'inverse, la région **Centrale** est à la traîne avec seulement **39.7K €**, malgré un volume de ventes correct.
* **Analyse complémentaire (SQL) :** J'ai noté que la catégorie "Meubles" (*Furniture*) dans le Centre a une marge très faible (2.49%), ce qui plomb la rentabilité globale de la zone.
* **Recommandation Business :** Auditer les coûts logistiques et les remises accordées dans la région Centrale pour redresser la marge.

### 🔍 Insight 4 : Stratégies différenciées par zone
*(Insère ici ton image : 4_bonus_top3_region_pro.png)*

* **Observation :** Les produits leaders ne sont pas les mêmes partout.
    * À l'Est et à l'Ouest, le *Canon imageCLASS* est roi.
    * Au Sud, c'est le système de vidéoconférence *Cisco* qui prime (22.6K €).
* **Action :** Adapter les catalogues promotionnels régionaux en fonction de ces préférences locales (Tech au Sud vs Bureautique à l'Est).

---

## 4. Conclusion & Impact ✅

Ce projet a permis de passer d'une gestion "à l'aveugle" basée sur des fichiers Excel dispersés à un **pilotage par la donnée**.

**Ce que j'ai appris / Démontré :**
* Capacité à dialoguer entre **Python** et **SQL**.
* Rigueur dans le **nettoyage des données** (Data Cleaning).
* Sens du **design de l'information** (choix des graphiques, lisibilité des axes, étiquettes intelligentes).

---

### 🔗 Source des données
[Kaggle Superstore Dataset Final](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
