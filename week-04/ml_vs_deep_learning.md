
# Mission 2 — What Makes Deep Learning Different?
## 1. Introduction

Artificial Intelligence has different techniques for making computers solve problems and perform intelligent tasks. Some systems follow instructions written by humans, while others learn from examples and experience.

Three important approaches are rule-based systems, traditional machine learning, and deep learning.

- **Rule-Based Systems:** These systems use conditions and instructions designed by humans to make decisions.
- **Traditional Machine Learning:** These algorithms study examples and identify relationships between input data and expected outputs.
- **Deep Learning:** This approach uses neural networks containing multiple processing layers to learn patterns and useful representations from data.

Although these approaches can solve similar problems, their learning methods, data requirements, and complexity are different.

## 2. Understanding How Each Approach Processes Information

The main difference between these approaches is how they reach a decision.

### A. Rule-Based Processing

A rule-based system follows instructions provided by a programmer or domain expert.

For example, an inspection system can check whether a measured value exceeds a predefined engineering limit. The output depends on the condition written in the program.

The system does not learn from previous examples.

### B. Traditional Machine Learning

Traditional machine learning identifies patterns by studying a dataset.

For example, an engineer can provide defect measurements such as area, shape, and brightness to a classification algorithm. The algorithm learns how these measurements relate to different defect categories.

The quality of the selected features can strongly influence the result.

### C. Deep Learning Processing

Deep learning uses interconnected neural network layers to process information.

Instead of depending entirely on manually calculated features, a deep learning model can learn useful representations directly from suitable input data.

For example, it can study semiconductor inspection images and learn visual characteristics associated with different defect categories.

## 3. Comparison of Different Learning Approaches

| Parameter | Rule-Based System | Traditional ML | Deep Learning |
|---|---|---|---|
| Main concept | Human-defined instructions | Learning from examples | Learning through multilayer neural networks |
| Decision process | Checks predefined conditions | Uses learned statistical patterns | Uses learned representations |
| Data requirement | No training dataset required | Requires training examples | Usually requires substantial training examples |
| Feature handling | Conditions are manually defined | Features are often selected or engineered | Features can be learned during training |
| Adaptability | Requires rule modification | Can be retrained using new data | Can be retrained using new data |
| Processing complexity | Usually simple | Depends on algorithm | Can be computationally intensive |
| Typical application | Threshold checking | Numerical classification | Complex image recognition |

The actual differences depend on the implementation and the problem being solved.

## 4. Understanding Feature Extraction

Feature extraction means identifying useful information from raw data that can help a model make predictions.

Consider a semiconductor inspection image.

An engineer may identify features such as:

- Defect area.
- Boundary shape.
- Pixel intensity.
- Edge information.
- Surface variation.

In a traditional machine learning workflow, these measurements may be calculated and supplied to an algorithm.

In deep learning, a neural network can learn useful image representations through its layers.

For example:

1. Initial layers may learn simple visual patterns.
2. Intermediate layers may combine these patterns into more complex structures.
3. Later layers may use the learned representations to distinguish defect categories.

This is one important reason deep learning is useful for complex image-processing applications.

## 5. How Training Changes a Model

Machine learning and deep learning models improve through training.

In supervised learning, the model receives examples along with their expected answers.

Consider a semiconductor image dataset containing two categories:

| Input Data | Expected Output |
|---|---|
| Inspection image of a scratch | Scratch |
| Inspection image of a crack | Crack |
| Inspection image of a clean surface | No Defect |

The learning process generally involves:

1. Providing an input example to the model.
2. Generating a predicted output.
3. Comparing the prediction with the expected output.
4. Calculating the prediction error using a loss function.
5. Adjusting model parameters to improve predictions.
6. Repeating the process using training examples.

After training, the model should be checked using separate data to determine whether it can recognize patterns in examples it has not previously seen.

Training accuracy alone does not prove that a model will work reliably in real applications.

## 6. What Makes Deep Learning Computationally Different?

Deep learning networks can contain many neurons, connections, and trainable parameters.

During training, the network performs mathematical operations to calculate predictions and update its parameters.

This can require significant computing resources, especially when processing large image datasets or using complex architectures.

Some important factors are:

### A. Network Size

A network with more layers and neurons may have more parameters to train.

### B. Training Dataset

Large and diverse datasets can provide more examples of the patterns the model needs to learn.

### C. Computational Resources

Graphics Processing Units (GPUs) can accelerate many neural network training operations.

### D. Training Time

Complex networks may require more time and resources to train and evaluate.

However, a larger network does not automatically produce better results. The architecture must be appropriate for the problem.

## 7. Can Deep Learning Always Replace Traditional Machine Learning?

No. Each approach has situations where it can be useful.

For example:

- A rule-based system can check whether a measured timing slack violates a specified limit.
- Traditional machine learning can study numerical design metrics and estimate timing risk.
- Deep learning can be investigated when complex input patterns, such as semiconductor inspection images, need to be classified.

For small structured datasets, traditional machine learning may provide good results with lower computational requirements.

For image-related problems, deep learning may be worth investigating because it can learn visual features directly.

The final choice should depend on experimental results rather than assuming that one technique is always superior.

## 8. Engineering Application — Semiconductor Industry

AI and machine learning have potential applications across semiconductor manufacturing and VLSI engineering.

Some examples include:

### A. Semiconductor Defect Classification

Deep learning can be investigated for identifying visual defect patterns in wafer inspection images.

### B. Timing-Risk Estimation

Traditional machine learning could use design metrics such as estimated slack, cell count, and fanout to predict possible timing problems.

### C. Congestion Analysis

Machine learning approaches could be explored to identify placement regions that may experience routing congestion.

### D. Engineering Report Analysis

AI techniques could assist in extracting and organizing useful information from large engineering reports.

These are possible applications. Their effectiveness depends on data availability, model validation, and the requirements of the engineering workflow.

## 9. My Understanding

Through this mission, I understood that different AI approaches solve problems in different ways.

I learned that:

- Rule-based systems make decisions using predefined conditions.
- Traditional machine learning identifies patterns from prepared datasets.
- Deep learning uses multiple neural network layers to learn complex representations.
- Feature selection is important in many traditional machine learning workflows.
- Deep learning can reduce manual feature-design requirements for complex inputs.
- More complex models can require additional data and computational resources.
- Every model needs proper evaluation before being used in practical applications.

As an ECE graduate interested in Physical Design, this comparison helped me understand where AI techniques could support semiconductor engineering tasks.

## 10. Conclusion

Rule-based systems, traditional machine learning, and deep learning provide different methods for processing information and solving problems.

Rule-based systems are useful for clearly defined conditions. Traditional machine learning is suitable for learning patterns from structured data. Deep learning is useful to investigate when complex representations must be learned from large or unstructured datasets.

Understanding their differences helps engineers choose an appropriate technique instead of selecting a model only because it is more advanced.

In semiconductor engineering, AI-based predictions should always be supported by reliable data, proper validation, and engineering verification.

## References

1. Google Machine Learning Crash Course — [Introduction to Machine Learning](https://developers.google.com/machine-learning/intro-to-ml). Explains the basic concepts and applications of machine learning.

2. IBM — [What Is Deep Learning?](https://www.ibm.com/think/topics/deep-learning). Describes neural networks, deep learning concepts, and applications.

3. TensorFlow — [Introduction to Neural Networks](https://www.tensorflow.org/learn). Provides learning resources about neural networks and deep learning.

4. Google Machine Learning Crash Course — [Neural Networks](https://developers.google.com/machine-learning/crash-course/neural-networks). Explains neural network components and their learning process.

