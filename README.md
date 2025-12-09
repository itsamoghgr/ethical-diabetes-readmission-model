# Ethical Predictive Modeling Pipeline

An end-to-end machine learning pipeline for predicting diabetes hospital readmission with strong emphasis on **privacy**, **fairness**, **transparency**, and **accountability**.

## 📋 Project Overview

This project demonstrates ethical AI principles applied to healthcare, specifically predicting 30-day hospital readmission for diabetic patients. The implementation addresses key ethical concerns in AI deployment while maintaining model performance.

## 🗂️ Dataset

- **Source**: UCI Diabetes 130-US Hospitals (1999-2008)
- **Size**: 101,766 patient encounters
- **Features**: 50 attributes including demographics, clinical measurements, and medications
- **Target**: Hospital readmission (NO, <30 days, >30 days)

## 🎯 Key Features

### 1. Privacy Protection (Differential Privacy)
- Implemented Laplace mechanism with configurable privacy budget (ε)
- Demonstrated privacy-accuracy tradeoff across multiple ε values
- Recommended ε = 1.0 for balanced privacy and utility

### 2. Fairness & Bias Analysis
- **Demographic profiling**: Identified representation skew across race, gender, and age groups
- **Bias diagnostics**: Disparate Impact Ratio (0.975), Statistical Parity Difference
- **Mitigation strategies**: Sample reweighting, class balancing, stratified sampling

### 3. Model Explainability
- **LIME**: Local interpretable explanations for individual predictions
- **Counterfactuals**: "What-if" scenarios showing minimal changes to flip predictions
- **Feature importance**: Transparent ranking of predictive factors

### 4. Fairness Evaluation
- Subgroup performance analysis across demographics
- Accuracy disparity: 0.0757 (within acceptable 0.10 threshold)
- Gender parity maintained across model predictions

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy lime
```

### Running the Notebook
```bash
jupyter notebook ethics.ipynb
```

Run all cells sequentially or select "Cell → Run All" in the Jupyter menu.

## 📊 Results

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| **Logistic Regression** | **0.6237** | **0.6185** | **0.4988** | **0.5523** | **0.6587** |
| Random Forest | 0.6039 | 0.5870 | 0.5012 | 0.5407 | 0.6366 |
| Gradient Boosting | 0.6296 | 0.6412 | 0.4626 | 0.5375 | 0.6734 |

**Best Model**: Logistic Regression (selected for balanced F1-score and fairness)

### Fairness Metrics
- **Disparate Impact (Race)**: 0.975 ✓ Acceptable [0.8-1.25]
- **Disparate Impact (Gender)**: 0.962 ✓ Acceptable
- **Accuracy Disparity**: 0.0757 ✓ Below 0.10 threshold

## 🛡️ Ethical Principles

### Privacy
- Differential privacy ensures individual patient data cannot be reconstructed
- Privacy budget tracking for all aggregate statistics

### Fairness
- Quantitative bias testing across protected attributes
- Balanced performance across demographic groups
- Mitigation strategies implemented and documented

### Transparency
- Model decisions explained using LIME
- Counterfactual examples provide actionable insights
- Feature importance clearly documented

### Accountability
- Comprehensive deployment guidelines
- Monthly fairness audit protocols
- Human-in-the-loop decision framework
- Performance benchmarks with automatic alerts

## 📁 Project Structure

```
ethical-diabetes-readmission-model/
├── ethics.ipynb           # Main notebook with complete pipeline
├── dataset/
│   ├── diabetic_data.csv  # Patient encounter data
│   └── IDS_mapping.csv    # Code mappings for features
└── README.md              # This file
```

## 📈 Use Cases

- **Clinical Decision Support**: Identify high-risk patients for targeted interventions
- **Resource Allocation**: Optimize hospital bed management and follow-up care
- **Patient Education**: Personalized risk communication with explanations
- **Quality Improvement**: Systematic analysis of readmission patterns

## ⚠️ Limitations

- Historical data (1999-2008) may not reflect current medical practices
- Representation bias: Caucasian patients 75%+, minorities underrepresented
- Binary outcome simplification (3-class readmission collapsed to 2-class)
- Missing data in some features (weight, payer_code)
- Geographic limitation: US hospitals only

## Acknowledgments

- UCI Machine Learning Repository for the diabetes dataset
- LIME library developers for explainability tools
- Scikit-learn community for machine learning frameworks

---

**Assignment**: Developing an Ethical Predictive Modelling Pipeline  
**Focus**: Privacy, Fairness, Transparency, and Accountability in Healthcare AI 
