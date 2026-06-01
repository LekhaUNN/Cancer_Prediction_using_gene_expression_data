# 🧬 Cancer Diagnosis with Gene Expression Data

A neural network model that classifies cancer types from RNA-seq gene expression data using TensorFlow/Keras. Achieves **99.58% accuracy** across 5 cancer types.

---

## 📌 Overview

This project uses a feedforward neural network to classify cancer samples into one of five categories based on RNA-sequencing (RNA-seq) gene expression profiles. Each sample contains expression values for 8,429 genes.

**Dataset Source:** [UCI ML Repository – Gene Expression Cancer RNA-Seq](https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq)


## 🎯 Cancer Types Classified

| Label | Cancer Type |
|-------|-------------|
| BRCA  | Breast Invasive Carcinoma |
| KIRC  | Kidney Renal Clear Cell Carcinoma |
| LUAD  | Lung Adenocarcinoma |
| PRAD  | Prostate Adenocarcinoma |
| COAD  | Colon Adenocarcinoma |

## 📊 Dataset Summary

- **Total Samples:** 799
- **Features (Genes):** 8,429
- **Classes:** 5
- **Missing Values:** None

| Cancer Type | Sample Count |
|-------------|-------------|
| BRCA        | 300         |
| KIRC        | 146         |
| LUAD        | 141         |
| PRAD        | 134         |
| COAD        | 78          |

## 🏗️ Model Architecture

```
Input Layer  → 8429 features
Hidden Layer 1 → Dense(40, activation='relu')
Hidden Layer 2 → Dense(30, activation='relu')
Output Layer   → Dense(5,  activation='softmax')

Optimizer : Adam (learning_rate=0.002)
Loss      : Sparse Categorical Crossentropy
Epochs    : 200
Batch Size: 32
```

## ⚙️ Workflow

```
Raw CSV Data
    ↓
Data Exploration & Cleaning
    ↓
Label Encoding (LabelEncoder)
    ↓
Feature Normalization (MinMaxScaler → [0, 1])
    ↓
Train / Validation / Test Split (70 / 21 / 9)
    ↓
Neural Network Training (200 epochs)
    ↓
Evaluation & Metrics
```

## 📈 Results

| Metric    | Score  |
|-----------|--------|
| Accuracy  | 99.58% |
| Precision | 99.59% |
| Recall    | 99.58% |
| F1 Score  | 99.58% |
| Loss      | 0.013  |

The model converges rapidly — training accuracy reaches 100% by epoch 7 and validation accuracy stabilizes at ~99.4% from epoch 2 onwards.


## 🛠️ Requirements

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow keras
```

| Library      | Purpose                        |
|--------------|-------------------------------|
| numpy        | Numerical operations           |
| pandas       | Data loading & manipulation    |
| matplotlib   | Plotting training curves       |
| seaborn      | Gene expression boxplots       |
| scikit-learn | Preprocessing & metrics        |
| tensorflow   | Neural network framework       |
| keras        | High-level model API           |



3. **Download the dataset** from [UCI Repository](https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq) and place the CSV file in the project folder.

4. **Update the file path** in the notebook:
   ```python
   df = pd.read_csv("your-path/Cancer-Prediction-gene-expression-dataset.csv")
   ```

5. **Run the notebook**
   ```bash
   jupyter notebook cancer_diagnosis.ipynb
   ```
## 📁 Project Structure

```
cancer-gene-expression-nn/
│
├── cancer_diagnosis.ipynb     # Main Jupyter notebook
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

## 🔮 Future Improvements

- Add dropout layers to reduce overfitting risk
- Experiment with deeper architectures or CNNs on expression matrices
- Apply PCA or feature selection to reduce 8,429 features
- Try SHAP values to identify most predictive genes
- Add confusion matrix visualization


