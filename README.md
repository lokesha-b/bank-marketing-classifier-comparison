# Practical Application III: Comparing Classifiers

## Overview

This project compares the performance of four classification models on a bank marketing dataset to predict whether a client will subscribe to a term deposit.

**Models Compared:**
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Decision Trees
- Support Vector Machines (SVM)

## Business Problem

A Portuguese banking institution wants to predict whether a client will subscribe to a term deposit based on their demographic, financial, and campaign-related information. The goal is to optimize marketing campaign targeting, reduce costs, and improve conversion rates.

## Dataset

The dataset comes from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bank+marketing) and contains:
- **41,188 observations** from multiple telephone marketing campaigns
- **20 input features** (client data, campaign info, economic indicators)
- **1 target variable** (term deposit subscription: yes/no)
- Data collected from May 2008 to November 2010

### Key Features:
| Category | Features |
|----------|----------|
| Client Information | age, job, marital, education, default, housing, loan |
| Campaign Information | contact, month, day_of_week, duration, campaign |
| Previous Campaign | pdays, previous, poutcome |
| Economic Indicators | emp.var.rate, cons.price.idx, cons.conf.idx, euribor3m, nr.employed |

## Key Findings

### 1. Class Imbalance
The dataset is highly imbalanced with approximately **89% of clients not subscribing** to term deposits. This affects model performance and requires careful evaluation.

### 2. Model Performance Comparison

| Model | Train Time | Train Accuracy | Test Accuracy |
|-------|------------|----------------|---------------|
| Logistic Regression | ~1s | ~90% | ~90% |
| KNN | ~1s | ~91% | ~89% |
| Decision Tree | ~1s | ~99% | ~89% |
| SVM | ~30s | ~90% | ~90% |

### 3. Training Efficiency
- **Logistic Regression** and **Decision Trees** trained quickly
- **SVM** had significantly longer training times

### 4. Overfitting
Decision Trees showed signs of overfitting (high training accuracy, lower test accuracy) which improved after hyperparameter tuning.

## Recommendations

1. **Model Selection**: Logistic Regression is recommended due to its balance of accuracy, interpretability, and training speed.

2. **Feature Engineering**: The 'duration' feature was removed for realistic predictions since it's only known after the call.

3. **Handling Imbalance**: Use techniques like SMOTE, class weights, or threshold adjustment to improve minority class prediction.

4. **Business Application**: Focus on identifying potential subscribers to optimize marketing resources.

## Project Structure

```
Assignment_17_GitHub/
├── README.md                 # Project overview and findings
├── requirements.txt          # Python dependencies
├── .gitignore               # Git ignore file
├── notebooks/
│   └── prompt_III.ipynb     # Main Jupyter Notebook with analysis
└── data/
    ├── bank-additional-full.csv    # Dataset
    └── bank-additional-names.txt   # Feature descriptions
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/your-username/comparing-classifiers.git
cd comparing-classifiers
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. Open the Jupyter Notebook:
```bash
jupyter notebook notebooks/prompt_III.ipynb
```

2. Run all cells to reproduce the analysis

## Dependencies

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Author

UC Berkeley Program Assignment

## License

This project is for educational purposes.

## Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bank+marketing) for the dataset
- [Moro et al., 2014](https://www.sciencedirect.com/science/article/pii/S016792361400061X) for the dataset paper