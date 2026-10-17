# Mission 9 — Semiconductor Case Study

## Research Question : How can machine learning help predict timing problems during semiconductor Physical Design?

## Problem Statement

In semiconductor Physical Design, engineers need to determine whether a design will meet its timing requirements. Timing analysis can be computationally demanding, and engineers may want an early indication of potential problems while exploring design options.

A machine learning model could use historical design data to estimate timing-related outcomes and help engineers prioritise designs for further investigation.

The model would support engineering decisions rather than replace accurate timing analysis or sign-off.

## Available Data

A hypothetical dataset could contain information collected from previous design runs.

| **Feature** | **Description** | **Data Type** |
|---|---|---|
| Cell count | Number of cells in the design | Numerical |
| Estimated congestion | An estimate of routing congestion | Numerical |
| Utilisation | Proportion of placement area occupied by cells | Numerical |
| Clock frequency target | Required operating frequency | Numerical |
| Design configuration | Identifier or category for the design setup | Categorical |
| Measured timing result | Timing result obtained from engineering analysis | Numerical |

The dataset should contain reliable measurements and representative examples from different design conditions. The features must be available at the point when the model is expected to make a prediction.

## Target Variable

For this case study, the target is:

**Meets Timing:** Whether the design satisfies its specified timing requirement.

- `Yes` — the design meets the specified timing requirement.
- `No` — the design does not meet the specified timing requirement.

This makes the problem a **binary classification task**.

The target label must be derived from trusted timing-analysis results using a clearly defined timing criterion, such as whether the required timing constraints are satisfied.

## Machine Learning Task

**Task type:** Supervised learning — binary classification.

**Inputs:** Available design characteristics, such as cell count, congestion, utilisation, and clock frequency target.

**Output:** A predicted class indicating whether the design is likely to meet timing.

The model would learn relationships between historical design characteristics and their corresponding timing labels.

A probability score could also be produced to indicate the model's estimated likelihood that a design will meet timing. This score would need to be validated and should not be treated as a guarantee.

## Proposed Workflow

1. Collect historical Physical Design data and timing results.
2. Check data quality, consistency, and target labels.
3. Prepare relevant features and separate training, validation, and test data.
4. Train a classification model using the training data.
5. Select and tune the model using validation data.
6. Evaluate the final model on unseen test data.
7. Review predictions with engineers and monitor performance when design conditions change.

The dataset should be split carefully to avoid data leakage. For example, closely related runs from the same design should not be distributed across training and test sets in a way that makes evaluation unrealistically easy.

## Evaluation Metrics

Suitable metrics include:

| **Metric** | **Purpose** |
|---|---|
| Recall for timing failures | Measures how many actual timing failures the model identifies. |
| Precision for predicted timing failures | Measures how many designs flagged as timing failures actually fail timing. |
| Confusion matrix | Shows correct and incorrect predictions for both classes. |
| Accuracy | Measures the overall proportion of correct predictions. |
| False-negative rate | Measures how often actual timing failures are incorrectly predicted to meet timing. |
| Inference time | Measures how quickly the model produces a prediction. |

Recall for timing failures may be especially important when missing a failing design is costly. Precision also matters because excessive false alarms can waste engineering time.

The final choice of metrics should reflect the engineering risks and intended use of the model.

## Expected Benefits

- Identify designs that may need early investigation.
- Help prioritise engineering effort.
- Provide an additional estimate while exploring design options.
- Reveal patterns in historical design data that may deserve further analysis.
- Potentially reduce unnecessary design iterations if predictions are sufficiently reliable.

These are potential benefits; they would need to be demonstrated through actual evaluation.

## Limitations and Risks

- Historical data may not represent new designs or technologies.
- Incorrect measurements or labels may reduce reliability.
- Changes in tools, libraries, constraints, or implementation settings may affect predictions.
- A model may produce false positives or false negatives.
- A model trained on one set of design conditions may not generalise to another.
- A model may appear successful if training and test data are not separated properly.
- Predictions do not replace sign-off timing analysis.

The model should be used only within a clearly defined scope and monitored for changes in data and performance.

## Conclusion

Machine learning could support Physical Design by predicting whether a design is likely to meet timing based on historical design characteristics. A supervised binary classification model is one possible approach.

Its usefulness depends on data quality, representative training examples, appropriate evaluation metrics, and careful engineering review. Research demonstrates that ML-based timing prediction is a promising area, but the proposed model would still require independent validation.

The model should assist early investigation and prioritisation, not replace required timing analysis or engineering sign-off.

## Sources
Google for Developers — Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
Google for Developers — Classification: https://developers.google.com/machine-learning/crash-course/classification

## Verification note: 
This case study is a proposed illustrative application for Physical Design. The dataset, workflow, and benefits are hypothetical and have not been validated against actual semiconductor design runs.
