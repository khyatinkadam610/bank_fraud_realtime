# Fraud model training & inference

Quick starter for training a fraud-detection model on `input/Base.csv`.

Usage (Windows `cmd.exe`):

1. Create a virtual environment and install dependencies:

```
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

2. Train model (auto-detects common target column names):

```
python scripts\train_model.py --input input\Base.csv --outdir models
```

Optional: pass `--target YourLabelColumn` if auto-detection fails.

3. Run inference on new data:

```
python scripts\inference.py --model models\best_model.joblib --input input\Base.csv --output preds.csv
```

Files added:
- `scripts/train_model.py` : training script with preprocessing pipeline and LightGBM
- `scripts/inference.py` : simple inference utility
- `requirements.txt` : Python dependencies

Next suggestions:
- Run the training script and share the produced `models/metrics.json` if you want further tuning or a notebook conversion.
- I can also add logging, experiments tracking (MLflow), or a notebook demo — tell me which you prefer.
