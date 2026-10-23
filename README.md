# Bike Sharing Project

A one-day project with real data from Capital Bikeshare, the bike sharing system of Washington, D.C. You predict how many bikes are rented in an hour from the time of day, the calendar and the weather: explore the data, compare a linear model, a decision tree and ensemble methods (random forest, gradient boosting, voting and stacking), and find out where the best model makes its biggest mistakes.

## Learning Objectives

By the end of this project, you should be able to:

- Extract calendar features (hour, weekday, working day) from a timestamp, and find the columns that leak the target before you train any model.
- Train a random forest, gradient boosting models (XGBoost, CatBoost) and a voting or stacking ensemble for a regression target, tune them with cross-validation, and explain why they beat a linear model and a single tree on this data.
- Compare every model with a mean and a rule-based baseline in one table of training and test scores, and use the residuals of the best model to find and explain where it makes its biggest mistakes.

## Learning Path

| File | Description |
|---|---|
| [**01 - Bike Sharing Project**](01_bike_sharing_project.ipynb) | The project: the business problem, the data description and the task in eight steps. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Assets**](assets/) | The diagram of the project's steps shown in the notebook, with its Mermaid source in `assets/diagrams/`. |
| [**Data**](data/) | `bike_sharing.csv`: one row per hour from October 2024 to September 2026, with the rentals, the weather and the public holidays. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it including the `< >` brackets with your own value. For example, `cd <repo-name>` becomes `cd my-bike-sharing-project`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

> [!CAUTION]
> **macOS users:** XGBoost needs the OpenMP runtime. If `import xgboost` fails with an error about `libomp`, install it with `brew install libomp`.

---

### 5. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**scikit-learn: Ensembles**](https://scikit-learn.org/stable/modules/ensemble.html): Random forests, gradient boosting, voting and stacking.
- [**XGBoost: Python API**](https://xgboost.readthedocs.io/en/stable/python/python_api.html): `XGBRegressor` and its hyperparameters.
- [**XGBoost: Notes on parameter tuning**](https://xgboost.readthedocs.io/en/stable/tutorials/param_tuning.html): Which hyperparameters control overfitting, and which the speed of learning.
- [**CatBoost: Python API**](https://catboost.ai/docs/en/concepts/python-reference_catboostregressor): `CatBoostRegressor`, its defaults and the `cat_features` parameter.
- [**scikit-learn: Tuning the hyperparameters of an estimator**](https://scikit-learn.org/stable/modules/grid_search.html): Grid search, randomized search and how they use cross-validation.
- [**Capital Bikeshare system data**](https://capitalbikeshare.com/system-data): The trip records the rentals were counted from, under the [Capital Bikeshare Data License Agreement](https://capitalbikeshare.com/data-license-agreement).
- [**Open-Meteo Historical Weather API**](https://open-meteo.com/en/docs/historical-weather-api): The source of the weather data, licensed CC BY 4.0.
- [**Fanaee-T and Gama (2014), Event labeling combining ensemble detectors and background knowledge**](https://doi.org/10.1007/s13748-013-0040-3): The paper behind the classic UCI Bike Sharing dataset, which first paired Capital Bikeshare rentals with weather, for 2011 and 2012.
