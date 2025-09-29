# Fantasy Hockey Classification Project

This project reframes your fantasy hockey app data into **classification** problems:

1. **Skaters:** Predict whether a skater will end a season with **≥ 20 goals** (`is_20_goals`).
2. **Goalies:** Predict whether a goalie will post a **save% above the seasonal median** (`is_above_median_sv`).
   
Both are supervised binary classification tasks suitable for algorithms you’ve covered (Logistic Regression, KNN, SVM, Random Forest).

---

## Quickstart (VS Code + Jupyter)

1. **Open the folder** in VS Code:  
   `File → Open Folder… → select: fantasy_hockey_classification_project`

2. **Create/activate a virtual env (optional but recommended):**
   ```bash
   python -m venv .venv
   # Windows PowerShell
   .venv\Scripts\Activate.ps1
   # macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter in VS Code** (top-right “Run All” in the Notebook, or open the Command Palette → “Jupyter: Create New Blank Notebook” and open ours).

5. **Open the starter notebook:**  
   `notebooks/01_classification_starter.ipynb`

6. **Run cells top-to-bottom**. The notebook will:
   - Load the 3 years of player & goalie CSVs (referencing the copies you uploaded).
   - **Clean**: standardize dtypes, handle missing values, drop duplicates, harmonize team/position strings.
   - **Engineer targets**: `is_20_goals` (skaters), `is_above_median_sv` (goalies).
   - **Model**: train/test split, pipelines for Logistic Regression, KNN, SVM, Random Forest.
   - **Evaluate**: Accuracy, Precision, Recall, F1, ROC AUC + confusion matrices.
   - **Explain**: basic feature importances/coefficients.
   - **Visualize**: ROC curves and a few EDA charts.

---

## Starting a GitHub Repo (step-by-step)

> **Prereq:** Create an empty repo on GitHub first (no README/Gitignore/Licenses added), e.g. `fantasy_hockey_classification_project`.

From the **project root** (same folder as this README):

```bash
git init
git add .
git commit -m "Initial commit: classification project scaffold + starter notebook"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/fantasy_hockey_classification_project.git
git push -u origin main
```

If you get an error like *“failed to push some refs”* you may need to:
```bash
git pull --rebase origin main
git push -u origin main
```

---

## What to Write About (Portfolio-Friendly)

- **Problem definition:** why 20 goals for skaters / above-median save% for goalies?
- **Data sources & cleaning:** duplicates removed, nulls handled, categorical standards (e.g., `ATL` vs `WPG`).
- **Model choices:** which algorithms and why; pros/cons; hyperparameter notes.
- **Evaluation:** compare metrics; discuss tradeoffs (precision vs recall); show confusion matrices.
- **Insights:** which features matter most (e.g., shots, TOI, PP time); hockey interpretation.
- **Limitations & Next Steps:** class imbalance, injuries, teammate effects, deployment ideas.

---

## Project Structure

```
fantasy_hockey_classification_project/
├─ notebooks/
│  └─ 01_classification_starter.ipynb
├─ src/
│  └─ utils.py
├─ figures/              # charts exported here
├─ reports/              # any write-ups you export
├─ data/                 # keep empty or add README; raw data lives outside git
├─ requirements.txt
├─ .gitignore
└─ README.md
```

> Note: The notebook reads the CSVs you already uploaded from `/mnt/data/...`. For portability, copy those into `data/` later and update paths.
