🧠 Breast Cancer Classification using Feature Engineering & Model Comparison
📌 Overview

This project focuses on building an accurate and interpretable classification model for breast cancer diagnosis using the Breast Cancer Wisconsin dataset. The goal is not only high performance but also understanding the underlying data structure and feature importance.

🎯 Objectives
Perform in-depth Exploratory Data Analysis (EDA)
Identify key predictive features
Apply feature engineering to reduce dimensionality
Compare multiple machine learning models
Build a simple, interpretable, high-performing model
🔍 Exploratory Data Analysis (EDA)
Key Findings:
Dataset shows moderate class imbalance (~63% Benign, ~37% Malignant)
Strong separation observed in:
Size features → radius, perimeter, area
Shape features → concavity, concave points, compactness
Weak separation in:
texture, symmetry, fractal dimension
Multicollinearity:
High correlation among:
radius ≈ perimeter ≈ area
Feature grouping identified:
Size cluster
Shape cluster
⚙️ Feature Engineering

To reduce redundancy and improve interpretability:

size_score
Captures tumor size
shape_score
Captures structural irregularity
Insight:

A 2-feature representation preserves most of the predictive power.

🤖 Models Used
Logistic Regression
Linear Discriminant Analysis (LDA)
Quadratic Discriminant Analysis (QDA)
K-Nearest Neighbors (KNN)
📊 Model Performance
Model	Accuracy	Malignant Recall	Key Observation
Logistic Regression	99%	0.98	Best overall
KNN	95%	0.86	Sensitive to local overlap
QDA	93%	0.83	Unnecessary flexibility
LDA	90%	0.74	Strong assumptions fail
🧠 Key Insights
Dataset is highly separable
Size is the dominant feature
Shape adds refinement
Texture-based features add noise
Simple models outperform complex ones
🔬 Final Model

Using only:

['size_score', 'shape_score']

Achieved:

99% accuracy
Only 1 misclassification
Coefficient Insight:
Size has significantly higher impact than shape
Confirms EDA findings
📈 Decision Boundary
Clear linear separation
Minimal overlap between classes
Confirms suitability of linear models
⚠️ Important Consideration
False negatives (missed malignant cases) are critical
Model evaluation focused beyond accuracy:
Recall
F1-score
🚀 Conclusion

The project demonstrates that breast cancer classification can be effectively solved using a low-dimensional, interpretable feature space. Tumor size and shape alone capture the majority of the predictive signal, making Logistic Regression the optimal choice.

💡 Key Takeaway

Simplicity beats complexity when the data is inherently structured.

📂 Tech Stack
Python
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn
📌 Future Improvements
Cross-validation & robustness checks
Threshold tuning for medical sensitivity
ROC-AUC optimization
Deployment-ready pipeline
👤 Author

https://www.linkedin.com/in/shorya-bisht-a20144349/

