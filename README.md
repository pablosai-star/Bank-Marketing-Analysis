# Bank Marketing Analysis

Analyse exploratoire et modèle prédictif sur les données de campagnes
marketing téléphoniques d'une banque portugaise (2008–2010).

# Objectif

Identifier les profils clients les plus susceptibles de souscrire
à un dépôt à terme, et construire un modèle de classification binaire
pour optimiser les futures campagnes.

# Dataset

- Source : [UCI Machine Learning Repository — Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing)
- Volume : 41 188 clients, 20 variables
- Cible : variable `y` — souscription oui/no (déséquilibre 89%/11%)

# Stack

- Python : Pandas, Matplotlib, Seaborn
- Machine Learning : Scikit-learn (Logistic Regression, Random Forest)
- Environnement : Jupyter Notebook, VS Code

# 📁 Structure du repo

├── Marketing_Banking_campaigns.ipynb  # Notebook principal
├── bank-additional-full.csv           # Dataset complet
├── target_distribution.png            # Distribution variable cible
├── souscription_par_job.png           # Taux par profession
├── souscription_par_mois.png          # Taux par mois
├── souscription_par_age.png           # Taux par tranche d'âge
├── duration_souscription.png          # Durée d'appel vs souscription
└── README.md

#📊 Key Insights EDA

- Déséquilibre de classes : 89% non-souscripteurs vs 11% souscripteurs
- Profils les plus réceptifs : seniors 65+ (47%) et étudiants 18-25 (21%)
- Meilleures périodes : mars (50%), décembre et septembre (~45%)
- Pire mois : mai (6.5%) malgré le plus grand volume de contacts
- Durée d'appel : les souscripteurs restent 2.5x plus longtemps en ligne

# Modèle Prédictif

- Algorithme retenu : Logistic Regression (solver=saga, class_weight=balanced)
- Recall classe yes : 0.65 — détecte 65% des vrais souscripteurs
- Random Forest testé mais moins performant sur le recall (0.29)
- Choix métier : recall privilégié sur precision — mieux vaut contacter
  un client de trop que rater un souscripteur potentiel
