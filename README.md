# Mental Health Screening-Support System Using Machine Learning

> **⚠️ IMPORTANT DISCLAIMER**: This is a **research prototype and educational tool only**. It does **not** diagnose, treat, or assess any medical or mental health condition. All predictions are based on survey response patterns from a research dataset. This system is **not** intended for clinical, employment, insurance, or any high-stakes decision-making. If you or someone you know is struggling, please consult a qualified mental health professional.

---

## Project Overview

This project is an educational machine learning application developed as a final-year Computer Science Engineering academic project. It demonstrates how survey-based data can be used to build classification models that identify patterns in responses related to workplace mental health.

**Project Title:** Mental Health Screening-Support System Using Machine Learning Algorithms

**Domain:** Machine Learning · Public Health Research · Human-Computer Interaction

---

## Dataset

This project uses the **OSMI Mental Health in Tech Survey** dataset (or a clearly labeled synthetic version for demonstration when the real dataset is unavailable).

- **Source:** [Open Sourcing Mental Illness (OSMI)](https://osmihelp.org/research)
- **License:** Open for research use (verify current license at source)
- **Target Variable:** Whether a respondent has sought mental health treatment (`treatment`)
- **Records:** ~1,259 responses (real dataset); 500 synthetic records (demo mode)
- **Features:** ~27 survey questions covering workplace policies, support, attitudes

> See `data/README.md` for full dataset documentation.

---

## Project Structure

```
mental/
├── app.py                      # Streamlit web application
├── requirements.txt            # Python dependencies
├── README.md                   # This file
├── .gitignore                  # Git ignore rules
├── .env.example                # Environment variable template
├── data/
│   ├── README.md               # Dataset documentation
│   ├── dataset_template.csv    # Column template for real dataset
│   └── sample_synthetic_data.csv  # Clearly labeled synthetic test data
├── src/
│   ├── __init__.py
│   ├── data_loader.py          # Dataset loading utilities
│   ├── preprocessing.py        # Feature engineering and encoding
│   ├── train_model.py          # Model training pipeline
│   ├── evaluate_model.py       # Evaluation metrics and charts
│   ├── predict.py              # Inference utilities
│   ├── model_utils.py          # Save/load utilities
│   └── ui_components.py        # Reusable Streamlit UI components
├── models/
│   └── README.md               # Model file documentation
├── reports/
│   ├── README.md
│   ├── model_metrics.json      # Machine-readable metrics
│   ├── model_comparison.csv    # Human-readable comparison
│   └── figures/                # Generated charts
├── docs/
│   ├── project_report.md       # Full academic report
│   ├── abstract.md
│   ├── methodology.md
│   ├── data_dictionary.md
│   ├── limitations.md
│   ├── future_scope.md
│   ├── references.md
│   ├── presentation_outline.md
│   ├── viva_questions.md
│   └── flowchart.md            # Mermaid system diagrams
└── tests/
    ├── test_data.py
    ├── test_preprocessing.py
    ├── test_training.py
    └── test_prediction.py
```

---

## Quick Start (Windows PowerShell)

### 1. Prerequisites
- Python 3.10 or higher — download from [python.org](https://www.python.org/downloads/)
- Git (optional, for version control)

### 2. Setup

```powershell
# Navigate to the project directory
cd d:\WORK\HCL\mental

# Create virtual environment
python -m venv venv

# Activate virtual environment
.\venv\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt
```

> **Note:** If PowerShell blocks script execution, run:
> `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

### 3. Train the Models

```powershell
# Train all five ML algorithms (uses synthetic data if real dataset unavailable)
python src/train_model.py
```

This will:
- Load and preprocess the dataset
- Train Logistic Regression, Decision Tree, Random Forest, SVM, and KNN
- Save the best model to `models/`
- Save evaluation metrics to `reports/`
- Generate performance charts to `reports/figures/`

### 4. Launch the Web Application

```powershell
streamlit run app.py
```

The application will open at `http://localhost:8501`

### 5. Run Tests

```powershell
python -m pytest -q
```

---

## Using the Real Dataset

1. Visit [OSMI Survey Data](https://osmihelp.org/research)
2. Download the survey CSV file
3. Place it in `data/` as `mental_health_survey.csv`
4. Re-run `python src/train_model.py`

The system auto-detects the real dataset and switches out of demonstration mode.

---

## Five Machine Learning Algorithms

| Algorithm | Strengths | Weaknesses |
|-----------|-----------|------------|
| Logistic Regression | Interpretable, fast, baseline | Assumes linearity |
| Decision Tree | Highly interpretable, visual | Prone to overfitting |
| Random Forest | Robust, handles noise | Less interpretable |
| Support Vector Machine | Effective in high dimensions | Slow on large datasets |
| K-Nearest Neighbors | Simple, no training phase | Slow inference, sensitive to scale |

---

## Evaluation Metrics

- **Accuracy** — overall correct predictions
- **Macro Precision / Recall / F1** — averages across classes (accounts for imbalance)
- **ROC-AUC** — discrimination ability
- **Confusion Matrix** — per-class performance breakdown
- **Cross-Validation Score** — generalization estimate

---

## Ethical Considerations

- No personal identifiers collected or stored
- User inputs are not persisted or transmitted
- System clearly labeled as a research prototype
- Not suitable for clinical, legal, or employment decisions
- See `docs/limitations.md` for full ethical discussion

---

## Common Errors & Solutions

| Error | Solution |
|-------|---------|
| `ModuleNotFoundError` | Activate venv: `.\venv\Scripts\Activate.ps1` |
| `streamlit: command not found` | Install: `pip install streamlit` |
| `FileNotFoundError` on model | Run training first: `python src/train_model.py` |
| PowerShell execution policy | `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` |
| `PermissionError` on port 8501 | Use: `streamlit run app.py --server.port 8502` |

---

## Academic Context

- **Degree:** B.Tech / B.E. Computer Science Engineering
- **Subject:** Machine Learning / Artificial Intelligence
- **Project Type:** Final Year Major Project
- **Complexity Level:** Intermediate

---

## License & Attribution

- Project code: MIT License (educational use)
- Dataset: OSMI — verify current license at source
- Synthetic data: Generated for software testing only; does not represent real individuals

---

*Built as an educational prototype. Not a medical device or clinical tool.*
