# Mission 01 — Data Behind Deep Learning
## 1. Introduction

Deep learning models learn patterns from examples. Before training a neural network, raw data must be collected, prepared, labelled, and checked for quality. Poorly prepared data can lead to incorrect predictions even when the model architecture is suitable.

For this mission, I use the example of a semiconductor inspection system that examines images and predicts whether a possible defect is present.

## 2. How Does an Image Become Numerical Data?

A computer represents a digital image as a collection of small elements called pixels. Each pixel stores numerical information about the image's colour or brightness.

- **Grayscale image:** Each pixel typically contains one intensity value, commonly from 0 to 255 for an 8-bit image.
- **RGB image:** Each pixel contains three values representing Red, Green, and Blue.
- **Image dimensions:** An RGB image can be represented as a numerical array with dimensions Height × Width × 3.

For example, a small RGB image with dimensions 32 × 32 contains:

32 × 32 × 3 = 3,072 numerical values.

A neural network processes these numerical values rather than understanding an image in the same way a human does. During training, it learns patterns that may help distinguish defective images from non-defective ones.

### Example: Grayscale Image

| Pixel | Intensity |
|---|---:|
| Pixel 1 | 0 |
| Pixel 2 | 120 |
| Pixel 3 | 200 |
| Pixel 4 | 255 |

- 0 represents black.
- 255 represents white.
- Values between them represent different shades of grey.

## 3. Data Preparation

Data preparation transforms raw data into a consistent format that a model can process.

Important steps include:

### A. Data Collection
Gather representative semiconductor inspection images from suitable inspection processes.

### B. Data Cleaning
Identify corrupted images, incorrect records, duplicates, and unusable examples.

### C. Resizing
Convert images to a consistent size when required by the model.

### D. Formatting
Convert images into numerical arrays or tensors in the format expected by the model.

### E. Normalization
Scale pixel values to a suitable range, such as 0–1 instead of 0–255.

For example:

Normalized value = Original pixel value / 255

If a pixel value is 128:

128 / 255 ≈ 0.502

Normalization helps place input values on a suitable scale and can make model training more effective.

### F. Labelling
Assign the correct target label to each image.

### G. Dataset Splitting
Separate the data into training, validation, and test sets.

## 4. Labels and Examples

A **label** is the target answer associated with an example. The input is what the model receives, while the label is the answer it learns to predict in supervised learning.

For semiconductor inspection, a simple labelled dataset could contain:

| Image Example | Label |
|---|---|
| Image showing a confirmed defect | Defect |
| Image showing no confirmed defect | No Defect |
| Image containing a confirmed crack | Defect |
| Image showing a clean inspection area | No Defect |

The labels must be based on reliable inspection or expert review.

If a defective image is incorrectly labelled as "No Defect", the model may learn a misleading pattern.

Labels may also be more detailed than two classes. For example, a dataset could classify scratches, cracks, contamination, and other defect categories separately.

## 5. Data Quality

Data quality affects how well a neural network can learn useful patterns.

Common data-quality problems include:

### A. Incorrect Labels
The model receives the wrong target answer and may learn incorrect associations.

### B. Duplicate Images
Repeated or near-identical images can make the model appear more accurate than it really is, especially if duplicates appear in different dataset splits.

### C. Noisy or Corrupted Images
Image artifacts, blur, or inconsistent lighting may hide important defect features.

### D. Missing Examples
Rare but important defect types may be absent from the dataset.

### E. Inconsistent Capture Conditions
Different cameras, magnification, lighting, or inspection procedures can introduce variations unrelated to the defect itself.

These problems should be investigated before training. Data cleaning must also be careful not to remove genuine defects simply because they look unusual.

## 6. Representativeness and Class Imbalance

A dataset should represent the range of examples the model is expected to encounter in practice.

Suppose a dataset contains:

| Category | Number of Images |
|---|---:|
| No Defect | 9,500 |
| Defect | 500 |
| **Total** | **10,000** |

This is a class imbalance because one category contains far more examples than the other.

A model could achieve apparently high accuracy by predicting "No Defect" for most images, while still missing many real defects.

Possible approaches include:

- Collecting more examples of underrepresented defect categories.
- Using appropriate sampling strategies.
- Applying class weights where suitable.
- Evaluating each class separately.

The dataset should also represent variations in defect size, shape, lighting, manufacturing conditions, and inspection equipment.

## 7. Training, Validation, and Test Splits

The original dataset is commonly divided into three separate subsets.

