# Voice Gender Recognition - kNN Optimization & GridSearchCV 🎙️🤖

## Project Overview
This repository presents a specialized study on gender classification through acoustic voice features using the **k-Nearest Neighbors (kNN)** algorithm. This project is a direct evolution of my previous work in Undergraduate Research, shifting the focus from linear modeling to neighborhood-based classification and **exhaustive hyperparameter tuning**.

The main goal here is to demonstrate how systematic optimization can transform a baseline classifier into a high-performance, robust model.

---

## 🔗 Connection to Previous Research
This project leverages the data cleaning pipeline established in my [Logistic Regression Project](INSERT_LINK_HERE). By reusing the same **Outlier Removal (IQR)** and **Multicollinearity Filtering** protocols, I am able to compare different algorithms under the same data conditions, ensuring a scientifically sound comparison.

---

## 🛠️ Technical Workflow

### 1. Baseline Establishment
Before any optimization, a "Vanilla" kNN model was trained on raw data to provide a reference point for improvement.

### 2. Data Refinement
Application of the established pipeline:
* **Feature Selection:** Removing redundant variables with correlation > 0.90.
* **Normalization:** Scaling features using `StandardScaler` (essential for distance-based algorithms like kNN).
* **Noise Reduction:** IQR filtering to handle recording inconsistencies.

### 3. Hyperparameter Tuning (GridSearchCV)
Instead of manual tuning, I implemented `GridSearchCV` to explore:
* **n_neighbors ($k$):** Range from 1 to 50.
* **Weights:** Uniform vs. Distance-based.
* **Distance Metrics:** Euclidean ($p=2$) vs. Manhattan ($p=1$).
* **Cross-Validation:** 7-fold CV to prevent overfitting and ensure generalization.

---

## 📈 Performance & Metrics
The model's final evaluation was performed on a **completely unseen test set** (10% of the original data), utilizing:
* **Accuracy, Precision, Recall, f1-score.**
* **Confusion Matrix.**
* **ROC Curve & AUC Score:** To measure the model's diagnostic ability across different thresholds.

---

## 🚀 Key Takeaways
The transition from the baseline to the optimized model showed a significant leap in stability. The use of **GridSearchCV** was instrumental in finding the "sweet spot" for $k$, proving that proper tuning is just as important as the choice of algorithm itself.

---

## 💻 Tech Stack
* **Language:** Python
* **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn
* **Environment:** Google Colab / Jupyter Notebook

---

## 📂 How to Use

This project was designed to be fully reproducible directly in your browser via **Google Colab**.

1. **Open the Notebook:** Click the badge below to open the project:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1B1jTweHxE9nHBAAnTmJs1v9X-_k0KBnF?authuser=1#scrollTo=vx8ueD-IDovf)
2. **Upload the Dataset:** Make sure to upload the `voice.csv` dataset to the session storage in Colab (left sidebar) before running the cells.
3. **Run All:** Go to the menu **Runtime > Run all** to execute the entire pipeline, from baseline analysis to GridSearchCV optimization.

*Note: The notebook handles all library imports (Scikit-learn, Pandas, etc.), so no local installation is required.*
---
