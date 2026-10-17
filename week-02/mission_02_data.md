# Mission 2 — Understand Data
## Research question: What does it mean to learn a pattern from data?

An ML (Machine Learning) system learns patterns from data by identifying relationships between input features and known outcomes or by finding patterns in data without predefined labels. The quality and relevance of the data affect how well the model learns.

## 1. Basic Data Concepts
| Concept | Explanation | Example (Chip Design) |
|---|---|---|
| Dataset | A collection of data used to study a problem or train a model. | Historical chip-design results containing delay, power, cell count, and timing status. |
| Sample | One example or item in a dataset. | Data recorded for one chip-design run. |
| Observation | A recorded instance of something measured or observed. | The measured delay and power values for one design run. |
| Feature | An input variable used by a model to learn patterns or make predictions. | Delay, power consumption, and cell count. |
| Label | The known answer or category associated with a training example. | Pass or Fail timing status. |
| Target | The outcome the model is intended to predict. | Predicting whether a chip-design run will Pass or Fail timing. |

## Distinguishing Data Types

### Structured Data vs Unstructured Data

| Type | Explanation | Example |
|---|---|---|
| Structured Data | Data organised in a predefined format, such as rows and columns. | A table containing cell count, delay, and congestion measurements from VLSI design runs. |
| Unstructured Data | Data that does not naturally follow a fixed tabular structure. | A chip layout image, an audio recording, or a free-form text report. |

**Difference:** Structured data is organised in a defined format, making it easier to store and analyse using tables. Unstructured data may require additional processing to extract useful information.

### Numerical Features vs Categorical Features

| Type | Explanation | Example |
|---|---|---|
| Numerical Features | Features represented by numbers that express quantities or measurements. | Cell Count = 12000; Estimated Delay = 0.82 ns. |
| Categorical Features | Features that represent groups, classes, or categories. | Congestion Level = Low, Medium, or High. |

**Difference:** Numerical features represent measurable quantities, while categorical features represent labels or groups. 
Categorical values may be encoded into numbers for a model, but those numbers do not necessarily represent quantities.

### Examples from the Illustrative Dataset

- **Structured data:** The complete VLSI design-run table.
- **Numerical features:** Cell Count and Estimated Delay.
- **Categorical feature:** Congestion Level.
- **Target / Label:** Meets Timing (Yes or No), which is a categorical target.

## Data Quality Concepts

| Concept | Explanation | Example |
|---|---|---|
| Data Collection | Gathering relevant information from sources or measurements. | Collecting delay and power measurements from chip-design runs. |
| Data Cleaning | Finding and correcting or handling errors and problems in a dataset. | Correcting an incorrectly entered delay value or removing an accidental duplicate record. |
| Missing Values | Values that are absent from some records. | A design run has no recorded power measurement. |
| Noisy Data | Data containing errors, random variation, or irrelevant information that can affect learning. | A faulty measurement tool records an incorrect delay value. |
| Inconsistent Labels | Labels assigned incorrectly or using different meanings for similar cases. | The same timing-failure condition is marked Fail in one record and Pass in another. |

Data should be collected consistently using appropriate measurement conditions. Before training a model, the dataset should be checked for accuracy, completeness, and consistency.
## Example Dataset
**Problem:** Predict whether a VLSI Physical Design run meets its timing target.
| Run | Cell Count | Estimated Delay (ns) | Congestion Level | Meets Timing |
|---|---:|---:|---|---|
| R1 | 12000 | 0.82 | Low | Yes |
| R2 | 18000 | 1.15 | Medium | No |
| R3 | 9500 | 0.76 | Low | Yes |
| R4 | 22000 | 1.30 | High | No |
| R5 | 15000 | 0.91 | Medium | Yes |
| R6 | 20000 | 1.22 | High | No |

### Identifying Features and Target

- **Number of samples:** 6 design runs.
- **Features:** Cell Count, Estimated Delay, and Congestion Level.
- **Target / Label:** Meets Timing.
- **Numerical features:** Cell Count and Estimated Delay.
- **Categorical feature:** Congestion Level.
- **Target type:** Binary classification because the output has two classes: Yes and No.
- **Data type:** Structured and labelled data because the information is organised in a table and each run has a known outcome.

## 6. Why Are Training, Validation, and Test Data Different?

- **Training data:** Used by the learning algorithm to learn patterns from examples.
- **Validation data:** Used during development to compare models and adjust settings.
- **Test data:** Used at the end to evaluate how well the selected model performs on unseen examples.

Keeping these datasets separate helps provide a fairer evaluation. If information from the test set influences model development, the reported performance may be overly optimistic.

## Why Does More Data Not Always Mean Better Data?

Data quantity refers to the number of examples available, while data quality refers to how accurate, complete, consistent, relevant, and representative those examples are.

For example, collecting 10,000 design-run records may seem useful. However, if many records contain incorrect delay measurements, duplicate entries, or wrong timing labels, the model may learn misleading patterns.

Therefore, **a large amount of poor-quality data does not guarantee a good model**. Both quantity and quality matter.


## Connection to VLSI Physical Design

In VLSI Physical Design, an ML model could potentially help predict whether a design run will meet a timing target.

- **Input features:** Cell count, estimated delay, and congestion level.
- **Target:** Whether the design meets timing.
- **Possible use:** Help engineers identify design runs that may need further investigation.
- **Important limitation:** The prediction depends on the quality and representativeness of the training data.

###  Two Ways Data Quality Can Affect a Model

**1. Incorrect measurements**

If the estimated delay values are inaccurate, the model may learn incorrect relationships between design features and timing results. This can lead to unreliable predictions.

**2. Incorrect labels**

If a design that fails timing is incorrectly labelled as passing, the model learns from wrong information. As a result, it may predict Pass or Fail incorrectly for new design runs.

### Conclusion

Data quality is important because an ML model learns patterns from the examples provided to it. Accurate measurements and correct labels help the model make more reliable predictions.

**Note:** This dataset is fictional and is not based on actual VLSI design measurements.


## Sources

1. Google for Developers — Machine Learning Course:  
   https://developers.google.com/machine-learning/crash-course/

2. Google for Developers — Data Characteristics:  
   https://developers.google.com/machine-learning/crash-course/overfitting/data-characteristics

3. IBM — What Is Machine Learning?  
   https://www.ibm.com/think/topics/machine-learning

**Verification Note:** These sources provide background on ML and data concepts. The semiconductor design dataset in this submission is fictional and illustrative; it is not evidence of actual chip-design results.
