# Prédiction des prix de l'immobilier en Californie

Projet de machine learning pour prédire le **prix médian des logements** par quartier en Californie, basé sur le dataset du recensement californien de 1990.

## Contenu

```
housing_prediction_clean.ipynb   # Notebook principal
```

## Lancement rapide

```bash
pip install pandas numpy matplotlib scikit-learn
jupyter notebook housing_prediction_clean.ipynb
```

## Structure du notebook

| Section | Description |
|---|---|
| 1. Imports | Toutes les dépendances |
| 2. Chargement | Téléchargement et lecture du dataset |
| 3. Exploration | Statistiques descriptives, cartes, corrélations |
| 4. Feature Engineering | Création de nouvelles variables |
| 5. Nettoyage | Valeurs manquantes, encodage catégoriel |
| 6. Échantillonnage | Split train / validation / test (70/15/15) |
| 7. Modèles | Entraînement et comparaison de 4 modèles |
| 8. Évaluation finale | Résultats sur le jeu de test |
| 9. Conclusion | Synthèse et pistes d'amélioration |

## Modèles comparés

| Modèle | R² | RMSE |
|---|---|---|
| Régression linéaire | ~0.63 | ~70 000  |
| Arbre de décision | ~0.62 | ~71 000 |
| Random Forest | ~0.81 | ~50 000 |
| **Gradient Boosting** | **~0.83** | **~48 000** |

Le **Gradient Boosting** est retenu comme modèle final.

## Variables clés

- `median_income` — le revenu médian a l'importance la plus élevée sur le prix (0.54)
- -`population_per_household` — le nombre moyen de personnes par foyer est le 2ème facteur le plus influent (0.13)
- `ocean_proximity` — la proximité avec l'océan possède également une incidence significative sur le prix final (0.09)

## Limites

- Données de **1990** : ne reflète pas le marché actuel
- Prix plafonnés à **500 001 $** dans le dataset original
