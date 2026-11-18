# Instructions pour les agents IA qui contribuent à ce repo

Ce repo est un projet universitaire ML-2026 (ESILV), groupe de 3 étudiants.
Tout contributeur humain ou IA doit respecter les règles ci-dessous.

## Règles impératives

1. **Jalons** : après chaque commit ou push significatif, ajouter une ligne dans `jalons.md` au format :
   `- AAAA-MM-JJ | Auteur | Description courte de la modification`

2. **Gouvernance IA** : le dossier `ai_governance/` contient trois fichiers obligatoires :
   - `CONTRIBUTIONS.md` : matrice de répartition des tâches entre les 3 membres
   - `PROMPT_LOG.md` : 4 à 6 interactions critiques avec l'IA (min. 1 par étudiant)
   - `AI_AUDIT.md` : au moins 4 erreurs concrètes de l'IA détectées et corrigées (min. 1 par étudiant)

3. **Pas de fuite de données** : tout preprocessing (scaler, imputation, SMOTE) doit être fit sur le train set uniquement, puis appliqué au test. Toute violation doit être documentée dans `AI_AUDIT.md`.

4. **Reproductibilité** : graines fixées partout (`random_state=42` par défaut), versions épinglées dans `requirements.txt`, chemins relatifs uniquement.

5. **Style de commit** : messages courts et factuels en anglais. Exemples valides :
   - `feat: add baseline logistic regression`
   - `fix: correct data leakage in scaler`
   - `docs: update jalons.md`

6. **Ne jamais commiter** : clés d'API, tokens, mots de passe, données brutes volumineuses (utiliser `.gitignore` et `data/.gitkeep`).

7. **Rapport** : `report/Report_Group_XX.pdf` doit être en anglais. +1 ou +2 pts si fait en LaTeX.

## Structure attendue du repo

Cointegration-Arbitrage/
├── README.md
├── jalons.md
├── agent.md
├── requirements.txt
├── .gitignore
├── notebooks/ # EDA, experiments
├── src/ # code modulaire
├── report/ # rapport final PDF
├── ai_governance/ # CONTRIBUTIONS.md, PROMPT_LOG.md, AI_AUDIT.md
└── data/ # .gitkeep uniquement, données ignorées


## Rappel du sujet

Prédire l'évolution d'un stock à partir des stocks corrélés du même secteur (approche pairs trading / corrélation inter-stocks). Dataset public à confirmer (Yahoo Finance via yfinance, ou Kaggle S&P 500).