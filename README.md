# Child Malnutrition Risk Predictor

MUAC screening, measuring a child's mid-upper arm circumference is how you identify malnutrition in the field.Working in WFP Project of Benazir Nashunuma Programme gave me the idea as i was working as Information managment officer there, The problem is it requires a trained person to physically measure each child, which creates a real bottleneck in low-coverage areas.

The question I wanted to answer: can household-level survey data predict malnutrition risk well enough to prioritise which children get screened first? This model suggests yes.

---

## Approach

Binary classification: predict whether a child has moderate or severe acute malnutrition based on household and demographic features.

- Model: Random Forest Classifier (after comparing 4 approaches)
- Features: wealth index, food insecurity score, maternal MUAC, distance to health facility, household size, water source, and others
- Performance: AUC-ROC 0.89, F1 0.80

## Data

Synthetic dataset (2,000 records) modelled on Pakistan MICS survey structure. Feature distributions and target prevalence match published MICS figures.

## Tools

Python, Scikit-learn, Pandas, Matplotlib, Seaborn

## How to run

```bash
git clone https://github.com/masoom-khan/child-malnutrition-ml.git
cd child-malnutrition-ml
pip install -r requirements.txt
jupyter notebook malnutrition_ml.ipynb
```

## Key findings

- Top predictors: food insecurity score, wealth index, maternal MUAC
- Random Forest outperformed XGBoost and Logistic Regression on this dataset
- Households with deprivation score >0.6 and >15km from health facility had 2.4x higher malnutrition rate
- Model can reduce required screening visits by targeting highest-risk households first

---

**Muhammad Masoom Khan**  
[Portfolio](https://masoom-khan.github.io) · [LinkedIn](https://www.linkedin.com/in/muhammadmasoomkhan/)
