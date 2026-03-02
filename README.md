# End-to-End ML Lifecycle Project

An end-to-end ML pipeline project built for learning, using student data to predict math scores and serving predictions via a Flask web app.

## What’s Included
- Data ingestion from `notebooks/data/stud.csv`
- Data transformation with preprocessing + feature scaling
- Model training with multiple regressors and model selection
- Serialized artifacts for the trained model and preprocessor
- Flask UI for interactive predictions

## Project Structure
- `app.py` Flask app entrypoint
- `src/components/` ingestion, transformation, training
- `src/pipeline/` train and predict pipelines
- `artifact/` generated training artifacts (train/test splits, model, preprocessor)
- `templates/` Flask HTML templates

## Setup
1. Create and activate a virtual environment.
2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Train the Model
Run the training pipeline to create artifacts in `artifact/`:
```bash
python -m src.pipeline.train_pipeline
```

## Run the Web App
Start the Flask server:
```bash
python app.py
```
Then open the app at `http://localhost:5000`.

## Notes
- The training data is expected at `notebooks/data/stud.csv`.
- The prediction pipeline loads `artifact/model.pkl` and `artifact/preprocessor.pkl`.
- If you retrain, the artifacts will be overwritten with the latest versions.

## Next Steps
- Containerize the app with Docker.
- Deploy to the cloud (e.g., AWS).
