
# Week 04 — Neural Network Playground Experiment

**Name:** Uppula Sathvika  
**Track:** Physical Design (PD)  
**Background:** B.Tech Graduate in Electronics and Communication Engineering (ECE)  
**Program:** VLSIGuru AI Literacy Layer — 16-Week Program  
**Week:** 04

## 1. Objective

The objective of this experiment is to understand how a neural network learns by changing its architecture and observing how its predictions improve or change.

I used TensorFlow Playground to explore how hidden layers, neurons, and learning rate influence neural network training.

## 2. Tool Used

**TensorFlow Playground:**  
https://playground.tensorflow.org/

This interactive tool helps visualize how a neural network learns patterns from data.

## 3. Experiment 1 — Baseline Configuration

I started with a simple neural network configuration to understand the basic learning process.

| Parameter | Configuration |
|---|---|
| Dataset | Circle |
| Problem type | Classification |
| Input features | X1 and X2 |
| Hidden layers | 1 |
| Neurons | 4 |
| Activation function | Tanh |
| Learning rate | 0.03 |
| Regularization | None |

### Baseline Understanding

- The input features are passed into the neural network.
- The hidden layer processes the input data.
- The output layer predicts the class.
- The network adjusts its weights during training to reduce prediction errors.

## 4. Experiment 2 — Modified Configuration

For the second experiment, I increased the complexity of the neural network by adding another hidden layer.

| Parameter | Configuration |
|---|---|
| Dataset | Circle |
| Problem type | Classification |
| Input features | X1 and X2 |
| Hidden layers | 2 |
| Neurons | 4 in each layer |
| Activation function | Tanh |
| Learning rate | 0.03 |
| Regularization | None |

### Modified Experiment Understanding

Adding another hidden layer gives the network additional processing capacity to learn patterns from the input data.

I compared this configuration with the baseline network to understand the effect of network architecture.

### Observation

- The modified network has more trainable connections.
- Additional hidden layers can help a network learn more complex patterns.
- More layers do not automatically guarantee better performance.
- Training results also depend on the dataset, learning rate, and network configuration.

## 5. Comparison Between Both Experiments

| Feature | Baseline | Modified |
|---|---|---|
| Hidden layers | 1 | 2 |
| Neurons per layer | 4 | 4 |
| Activation | Tanh | Tanh |
| Learning rate | 0.03 | 0.03 |
| Network complexity | Lower | Higher |
| Learning capacity | Simpler architecture | More processing capacity |

## 6. Connection to Physical Design

Neural networks can be explored for possible applications in VLSI Physical Design.

For example, a machine learning model could be investigated for predicting congestion hotspots during placement.

Possible input features include:

- Placement density
- Number of cells
- Available routing resources
- Cell distribution
- Local congestion information

The model could learn relationships between these input features and congestion risk.

However, the model's predictions must be validated using actual design data and Physical Design tools.

## 7. What I Learned

Through this experiment, I understood:

1. A neural network learns by adjusting weights and biases.
2. Hidden layers help process input features and learn patterns.
3. Increasing the number of hidden layers increases network complexity.
4. The learning rate affects how the network updates its weights.
5. A complex network does not always produce better results.
6. Training and testing are important for evaluating model performance.

## 8. Limitations

- TensorFlow Playground provides a simplified learning environment.
- Its datasets are not actual VLSI design datasets.
- Results from this experiment cannot directly prove performance in Physical Design.
- Real-world applications require suitable training data and validation.

## 9. Conclusion

This experiment helped me understand the basic working of neural networks and the role of hidden layers in learning patterns.

By comparing a simple network with a network containing additional hidden layers, I understood that neural network architecture influences learning capacity.

I also learned how machine learning concepts could be explored in Physical Design applications, such as congestion prediction.

## 10. Reference

- TensorFlow Playground: https://playground.tensorflow.org/
- Google Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course

