# Stage_Spitzkop_CI_CD_Prediction
ce projet vise a prédire la durée exécution d'un pipeline 


# 💻 Projet de Stage : Analyse et Prédiction des Performances CI/CD (Spitzkop Ingénierie)

## Introduction et Contexte

Ce dépôt contient le code source, les données de maquette et la documentation du projet réalisé dans le cadre de mon stage de Mastére2 en tant que **Chef de Projet IA & Data**.

L'objectif principal était de répondre au défi de l'**efficacité et de la stabilité** des livraisons logicielles, en alignement avec les meilleures pratiques DevOps et les **métriques DORA**.

### Problématique ⚠️

Comment peut-on transformer les **logs bruts des pipelines CI/CD** en un **système de prédiction proactive** capable d'anticiper les durées d'exécution et de diagnostiquer les causes racines des échecs, justifiant ainsi l'optimisation des ressources ?

### Objectifs Clés

1.  **Prédiction ML :** Entraîner un modèle de Régression pour anticiper la **durée d'exécution** d'un pipeline (réduisant le *Lead Time*).
2.  **Diagnostic Proactif :** Fournir une vue claire des risques et des **Taux d'Échec par Dépôt** (CFR) pour cibler les efforts d'optimisation.
3.  **Infrastructure Cloud Native :** Développer le système en utilisant des services AWS pour une architecture robuste et scalable.

---

## 🛠️ Justification des Outils et de l'Architecture

Le choix des outils était essentiel pour créer une solution moderne et industrielle.

| Outil/Technologie | Rôle dans le Projet | Justification du Choix |
| :--- | :--- | :--- |
| **Python / Scikit-learn** | **Modélisation ML** | Simplicité, performance et facilité d'interprétation des coefficients (pour la Régression Linéaire). |
| **AWS SageMaker (Endpoint)** | **Déploiement MLOps** | Plateforme Cloud entièrement gérée, permettant de transformer le modèle en une API HTTP consultable en temps réel, essentielle pour l'intégration future du pipeline CI/CD. |
| **Grafana (Interface BI)** | **Visualisation & Monitoring** | Outil Open Source standard du DevOps et de l'Observabilité. Permet de créer des tableaux de bord dynamiques pour visualiser la performance du modèle et les métriques DORA. |
| **YData-Profiling** | **Analyse Exploratoire (EDA)** | Permet de réaliser un audit automatique de la qualité des données (valeurs manquantes, corrélations) en une seule ligne de code, assurant la rigueur scientifique avant l'entraînement. |
| **Jeu de Données CSV** | **Maquette & Entraînement** | Données simulées (2057 lignes) enrichies pour simuler un taux d'échec réaliste (environ 17%), ce qui est nécessaire pour tester la robustesse du modèle. |

---

## 📊 Contenu du Dépôt et Démarrage Rapide

| Fichier | Description |
| :--- | :--- |
| **`prediction_du_temps.ipynb`** | **Notebook Principal.** Contient l'intégralité du processus : EDA, Encodage (One-Hot Encoding), Séparation Train/Test, Entraînement du modèle de Régression Linéaire, et l'évaluation finale (MAE, R²). |
| **`ci_cd_prediction_mock_2057_errors.csv`** | Le jeu de données factice utilisé pour l'entraînement. |
| **`linear_regression_final_model.joblib`** | Le modèle entraîné, sérialisé et prêt à être déployé (artefact de modèle). |
| **`inference.py`** | Script Python nécessaire pour le déploiement sur SageMaker (définit les fonctions `model_fn`, `input_fn`, `predict_fn`). |

### Comment Exécuter le Code

1.  Cloner ce dépôt (`git clone [URL]`).
2.  Installer les dépendances (`pip install pandas scikit-learn ydata-profiling`).
3.  Ouvrir et exécuter le Notebook **`prediction_du_temps.ipynb`** pour reproduire l'entraînement du modèle.

---

**Auteur :** Christelle Flore KAMGA  
**Rôle :** IA & Data Manager  
**Encadrement :** Spitzkop Ingénierie
