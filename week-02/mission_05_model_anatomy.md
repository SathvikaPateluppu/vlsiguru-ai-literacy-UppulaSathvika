
# MISSION 5 | Understand the Anatomy of an ML Model

## Research Question: What happens between feeding data into an ML system and receiving a prediction?

## Answer

When data is given to a Machine Learning (ML) system, the system uses a trained model to process the input and generate a prediction. Before the model can make predictions, it usually goes through a training process in which a learning algorithm learns patterns from example data.
During training, the model makes predictions and compares them with the correct target answers. A loss function measures the prediction errors, and an optimisation process adjusts the model's parameters to improve its predictions. This process continues until a suitable stopping point is reached.
After training, the trained model is used for inference. During inference, new input data is given to the model, and it produces a prediction using the patterns it has learned.

##  Distinguish an Algorithm, a Model, and Learned Parameters

An algorithm, a model, and learned parameters are three different parts of a Machine Learning system.

**Algorithm:** An algorithm is the method or procedure used to learn patterns from training data.

**Model:** A model represents the learned relationship between inputs and outputs and uses it to make predictions.

**Learned Parameters:** Parameters are the values adjusted during training so that the model can make better predictions.

| Term | Meaning | Example |
|---|---|---|
| Algorithm | A method used to learn patterns from data | Linear Regression |
| Model | The learned relationship used to make predictions | A model that predicts chip power consumption |
| Parameters | Values learned during training | Slope and intercept in Linear Regression |
| Training | The process of learning patterns from example data | Learning the relationship between chip frequency and power |
| Inference | Using a trained model to predict outcomes for new inputs | Predicting power consumption for a new chip |

## Training Versus Inference
**Training** is the process in which a learning algorithm learns patterns from example data. During training, the model makes predictions, compares them with the correct answers when available, measures the errors, and adjusts its parameters to improve its predictions.

**Inference** is the process of using a trained model to make predictions on new data. The model applies what it has already learned to produce an output.

| Training | Inference |
|---|---|
| The model learns patterns from training data. | The trained model uses learned patterns to make predictions. |
| Parameters are adjusted to reduce the loss. | Learned parameters are used to process new inputs. |
| Training examples and target answers are used in supervised learning. | New input data is provided to the trained model. |
| It may require many iterations. | It produces a prediction after processing an input. |
| Example: Learning from chip frequency and power data. | Example: Predicting the power consumption of a new chip. |

## How Model Outputs Are Compared with Target Answers During Training
During supervised training, a model receives input examples and produces predictions. When the correct target answers are available, the predictions are compared with those targets to measure how far the model's outputs are from the expected results.

For example, suppose a model predicts the power consumption of a semiconductor chip. If the actual power consumption is known, we can compare the predicted value with the actual value and calculate the error.

| Step | Process | Explanation |
|---|---|---|
| 1 | Input Data | The model receives training examples. |
| 2 | Initial Parameters | The model starts with initial parameter values. |
| 3 | Prediction | The model produces predictions from the input data. |
| 4 | Error Calculation | The predictions are compared with the target values. |
| 5 | Loss Function | A loss function measures the prediction error. |
| 6 | Optimisation | The model's parameters are adjusted to reduce the loss. |
| 7 | Repetition | The process repeats until a suitable stopping point is reached. |
| 8 | Trained Model | The model is ready to make predictions on new data. |

## Explain the Intuition Behind Loss/Error Measures and Optimisation

A loss function measures how far a model's predictions are from the correct target values. It provides a way to evaluate how well the model is performing during training.

For example, if a model predicts a chip's power consumption as 8 watts when the actual value is 10 watts, the absolute error is 2 watts.

An optimisation process adjusts the model's learned parameters to reduce the loss. It tries to find parameter values that make the model's predictions fit the training data better.

The process can be understood in five simple steps:

1. The model makes a prediction.
2. The prediction is compared with the correct answer.
3. A loss or error measure indicates how far the prediction is from the target.
4. The optimisation method adjusts the model's parameters.
5. The model repeats the process to improve its predictions.

| Concept | Purpose |
|---|---|
| Prediction | The output produced by the model for an input. |
| Target | The correct answer provided in the training data. |
| Error | The difference between a prediction and its target. |
| Loss Function | Measures prediction error using a defined calculation. |
| Optimisation | Updates the model's parameters to reduce the loss. |
| Parameters | Values learned by the model during training. |

