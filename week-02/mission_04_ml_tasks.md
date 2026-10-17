# MISSION 4 — Understand ML Task Types
## Research question: What kinds of problems can machine learning solve
### Six Main Machine Learning Task Types
### 1. Classification
Classification predicts a category or class for given input data.

- **Input:** Data containing relevant features.
- **Output:** A category or class.
- **Example:** Classifying semiconductor chips as defective or non-defective.

### 2. Regression
Regression predicts a continuous numerical value.

- **Input:** Data containing features related to a numerical value.
- **Output:** A numerical value.
- **Example:** Predicting the power consumption of a semiconductor chip.

### 3. Clustering
Clustering groups similar data points without requiring predefined labels.

- **Input:** Unlabelled data.
- **Output:** Groups or clusters of similar items.
- **Example:** Grouping semiconductor chips with similar electrical characteristics.

### 4. Anomaly Detection
Anomaly detection identifies data points or behaviours that differ from normal patterns.

- **Input:** Historical measurements or operating data.
- **Output:** An anomaly score or an alert.
- **Example:** Detecting unusual voltage or current readings during chip testing.

### 5. Dimensionality Reduction
Dimensionality reduction reduces the number of features while preserving important information as much as possible.

- **Input:** Data containing many features.
- **Output:** A smaller set of features or a lower-dimensional representation.
- **Example:** Reducing hundreds of semiconductor test measurements to a smaller set of informative features.

### 6. Recommendation and Ranking
Recommendation suggests relevant items, while ranking orders items according to their predicted relevance.

- **Input:** User preferences, historical interactions, or item features.
- **Output:** Recommended items or an ordered list.
- **Example:** Recommending VLSI courses based on a student's interests and ranking them by relevance.

## Real-World Problems

| No. | Real-World Problem | ML Task Type | Input Data | Expected Output |
|---|---|---|---|---|
| 1 | Detect defective semiconductor chips | Classification | Electrical test measurements and labelled chip results | Defective or non-defective |
| 2 | Predict chip power consumption | Regression | Voltage, frequency, workload, and design features | Predicted power in watts |
| 3 | Group similar semiconductor chips | Clustering | Electrical characteristics and performance measurements | Groups of similar chips |
| 4 | Detect unusual chip behaviour | Anomaly Detection | Voltage, current, and test measurements | Anomaly score or alert |
| 5 | Simplify semiconductor test data | Dimensionality Reduction | Test measurements and process features | Reduced set of informative features |
| 6 | Recommend VLSI courses | Recommendation/Ranking | Student interests, skills, and course information | Recommended courses in ranked order |
| 7 | Identify spam emails | Classification | Email text, sender details, and other features | Spam or not spam |
| 8 | Predict house prices | Regression | Location, area, number of rooms, and other features | Estimated house price |

##  Task Type vs Learning Paradigm

| Aspect | Task Type | Learning Paradigm |
|---|---|---|
| Meaning | What problem should the model solve? | How does the model learn? |
| Examples | Classification, regression, clustering | Supervised, unsupervised, reinforcement learning |
| Main focus | Expected output | Source of the learning signal |
| Example | Predict whether a chip is defective | Learn from labelled examples of defective and non-defective chips |

## Different Algorithms Solve the Same Task?
Yes. Multiple algorithms can solve the same type of ML task. Their performance depends on the data, assumptions, and problem requirements.

| Task Type | Possible Algorithms |
|---|---|
| Classification | Logistic Regression, Decision Tree, Random Forest, Support Vector Machine |
| Regression | Linear Regression, Decision Tree Regressor, Random Forest Regressor |
| Clustering | K-means, Hierarchical Clustering, DBSCAN |
| Anomaly Detection | Isolation Forest, One-Class SVM, Statistical Thresholding |
| Dimensionality Reduction | PCA, Autoencoders |
| Recommendation/Ranking | Collaborative Filtering, Learning-to-Rank Models |

- For example, semiconductor defect classification can use a Decision Tree, Random Forest, or Support Vector Machine. The best algorithm depends on the available data, accuracy requirements, interpretability, and computational cost.

## Conclusion
Machine Learning can solve different types of problems, such as classification, regression, clustering, anomaly detection, dimensionality reduction, and recommendation or ranking.
I learned that each task type has a different purpose and expected output. Task type explains what problem the model solves, whereas the learning paradigm explains how the model learns. Different algorithms can also solve similar tasks depending on the data and requirements.

## Sources
Google for Developers — Machine Learning Crash Course
https://developers.google.com/machine-learning/crash-course

IBM — What Is Machine Learning?
https://www.ibm.com/think/topics/machine-learning

Google Introduction to Clustering:
https://developers.google.com/machine-learning/clustering
