## Homework Results

| Question | Answer |
|---|---|
| Q1 — Installed MLflow version | 3.17.0 |
| Q2 — Number of preprocessing output files | 4 |
| Q3 — min_samples_split | 2 |
| Q4 — Artifact storage parameter | default-artifact-root |
| Q5 — Best validation RMSE | 5.335 |
| Q6 — Best test RMSE | 5.567 |

Registered model: `nyc-green-taxi-duration`, version `1`.

## Dataset

NYC Green Taxi Trip Records for 2023:

- January: model training.
- February: hyperparameter tuning and validation.
- March: selection among the five best candidates, as required by Q6.

## Experiment Tracking

MLflow uses SQLite (`mlflow.db`) for metadata and a local `artifacts`
directory for model artifacts.

The tracking server runs with
`--default-artifact-root ./artifacts --no-serve-artifacts`.

## Repository Contents

- `preprocess_data.py`: prepares datasets and saves the fitted DictVectorizer.
- `train.py`: trains a Random Forest model with MLflow autologging.
- `hpo.py`: tunes hyperparameters and manually logs parameters and validation RMSE.
- `register_model.py`: evaluates the top five candidates and registers the model
  with the lowest test RMSE.
- `requirements.txt`: primary dependencies.
- `requirements-lock.txt`: pinned versions of all installed dependencies.

Downloaded data, generated artifacts, the virtual environment, and the local
MLflow database are excluded from Git.