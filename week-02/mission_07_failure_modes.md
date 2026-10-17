# MISSION 7 — Understand Why ML Systems Fail
## Research Question: Even if a model works during testing, why might it fail in reality?

## Why Can Machine Learning Systems Fail?
A machine learning (ML) model learns patterns from the data used during training. However, the data may be incomplete, incorrect, biased, or different from the data the model encounters in real-world situations.

Therefore, a model that performs well during testing may still make incorrect predictions after deployment.

Common reasons for ML failure include:

- Poor-quality or unrepresentative data
- Incorrect labels
- Missing values and noisy observations
- Data bias
- Data leakage
- Changes in real-world data
- Lack of human oversight

## 2. Common Reasons for ML Failures

| S.No. | Reason | Explanation | Example | Possible Solution |
|---|---|---|---|---|
| 1 | Poor-Quality Data | Data contains errors, duplicates, or incorrect values. | Incorrect temperature readings from chip sensors. | Clean and validate the data before training. |
| 2 | Unrepresentative Data | Training data does not cover all real-world conditions. | A defect detection model is trained using images from only one production line. | Collect diverse data from different production lines and conditions. |
| 3 | Data Bias | Some groups, cases, or conditions are overrepresented or underrepresented. | A model detects common defects but misses rare defect types. | Balance data where appropriate and evaluate performance across different subsets. |
| 4 | Incorrect Labels | Training examples have wrong labels or target values. | A defective chip is labelled as a good chip. | Review labels and verify them using reliable methods or experts. |
| 5 | Missing Values | Some required data values are unavailable. | Voltage measurements are missing from a semiconductor dataset. | Investigate missing data and apply an appropriate handling method. |
| 6 | Noisy Observations | Data contains measurement errors or unwanted variations. | A faulty sensor records incorrect chip temperatures. | Check sensor calibration and identify measurement errors. |
| 7 | Data Leakage | Information unavailable at prediction time accidentally enters training or evaluation. | A chip failure prediction model uses a failure status recorded after the failure occurred. | Remove leaked information and use appropriate data splitting. |
| 8 | Data Drift | The distribution of real-world input data changes over time. | A model receives different voltage or workload patterns after deployment. | Monitor input data and evaluate performance regularly. |
| 9 | Concept Drift | The relationship between inputs and the target changes over time. | A new chip design changes the relationship between workload and temperature. | Collect updated data and retrain or recalibrate the model when necessary. |
| 10 | Lack of Human Oversight | Predictions are accepted without suitable review or additional checks. | A chip predicted as safe is approved without required testing. | Introduce human review and additional checks for high-risk predictions. |

##  Analysis of Three Hypothetical ML Failures

### Failure 1: Semiconductor Defect Detection Model Misses Defective Chips

**Scenario:**

A machine learning model is developed to identify defective semiconductor chips from inspection images. During testing, it achieves high accuracy. After deployment, it misses several defective chips produced under a different manufacturing condition.

**Likely Cause:**

The training data was not representative of all manufacturing conditions. Most training images came from one process, so the model did not learn patterns associated with defects from other processes.

**Evidence That Would Help Confirm It:**

- Compare training images with images collected after deployment.
- Calculate precision and recall separately for different manufacturing conditions.
- Review false-negative cases, where defective chips were predicted to be good.
- Check whether certain defect types or production lines are underrepresented in the training data.

**Possible Mitigation:**
- Collect representative images from different production lines and defect types.
- Correct incorrect labels and remove poor-quality images where appropriate.
- Evaluate the model on independent data from different manufacturing conditions.
- Send uncertain or high-risk predictions for human inspection.

### Failure 2: Chip Failure Prediction Model Shows Unrealistically High Accuracy

**Scenario:**

A model predicts whether a semiconductor chip will fail during testing. It reports 99% accuracy during evaluation, but its performance drops significantly when used in a real production environment.

**Likely Cause:**

