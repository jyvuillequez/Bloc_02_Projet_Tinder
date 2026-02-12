# Bloc 02 – Projet Tinder

Analyse de données de speed-dating pour comprendre les facteurs qui influencent l’intérêt mutuel entre participants et améliorer les recommandations de matching.

Projet réalisé dans le cadre de la certification **RNCP Niveau 6 – Concepteur Développeur en Science des données (Jedha Bootcamp)**.

## 1. Contexte & enjeux

- **Problématique métier :** Tinder cherche à mieux comprendre les mécanismes d’attraction lors des premières interactions afin d’améliorer les recommandations et l’expérience utilisateur
- **Décideurs cibles :** Équipes Produit, Marketing

## 2. Objectifs du projet

- Comprendre quels facteurs qui influencent la décision individuelle d’accepter un second rendez-vous
- Identifier l’écart entre préférences déclarées et comportements réels

## 3. Compétences mobilisées

- Analyse exploratoire de données (EDA)
- Préparation et sélection raisonnée des variables
- Visualisation de données (Plotly Express)
- Interprétation critique des résultats
- Formulation de recommandations orientées produit / business

## 4. Données

- **Source :**  
  Speed Dating Experiment Dataset (expériences menées entre 2002 et 2004)
- **Périmètre :**  
  - Chaque ligne correspond à une interaction entre deux participants  
  - Plusieurs vagues d’événements avec des protocoles légèrement différents
- **Variables clés :**
  - `dec` : décision individuelle d’accepter un second rendez-vous (0 / 1)
  - `match` : accord mutuel (non utilisé dans le cadre de cette étude)
  - `attr`, `fun`, `intel`, `sinc`, `amb`, `shar` : évaluations données pendant le date
  - Variables de contexte : `gender`, `order`, `samerace`, `wave`

## 5. Méthodologie

### 1. Préparation des données
- Sélection  d’un sous-ensemble de variables directement liées au processus de décision
- Exclusion des valeurs manquantes sur les évaluations clés
- Non-mélange des préférences déclarées collectées sur des échelles différentes
  (100 points vs 1–10) afin d’éviter les biais d’interprétation

### 2. Analyse exploratoire
- Statistiques descriptives comparant décisions positives et négatives
- Visualisations (boxplots, courbes de taux de décision, segmentations)
- Analyse des effets contextuels (ordre des dates, similarité perçue)

### 3. Restitution
- Insights structurés
- Interprétation (biais, limites, ...)

## 6. Résultats & recommandations

### Résultats clés
- Les décisions positives sont principalement associées à des signaux immédiats
  (attractivité perçue et fun) plutôt qu’à des traits plus abstraits ou déclaratifs
- Les préférences déclarées expliquent mal les décisions réelles
- Les intérêts partagés ont un impact plus fort que certaines similarités démographiques
- Le contexte (ordre des dates, fatigue décisionnelle) influence la probabilité de dire “yes”

### Limites & pistes d’amélioration
- Données issues d’un contexte expérimental et historique (absence de données "fraîches" et optimisée)
- Interactions très courtes

## 7. Installations des librairies Python
```text
python -m pip install -r requirements.txt
```

## 8. Organisation du projet

```text
.
├─ data/
│  ├─ raw/        # données brutes
│  └─ outputs/    # exports intermédiaires ou résultats
├─ notebooks/     # notebooks Jupyter (EDA, visualisations)
├─ src/           # scripts Python utilitaires (si besoin)
└─ presentation/  # supports de restitution (slides, images)