## Linear Regression 

Linear Regression is a supervised Machine Learning method used to predict a numerical value by learning a relationship between input features and known numerical outcomes.
It tries to find a straight line that represents the relationship between the inputs and outputs as closely as possible.

The basic equation is: **y = mx + b**
Where:
- **x** = Input feature
- **y** = Predicted numerical output
- **m** = Learned slope
- **b** = Learned intercept

During training, the algorithm uses example inputs and their actual numerical outcomes to learn suitable values for the slope and intercept. During inference, the trained model uses these learned parameters to estimate the outcome for a new input.

### Example: Predicting Semiconductor Chip Power Consumption

Suppose we want to estimate chip power consumption based on operating frequency.

| Input (Chip Frequency) | Target Output (Power Consumption) |
|---|---|
| 1.0 GHz | 5 W |
| 1.5 GHz | 7 W |
| 2.0 GHz | 9 W |
| 2.5 GHz | 11 W |

The algorithm learns a relationship between frequency and power consumption from these training examples. The trained model can then estimate power consumption for a new frequency.

example  the relationship is:
**Power (W) = 4 × Frequency (GHz) + 1**
For a new input of 3.0 GHz:
**Predicted Power = 4 × 3.0 + 1 = 13 W**
This is an illustrative example, not a measured semiconductor result. Real semiconductor power consumption can also depend on voltage, workload, temperature, and chip design, so a single input may not always provide an accurate prediction.

Linear Regression is useful when a numerical outcome can be reasonably approximated by a linear relationship.

##  Labelled Flow Diagram: From Examples to an Inference Result

The following flow diagram shows how data moves through the training and inference stages of a Machine Learning system.

```text
              TRAINING PHASE
                     |
                     v
        +--------------------------+
        | Training Examples        |
        | Inputs + Target Answers  |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Learning Algorithm       |
        | Learns from Examples     |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Model Makes Predictions  |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Compare Predictions      |
        | with Target Answers      |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Loss Function            |
        | Measures Prediction Error|
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Optimisation             |
        | Updates Parameters       |
        +--------------------------+
                     |
                     v
             Repeat Training
             to Reduce Loss
                     |
                     v
        +--------------------------+
        | Trained Model            |
        | Learned Parameters       |
        +--------------------------+
                     |
                     v
              INFERENCE PHASE
                     |
                     v
        +--------------------------+
        | New Input Data           |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Trained Model            |
        | Uses Learned Parameters  |
        +--------------------------+
                     |
                     v
        +--------------------------+
        | Prediction / Estimate    |
        +--------------------------+
```

### Explanation of the Labelled Flow Diagram

**1. Training Examples:** The process starts with training data containing input features and their corresponding target answers.

**2. Learning Algorithm:** The algorithm uses the training examples to learn patterns and relationships between inputs and targets.

**3. Model Makes Predictions:** The model generates predictions using its current parameter values.

**4. Compare Predictions with Target Answers:** The predicted values are compared with the actual target values to determine the prediction error.

**5. Loss Function:** A loss function measures how far the predictions are from the target values.

**6. Optimisation:** An optimisation method adjusts the model's parameters to reduce the loss.

**7. Repeat Training:** Prediction, loss calculation, and parameter updates are repeated until a suitable stopping condition is reached.

**8. Trained Model:** After training, the model contains learned parameter values that represent patterns found in the training data.

**9. Inference Phase:** New input data is provided to the trained model. The model uses its learned parameters to process the input.

**10. Prediction / Estimate:** The final output is a prediction for the new input, such as an estimated chip power consumption.

The diagram represents a common supervised learning process. The exact learning and optimisation methods can differ between algorithms.

## Conclusion

The anatomy of an ML model includes training data, a learning algorithm, learned parameters, a loss function, and an optimisation process. These components work together to produce a trained model.
Training helps the model learn patterns and reduce prediction errors, while inference uses the trained model to predict outcomes for new inputs. Linear Regression is a simple example of how a model learns a relationship between input features and numerical results.

##  Sources
Google Machine Learning Crash Course — Linear Regression:
https://developers.google.com/machine-learning/crash-course/linear-regression

Google Machine Learning Crash Course — Loss:
https://developers.google.com/machine-learning/crash-course/linear-regression/loss

scikit-learn — Linear Models
https://scikit-learn.org/stable/modules/linear_model.html

