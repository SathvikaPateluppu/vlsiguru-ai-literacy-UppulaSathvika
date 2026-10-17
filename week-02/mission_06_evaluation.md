
# MISSION 6 — Evaluation and Generalization

## Research Question : How do we know whether a machine learning model has learned something useful and performs well on new, unseen data

## Training, Validation, and Test Sets

| **Dataset** | **Purpose** |
|---|---|
| Training set | Used to train the model and learn its parameters. |
| Validation set | Used to compare models, tune hyperparameters, and make development decisions. |
| Test set | Used to evaluate the final selected model on unseen data. |

Keeping these datasets separate helps us estimate how well a model generalizes to new data. The test set should not be used repeatedly to tune the model because this can make the evaluation less reliable.

## Generalization, Overfitting, and Underfitting

**Generalization:** The ability of a trained model to make useful predictions on new, unseen data.

**Overfitting:** A model learns the training data too closely, including noise or accidental patterns. It performs well on training data but poorly on unseen data.

**Underfitting:** A model is too simple or has not learned enough from the data. It performs poorly on both training data and unseen data.

A good model should learn meaningful patterns that generalize to new examples rather than simply memorizing training data.

| **Concept** | **Meaning** | **Typical Performance** |
|---|---|---|
| Generalization | Performs well on unseen data. | Good performance on new examples. |
| Overfitting | Learns training-specific details or noise. | Good training performance but poor unseen-data performance. |
| Underfitting | Fails to learn important patterns. | Poor performance on both training and unseen data. |

## Classification Evaluation Metrics

**Accuracy:** The proportion of all predictions that are correct.

Accuracy = (TP + TN) / Total Predictions

**Precision:** Of all positive predictions, the proportion that are actually positive.

Precision = TP / (TP + FP)

**Recall:** Of all actual positive cases, the proportion correctly identified.

Recall = TP / (TP + FN)

**False Positive (FP):** The model predicts positive when the actual result is negative.

**False Negative (FN):** The model predicts negative when the actual result is positive.

**Absolute Error:** The absolute difference between a predicted numerical value and the actual value. It is commonly used in regression problems.

Absolute Error = |Actual Value - Predicted Value|

## Confusion Matrix

Consider a hypothetical Machine Learning model that predicts whether a semiconductor design will meet timing requirements.

|  | **Actual: Meets Timing** | **Actual: Fails Timing** |
|---|---:|---:|
| **Predicted: Meets Timing** | 80 (True Positive) | 10 (False Positive) |
| **Predicted: Fails Timing** | 5 (False Negative) | 5 (True Negative) |

In this example:

- True Positives (TP) = 80
- False Positives (FP) = 10
- False Negatives (FN) = 5
- True Negatives (TN) = 5
- Total predictions = 100

Here, the positive class is defined as a design that meets timing.

### Calculating the Metrics

**Accuracy**

Accuracy = (TP + TN) / Total Predictions

= (80 + 5) / 100 = **85%**

**Precision**

Precision = TP / (TP + FP)

= 80 / (80 + 10) = **88.89%**

**Recall**

Recall = TP / (TP + FN)

= 80 / (80 + 5) = **94.12%**

These values are illustrative and do not represent measured semiconductor design results.

## Why Accuracy Alone Can Be Misleading

Accuracy can be misleading when the classes are imbalanced.

For example, suppose 95 out of 100 semiconductor designs meet timing and only 5 fail. A model that predicts every design will meet timing achieves 95% accuracy, even though it fails to identify any timing failures.

This happens because the model predicts only the majority class.

In Physical Design, missing a timing failure could lead engineers to overlook a design that needs further investigation. Therefore, recall for the timing-failure class may be particularly important because it measures the proportion of actual timing failures correctly identified.

Precision is also important because too many false alarms can waste engineering time. The appropriate metric depends on the engineering objective and the cost of different errors.

## Why Comparing with a Simple Baseline Is Useful

A baseline is a simple method used as a reference point to evaluate a more advanced model.

For example, a baseline model could always predict that a semiconductor design will meet timing. If most designs in the dataset meet timing, this baseline may achieve high accuracy despite failing to identify timing violations.

A more advanced model should be compared with the baseline using suitable metrics, especially recall for timing failures when missing a failure is costly.
A baseline helps determine whether a more complex model provides a meaningful improvement over a simple approach.

## Conclusion

Training, validation, and test datasets serve different purposes in Machine Learning. Generalization indicates how well a model performs on unseen data, while overfitting and underfitting explain common causes of poor performance.

Accuracy, precision, recall, false positives, false negatives, and absolute error provide different ways to evaluate model performance. Accuracy alone can be misleading when classes are imbalanced, so the choice of metric must match the problem and the consequences of incorrect predictions.

Comparing a model with a simple baseline helps determine whether it offers a meaningful improvement. In VLSI Physical Design, these evaluation concepts can support reliable ML-assisted analysis, but engineering verification and sign-off remain essential.

## Sources

Google for Developers — Machine Learning Crash Course:
https://developers.google.com/machine-learning/crash-course

Google for Developers — Classification:
https://developers.google.com/machine-learning/crash-course/classification

Scikit-learn — Model Evaluation:
https://scikit-learn.org/stable/modules/model_evaluation.html

# Verification Note:
The confusion-matrix values and timing-prediction examples are hypothetical and created for this assignment. The semiconductor application is illustrative and does not represent measured industry results.

