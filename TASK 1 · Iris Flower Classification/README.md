# Data Science Task 1 — Iris Flower Classification

**Oasis Infobyte SIP | Track: Data Science | Task 1**
**Intern:** Himanshee

## Objective
Train a machine learning classification model to identify the species of an iris flower
(*Setosa*, *Versicolor*, or *Virginica*) from four physical measurements: sepal length,
sepal width, petal length, and petal width.

## Dataset
The classic **Iris dataset** (150 samples, 3 balanced classes, 4 numeric features), loaded
directly from `sklearn.datasets.load_iris()` — no external download needed.

## Tech Stack
- Python 3
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

## Project Structure
```
DataScience-Task1-IrisClassification/
├── Iris_Flower_Classification.ipynb   # Main notebook (fully executed, with outputs)
├── iris_pipeline.py                   # Equivalent standalone Python script
├── README.md
├── 01_pairplot.png                    # EDA screenshot
├── 02_boxplots.png                    # EDA screenshot
├── 03_correlation_heatmap.png         # EDA screenshot
└── 04_confusion_matrices.png          # Model evaluation screenshot
```

## What the notebook does
1. **Load the data** directly from scikit-learn.
2. **EDA** — shape, dtypes, null check, descriptive statistics.
3. **Visualisations** — pairplot, box plots per feature, correlation heatmap.
4. **Feature selection discussion** — petal length & petal width are identified as the
   most discriminative features; sepal width is the weakest.
5. **Train/test split** — 80/20, stratified by species.
6. **Model training** — 4 classifiers trained: Logistic Regression, K-Nearest Neighbours,
   Decision Tree, Random Forest.
7. **Evaluation** — accuracy, confusion matrix, and full classification report
   (precision/recall/F1) for every model.
8. **Conclusion** — best model identified with justification.

## Results

| Model                | Accuracy |
|-----------------------|----------|
| K-Nearest Neighbours  | **100%** |
| Logistic Regression   | 96.7%    |
| Decision Tree         | 93.3%    |
| Random Forest         | 90.0%    |

**Best model: K-Nearest Neighbours (k=5)** — the Iris classes form tight, well-separated
clusters in feature space (especially on petal measurements), which is exactly the kind of
data KNN handles best. See the notebook's conclusion section for the full reasoning and
caveats (small test set size).

## How to Run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Iris_Flower_Classification.ipynb
```
or run the plain script:
```bash
python iris_pipeline.py
```

## Author
Himanshee — B.Tech CSE, Amity University Noida
Oasis Infobyte AICTE Summer Internship Program
