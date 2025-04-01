# Credit Scoring with Reject Inference

This project develops a **credit risk scoring model** using **logistic regression** and **scorecard methodology**, incorporating **reject inference** to improve prediction accuracy for new applicants.

## 📊 Objective

To build a robust model that estimates the probability of default (`y`) for credit card applicants, and uses it to decide whether to approve or deny credit to new applicants. The model accounts for **selection bias** by including rejected applicants through an
**inference mechanism**.

## 🔁 Workflow Overview

1. **Data Preparation**
   - Load data from `DatosPractica_Scoring.xlsx`
   - Drop derived or redundant variables to avoid multicollinearity
   - Handle missing values and filter invalid observations

2. **EDA (Exploratory Data Analysis)**
   - Analyze variable distributions, correlations, and missing values
   - Separate variables into numerical and categorical

3. **Initial Modeling (Accepted Clients Only)**
   - Select variables based on IV (Information Value)
   - Apply optimal binning (`BinningProcess`)
   - Train logistic regression model
   - Score and validate using test set and AUC-ROC

4. **Reject Inference**
   - Use the initial model to predict `y` for previously rejected clients
   - Assign class labels (`0` or `1`) based on a probability threshold
   - Merge accepted and inferred rejected applicants

5. **Final Model**
   - Re-train logistic regression with inferred labels
   - Generate updated scorecard
   - Apply final model to new applicants (IDs 1286–1319)

## 📁 Files

- `DatosPractica_Scoring.xlsx` – input dataset

## 🧪 Key Tools

- Python 3.9+
- `scikit-learn`
- `scorecardpy` or equivalent binning tools
- `matplotlib` / `seaborn` for visualizations

## ✅ Output

- Probabilities of default (`prob_default`)
- Credit approval decisions (`y` = 0 or 1)
- Visuals: AUC-ROC, score distributions by class

## 📌 Notes

- Point of decision (`score threshold`) is based on the average predicted probability.
- Reject inference is handled via **classification-based method**.
- Model performance is evaluated on both training and test sets, as well as on rejected applicants and new data.


---

📬 For any questions or extensions, feel free to open an issue or reach out!

