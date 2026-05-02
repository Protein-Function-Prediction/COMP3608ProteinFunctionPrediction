# Protein Function Prediction using Deep Learning (CNN + Classical ML)

This project focuses on predicting **protein functions (Gene Ontology terms)** from amino acid sequences using a combination of:

- Convolutional Neural Networks (CNN)
- Classical machine learning models (Logistic Regression, Linear SVM)
- Hyperparameter tuning via random search

---

## 📁 Project Structure

models/ # Saved trained and tuned CNN models
data/ # Protein datasets (FASTA, CSV, TSV files)
notebooks/ # Jupyter notebooks for experiments
utils/ # Helper functions (preprocessing, encoding, etc.)


---

##  Datasets

Three datasets are used:

### 1. Protein GO Dataset
- Protein sequences with GO annotations

### 2. CAFA 5 Dataset
- Large-scale benchmark for protein function prediction

### 3. Human Protein Dataset
- Real human protein sequences with functional annotations

---

##  Preprocessing Pipeline

Each dataset undergoes:

1. Loading raw sequences
2. Extracting GO terms
3. Filtering rare labels (frequency thresholding)
4. Converting sequences into k-mer feature vectors
5. Multi-label binarization
6. Train/test split

---

##  Models

### 🔹 CNN Model
- 1D convolution over k-mer features
- Dropout regularization
- Sigmoid activation for multi-label classification
- Binary cross-entropy loss

###  Baseline Models
- Logistic Regression
- Linear SVM

---

##  Hyperparameter Tuning

Random search is used to optimize the CNN:

- Learning rate: `0.01, 0.001, 0.0001`
- Batch size: `32, 64, 128`
- Dropout: `0.2, 0.3, 0.5`
- Epochs: dataset-dependent

Best model is selected using:
- **Micro-average AUROC**

---

##  Evaluation Metrics

- Micro F1 Score
- Macro F1 Score
- AUROC
- AUPR (Area Under Precision-Recall Curve)
- F-max
- Hamming Loss

---

##  How to Run

### Install dependencies
```bash
pip install -r requirements.txt