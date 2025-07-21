Biodegradability Prediction Using Naïve Bayes and Logistic Regression
Author
Muzhaffar Ma’ruf Ibrahim
Department of Automatic Control & Systems Engineering, University of Sheffield

🧠 Abstract
This project builds and evaluates binary classification models to determine whether a chemical is biodegradable or non-biodegradable, using a QSAR dataset containing 1,055 chemical samples and 41 molecular descriptors. Two methods are implemented in MATLAB:

Naïve Bayes Classifier

Logistic Regression

Key results:

Logistic Regression achieves 90% accuracy and AUC = 0.84

Naïve Bayes achieves 58% accuracy and AUC = 0.72

PCA used for dimensionality reduction

5-fold cross-validation ensures robust performance metrics

🧾 Problem Statement
The classification of chemical substances based on biodegradability is vital for environmental regulation (e.g., under EU REACH framework). This project aims to:

Predict biodegradability using QSAR data

Compare Naïve Bayes vs. Logistic Regression

Emphasize model interpretability, scalability, and statistical validation

⚙️ Data Processing
Steps implemented in MATLAB:

Feature/Label Separation: X_QSAR (41 features), Y_QSAR (labels)

Cleaning: Verified absence of missing/infinite values

Deduplication: Removed 6 duplicate entries

Normalization: Applied z-score normalization

Dimensionality Reduction:

Performed PCA

Retained 22 principal components (>90% total variance)

Visualized explained variance and label distribution

🧪 Methodology
📘 Naïve Bayes Classifier
Based on Bayes' Theorem with assumption of feature independence

MATLAB function: fitcnb

Posterior computed for classification:

𝑃
(
𝑌
=
𝑘
∣
𝑋
1
,
.
.
.
,
𝑋
𝑝
)
=
𝜋
(
𝑌
=
𝑘
)
∏
𝑗
=
1
𝑝
𝑃
(
𝑋
𝑗
∣
𝑌
=
𝑘
)
∑
𝑘
=
1
𝐾
𝜋
(
𝑌
=
𝑘
)
∏
𝑗
=
1
𝑝
𝑃
(
𝑋
𝑗
∣
𝑌
=
𝑘
)
P(Y=k∣X 
1
​
 ,...,X 
p
​
 )= 
∑ 
k=1
K
​
 π(Y=k)∏ 
j=1
p
​
 P(X 
j
​
 ∣Y=k)
π(Y=k)∏ 
j=1
p
​
 P(X 
j
​
 ∣Y=k)
​
 
Used 5-fold cross-validation

Selected model with highest validation accuracy

📘 Logistic Regression
Solved using Newton-Raphson method with L2 regularization

Cost minimized via Hessian matrix:

𝑓
(
𝑥
)
=
𝑒
𝑎
0
+
𝑎
1
𝑇
𝑥
1
+
𝑒
𝑎
0
+
𝑎
1
𝑇
𝑥
f(x)= 
1+e 
a 
0
​
 +a 
1
T
​
 x
 
e 
a 
0
​
 +a 
1
T
​
 x
 
​
 
Convergence criterion: 
𝜖
=
10
−
6
ϵ=10 
−6
 

5-fold cross-validation for fair evaluation

📊 Performance Summary
Metric	Naïve Bayes	Logistic Regression
Accuracy	0.58	0.90
Sensitivity (Sn)	0.98	0.79
Specificity (Sp)	0.39	0.89
AUC (ROC Curve)	0.72	0.84

📈 Results
🔹 Naïve Bayes
<p align="center"> <img src="naivebayes_confusion.png" alt="NB Confusion Matrix" width="400"/> <img src="naivebayes_roc.png" alt="NB ROC Curve" width="400"/> </p>
🔹 Logistic Regression
<p align="center"> <img src="logistic_confusion.png" alt="Logistic Confusion Matrix" width="400"/> <img src="logistic_roc.png" alt="Logistic ROC Curve" width="400"/> </p>
✅ Conclusion
Logistic Regression significantly outperforms Naïve Bayes in all metrics except sensitivity.

Naïve Bayes, while computationally light and interpretable, suffers due to its conditional independence assumption.

Given the high-dimensional nature of QSAR data, Logistic Regression offers better model fit and robustness.

🧠 Recommendations
Consider advanced classifiers such as Neural Networks or Ensemble Methods

Improve interpretability via feature selection or SHAP values

Integrate real-time model updating using online learning

📩 Contact
Muzhaffar Ma’ruf Ibrahim
mmibrahim2@sheffield.ac.uk
