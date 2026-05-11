# COMP 3608 – Protein Function Prediction

A machine learning pipeline that classifies protein function using biophysical descriptors. Each notebook focuses on one dataset and runs all three models — Logistic Regression, SVM (RBF), and a 1-D CNN — on that dataset before moving to the next.

---

## Repository Structure

```
COMP3608ProteinFunctionPrediction/
│
├── .gitignore
├── README.md
├── requirements.txt
│
├── dataset1.ipynb      # All models on df1 – 5-class protein functional type
├── dataset2.ipynb      # All models on df2 – 20-class GO cellular component
└── dataset3.ipynb      # All models on df3 – 10-class GO molecular function
```

---

## Datasets

| Notebook | Dataset | Classes | Task |
|----------|---------|---------|------|
| `dataset1.ipynb` | Bioinformatics Simulated (df1) | 5 | Broad protein functional type (Enzyme, Receptor, Structural, Transporter, Other) |
| `dataset2.ipynb` | UniProt GO Annotations (df2) | 20 | GO cellular component terms |
| `dataset3.ipynb` | Human Proteome + GO Annotations (df3) | 10 | GO molecular function terms |

---

## How to Run

Each notebook is **self-contained** — it downloads its own dataset, preprocesses it, and runs all three models (LR → SVM → CNN) in sequence. Run the notebooks in any order, independently of each other.

---

## Setup

All notebooks run on **Google Colab**. To use GPU (recommended for CNN):
`Runtime → Change runtime type → T4 GPU`

### Install dependencies

Each notebook installs its own dependencies at the top. To install locally:

```bash
pip install -r requirements.txt
```

### Kaggle Authentication

Datasets are downloaded via `kagglehub`. On Colab, either:
- Upload your `kaggle.json` API token, or
- Run `kagglehub.login()` and follow the prompts
