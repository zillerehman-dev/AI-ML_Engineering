# Seaborn for AI/ML — A Practical Notebook Series

Two Jupyter notebooks covering the Seaborn visualisation library from fundamentals
through to full ML/EDA workflows, model evaluation, and deep learning training curves.
Written for people who already know Python and are building Data Science / ML skills.

Every section explains what a plot is, why it exists, when you'd reach for it in a real
ML project, and how to read its output correctly — not just the syntax.

## Contents

**Part 1 — `Seaborn_Mastery_Part1_Fundamentals_to_Regression.ipynb`**
- Seaborn fundamentals, architecture, figure-level vs axes-level functions
- Working with Seaborn's built-in datasets correctly
- Core parameters shared across the whole library
- Relational plots (scatter, line, relplot)
- Distribution plots (histogram, KDE, ECDF, rugplot, displot)
- Categorical plots (count, bar, box, violin, strip, swarm, point, catplot)
- Regression visualisation (regplot, lmplot) and its limits

**Part 2 — `Seaborn_Mastery_Part2_Matrix_to_Projects.ipynb`**
- Matrix plots (heatmap, clustermap), including confusion matrices
- Pairwise relationships (pairplot, PairGrid), FacetGrid, joint plots
- Styling and colour systems (reference)
- The statistics behind Seaborn, in plain language
- Seaborn + Pandas / NumPy / Matplotlib integration
- A complete step-by-step EDA workflow (Titanic)
- Seaborn before model training, and for model evaluation (confusion matrices,
  precision/recall/F1, actual-vs-predicted, residuals)
- Feature engineering guidance, deep learning training-curve visualisation
- Common mistakes, best practices, mini projects, interview prep, and a cheat sheet

Both notebooks were executed end-to-end before publishing — every cell runs and every
plot renders as shown.

## Requirements

```
pip install seaborn pandas matplotlib scikit-learn statsmodels
```

## Note on scope

The styling/theme/palette configuration functions (Part 2, sections 12–13) are presented
as reference tables rather than repeated full explanations, since they are simple
one-line configuration calls — a table is more useful there than restating the same
structure dozens of times. Every plot type that matters for real ML work keeps full
depth: what it is, why it exists, when to use it, and how to read it correctly.