| Dataset | Purpose | How It Is Used |
|---|---|---|
| Training Set | Teach the model to learn patterns | Used to update model parameters |
| Validation Set | Help choose and tune the model | Used during development to compare configurations and monitor generalization |
| Test Set | Estimate final performance on unseen examples | Used for final evaluation after model choices have been made |

A split such as 70% training, 15% validation, and 15% test is one possible starting point, not a universal rule. The appropriate split depends on the dataset size and problem.

The test set should not be used repeatedly to make model-development decisions. Doing so can make the final evaluation less reliable.

Duplicates and closely related images must also be handled carefully. For example, multiple images of the same physical wafer should not automatically be scattered across training and test sets if that would allow the model to recognise familiar wafer-specific patterns.

## 8. Data Preparation Flow Diagram

The following diagram summarises the workflow from raw inspection images to evaluation.

```mermaid
flowchart TD
    A["Raw Inspection Images"] --> B["Clean, Resize and Format Data"]
    B --> C["Assign and Verify Labels"]
    C --> D["Check Data Quality and Duplicates"]
    D --> E["Split into Training, Validation and Test Sets"]
    E --> F["Train Model Using Training Set"]
    F --> G["Evaluate Using Validation Set"]
    G --> H{"Improve the Model?"}
    H -- Yes --> I["Adjust Model Settings"]
    I --> F
    H -- No --> J["Final Evaluation Using Test Set"]
    J --> K["Review Errors and Limitations"]
```

### Explanation of Each Stage

1. **Raw Inspection Images:** Images are collected from the inspection process.
2. **Data Preparation:** Images are checked for quality and converted into a consistent numerical format.
3. **Label Verification:** Each usable image receives an appropriate label, and labels are checked for accuracy.
4. **Dataset Splitting:** Separate subsets are prepared for training, validation, and final testing.
5. **Training:** The neural network learns patterns from training examples by updating its parameters.
6. **Validation:** The model's performance is monitored using validation data.
7. **Model Improvement:** Engineers may adjust model settings based on validation results.
8. **Final Testing:** The selected model is evaluated using previously unseen test data.
9. **Review:** Errors are investigated to understand limitations and identify improvements.

## 9. Data-Related Problems That Can Affect Predictions

### Problem 1: Incorrect Labels

Suppose several images containing cracks are incorrectly labelled as "No Defect."

During training, the model receives contradictory examples and may learn that crack-like patterns do not indicate defects.

**Possible Effect:** The model may miss actual defects during inspection.

**Possible Mitigation:** Verify labels using reliable inspection records or expert review, investigate disagreements, and correct confirmed labelling errors.

### Problem 2: Unrepresentative or Imbalanced Data

Suppose the training dataset contains many examples of common defects but very few examples of a rare, serious defect.

The model may learn the common categories well but fail to recognise the rare defect.

**Possible Effect:** The system may report good overall accuracy while missing important defects.

**Possible Mitigation:** Collect more representative examples where possible, inspect per-class performance, and evaluate the model on a test set that adequately represents the intended use.

## 10. Connection to My Physical Design Track

As an ECE graduate interested in Physical Design, I understand that data quality is important when applying AI to semiconductor engineering.

Deep learning can be explored in semiconductor inspection and other engineering applications. However, reliable results depend on suitable input data, correct labels, and proper evaluation.

Understanding data preparation gives me a foundation for learning how AI and machine learning can support semiconductor engineering workflows.

## 11. My Understanding

Through this mission, I learned that deep learning does not begin directly with a neural network. It begins with collecting and preparing suitable data.

I understood the importance of:

- Converting images into numerical representations.
- Cleaning and normalizing data.
- Assigning correct labels.
- Identifying duplicate and noisy data.
- Understanding class imbalance.
- Separating training, validation, and test datasets.

I also learned that even a well-designed neural network may produce unreliable predictions if the data used for training is incorrect or unrepresentative.

## 12. Conclusion

Data preparation is a fundamental part of deep learning, not merely a preliminary step. Images must be represented numerically, cleaned, labelled, and divided appropriately before a model can learn and be evaluated.

For semiconductor inspection, reliable labels, representative data, and an independent test set are essential for assessing whether predictions are useful on unseen images.

Even a well-trained model can fail when the data contains errors or differs from the conditions encountered in practice.

## 13. References

1. Google Machine Learning Crash Course — [Working with Numerical Data](https://developers.google.com/machine-learning/crash-course/numerical-data)
2. Google Machine Learning Crash Course — [Dividing the Original Dataset](https://developers.google.com/machine-learning/crash-course/overfitting/dividing-datasets)
3. Google Machine Learning Crash Course — [Overfitting and Generalization](https://developers.google.com/machine-learning/crash-course/overfitting/overfitting)