Data leakage may have occurred. Information recorded after a chip failure, such as a final failure status, may have accidentally been included among the model's input features. The model therefore used information that would not be available when making a real prediction.

**Evidence That Would Help Confirm It:**

- Inspect the input features for information recorded after the prediction time.
- Review the data preparation and train-test splitting process.
- Compare performance using a properly separated test dataset.
- Check whether related records from the same chip or production batch appear in both training and test sets.

**Possible Mitigation:**

- Remove features that reveal future outcomes.
- Split data according to the actual prediction scenario, using time-based or group-based splitting when appropriate.
- Keep the test dataset independent from training and model selection.
- Evaluate the model on newly collected production data before relying on it.

### Failure 3: Semiconductor Temperature Prediction Model Becomes Inaccurate

**Scenario:**

An ML model predicts chip temperature using voltage, current, workload, and environmental measurements. It performs well initially, but its predictions become inaccurate after the company introduces a new chip design and changes the cooling system.

**Likely Cause:**

The real-world data distribution and the relationship between the input variables and chip temperature have changed. The model was trained on older operating conditions and does not adequately represent the new system.

**Evidence That Would Help Confirm It:**

- Compare input distributions before and after the design change.
- Compare predicted temperatures with actual sensor measurements.
- Track prediction errors over time.
- Evaluate errors separately for the old and new chip designs.
- Check whether sensors are calibrated and whether measurements contain missing values or noise.

**Possible Mitigation:**

- Collect verified data from the new chip design and cooling system.
- Retrain or recalibrate the model when justified by the evidence.
- Monitor prediction errors continuously after deployment.
- Use temperature sensors and engineering safety limits as independent checks.
- Require human or engineering review when predictions exceed defined risk thresholds.

## Why Accuracy Alone Is Not Enough

Accuracy measures the proportion of predictions that are correct. However, it may hide important failures when one class is much more common than another.

For example, if 95 out of 100 chips are good and 5 are defective, a model that predicts every chip as good achieves 95% accuracy. However, it detects none of the defective chips.

For defect detection, **recall for the defective class** is important because it measures the proportion of actual defective chips that the model identifies.

Other useful evaluation measures include:

- **Precision:** How many chips predicted as defective are actually defective?
- **Recall:** How many actual defective chips are detected?
- **Confusion matrix:** How many predictions are correct or incorrect for each class?

The appropriate metric depends on the problem and the consequences of different mistakes.

## Importance of Human Oversight

Human oversight helps prevent incorrect ML predictions from automatically causing harmful outcomes.

It is especially important when:

- A prediction could affect safety or product quality.
- The model encounters unfamiliar data.
- The model has low confidence or unusual inputs.
- A wrong prediction could cause significant financial or operational loss.
- The decision requires engineering knowledge or additional testing.

Human review does not guarantee that every decision will be correct, but it provides an additional opportunity to detect errors and take corrective action.

## Conclusion

Machine learning systems can fail even when they perform well during testing. Common causes include poor-quality data, unrepresentative training examples, incorrect labels, data leakage, and changes in real-world conditions.
The three hypothetical failures show that different problems require different solutions. Defect detection requires representative data and suitable evaluation metrics. Unrealistically high test performance requires checking for data leakage. Declining temperature prediction accuracy requires monitoring real-world changes and validating the model with updated data.
Reliable ML systems need good-quality data, independent evaluation, continuous monitoring, and appropriate human oversight. In VLSI and semiconductor engineering, these practices are especially important because incorrect predictions can affect chip quality, reliability, and safety.

## Sources

1. Google Machine Learning Crash Course — Classification: https://developers.google.com/machine-learning/crash-course/classification
2. Google Machine Learning Crash Course — Datasets, generalization, and overfitting: https://developers.google.com/machine-learning/crash-course

## Verification Note

The three failures in this mission are hypothetical examples created for learning purposes. Their causes are plausible explanations, not confirmed real-world incidents. In an actual ML project, the evidence should be examined before deciding which cause is responsible.

