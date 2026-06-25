# Practical Data Modeling and Machine Learning with Python
## From Data Preparation to Model Evaluation and Optimization

### Recommended Project Structure
\index{project structure}

A consistent directory layout makes it easy to navigate a project, share it with colleagues, and automate its execution. The following structure works well for data modeling projects of any size:

```
data_model/
├── data/
│   ├── raw/       # original, immutable source data
│   └── processed/ # cleaned and feature-engineered data
├── notebooks/
│   ├── 1-introduction.ipynb
│   ├── 3-data-preparation.ipynb
│   └── 4-probability-distributions.ipynb
├── src/              # reusable code modules if any
│   ├── __init__.p
│   ├── features.py   # feature engineering functions
│   ├── models.py     # model training and evaluation
│   └── visualize.py  # reusable plotting functions
├── figures/          # all saved plots go here
├── models/           # serialized model artifacts (.pkl, .joblib)
├── reports/          # final reports and summaries
├── requirements.txt  # pinned dependencies
├── pyproject.toml    # uv project configuration
├── uv.lock           # exact versions of all dependencies by uv
├── README.md         # project description and instructions
└── config.py         # paths, constants, hyperparameters
```

A few principles behind this structure:

- **Raw data is sacred.** The `data/raw/` directory is read-only. All transformations happen in code, so every step of data preparation is auditable and re-runnable.
- **Notebooks are for exploration; `src/` is for production.** Keep reusable logic in Python modules under `src/`. Import these into notebooks rather than duplicating code across notebooks.
- **Figures are generated, not manually saved.** Every plot is produced by a script that saves to `figures/`. If the data changes, re-run the script.

