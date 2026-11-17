# Credit Card Default Prediction Using Random Forest

**ES 335 : Machine Learning Course Project**

**Team:** Vipra Madanala (25110351) and Adarasandi Sai Ashwika (25110010)

**[Live Website](https://adarasandiashwika.github.io/credit-card-default-rf/)** | **[GitHub Repository](https://github.com/adarasandiashwika/credit-card-default-rf)**

## 1. Project Overview

This project uses the UCI Default of Credit Card Clients dataset to predict October 2005 payment defaults from customer information and repayment history.

We developed and tuned a Random Forest classifier, compared it with simpler baseline models, and evaluated its performance using precision, recall, F1-score, ROC-AUC, and average precision.

The website presents our methodology, experimental results, error analysis, limitations, and interactive model demonstrations.

## 2. Key Results

The final Random Forest uses 300 trees, a maximum depth of 12, balanced class weights, and a minimum of 10 samples per leaf.

| Metric | Test Score |
|---|---:|
| Accuracy | 0.7924 |
| Precision | 0.5291 |
| Recall | 0.5663 |
| F1-score | 0.5470 |
| ROC-AUC | 0.7774 |
| Average Precision | 0.5535 |

The model achieved a higher validation F1-score than the majority-class, repayment-rule, and decision-tree baselines. Its test performance is also comparable to other publicly available implementations using the same dataset.

Detailed comparisons and findings are available on the project website.

## 3. Individual Contributions

**Vipra Madanala**

Conducted exploratory data analysis, data quality checks, preprocessing, and dataset splitting. Developed the baseline models and trained the Random Forest, experimenting with tree depth, leaf size, class weighting, feature selection at each split, and number of trees. Selected the final model using validation results and examined overfitting and the limitations of model selection using a single validation split. Analyzed how changes in model complexity affected predictive performance.

**Adarasandi Sai Ashwika&#x20;**

Evaluated model performance using classification metrics and confusion matrices, examining the balance between missed defaults and false alarms. Conducted error analysis across repayment-status groups and studied feature importance to identify key predictive variables. Investigated how changing the classification threshold affects precision and recall, and examined the model's difficulty in detecting defaults without recent repayment delays. Developed the interactive website to present and explore the experimental findings.

## 4. Repository Contents

- `es335-ml-project-notebook.ipynb` - Complete machine learning workflow, experiments, and results.
- `index.html`, `style.css`, `ix.css`, `script.js`, `tryit.js` - Website implementation.
- `data/` - Exported results and model data for interactive visualizations.
- `exports/` - Trained model, dataset split IDs, and analysis outputs.
- `requirements.txt` - Python dependencies.

## 5. Dataset and Reproducibility

**Dataset:** [UCI Default of Credit Card Clients — Kaggle copy](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset)

The dataset contains 30,000 customers and 23 input features. We used a stratified 70/15/15 train-validation-test split with `random_state=42`.

### Reproducing the ML analysis

The notebook was developed using **Kaggle Notebooks** and contains Kaggle-specific input and output paths.

1. Download `es335-project-notebook.ipynb` from this repository and import it into Kaggle.
2. Add the linked credit card dataset through Kaggle's **Add Input** option.
3. Run all notebook cells in order.
4. The notebook generates the model results and exports the supporting files to `/kaggle/working/project_exports/`.

The notebook's saved outputs and exported results are also included in the repository for verification.

### Running locally

Clone the repository and install the dependencies:

```bash
git clone https://github.com/adarasandiashwika/credit-card-default-rf
cd credit-card-default-rf
pip install -r requirements.txt
```

The notebook can also be opened locally, but its Kaggle-specific dataset and export paths must be adjusted before running it.

To view the website locally:

```bash
python -m http.server 5500
```

## 6. References

1. Yeh, I. C., & Lien, C. H. (2009). *The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients.* Expert Systems with Applications, 36(2), 2473–2480.
2. Pedregosa et al. (2011). *Scikit-learn: Machine Learning in Python.* JMLR, 12, 2825–2830.

Additional implementation references are linked in the website's comparison section.

## 7. AI-Use Disclosure

We used Claude (Anthropic) and OpenAI for brainstorming the interactive features, debugging the notebook's export code, and writing and testing the website's HTML, CSS and JavaScript. We ran the notebook ourselves and checked the reported numbers against its outputs. We take responsibility for all results.
