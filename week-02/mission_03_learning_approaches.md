# Mission 3 — Understand the Main ML Approaches
## Research question: How does a system learn when it has labels, no labels, or feedback from actions

## Comparison table

| Learning Approach | Training Signal | What It Produces | One Limitation | Example |
|---|---|---|---|---|
| Supervised Learning | Labelled data containing inputs and correct answers | A model that predicts a class or numerical value | Requires reliable labelled data | Predict whether a VLSI design meets timing |
| Unsupervised Learning | Unlabelled data without predefined target answers | Groups, patterns, or relationships in data | Discovered patterns may be difficult to interpret | Group similar VLSI design runs based on congestion |
| Reinforcement Learning | Rewards or penalties received after taking actions | A policy for selecting actions to maximise long-term reward | Training may require many trials and can be costly | Learn placement strategies in a simulated chip-design environment |
| Self-Supervised Learning | Targets automatically generated from the data itself | A model that learns useful patterns or representations | The training task may not capture everything needed for the final task | Predict a missing word in a sentence |

## Supervised Learning

Supervised learning uses labelled examples to learn the relationship between inputs and known outputs. After training, the model can predict outcomes for new inputs.

### Diagram

```text
Labelled Data
      |
      v
Input Features + Correct Answers
      |
      v
ML Model Learns Patterns
      |
      v
Prediction for New Data
```
### Example
In VLSI Physical Design, a model can learn from previous design runs containing cell count, estimated delay, and the known timing result. It can then predict whether a new design run may meet its timing target.

### When it is Suitable?

It is suitable when labelled examples are available and the goal is to predict a known outcome, such as a category or numerical value.

### Limitation
Obtaining accurate labels can take time and effort. Incorrect labels may cause the model to learn misleading patterns.

## Unsupervised Learning

Unsupervised learning uses data without predefined target labels. The model tries to discover patterns, similarities, or groups in the data.

### Diagram

```text
Unlabelled Data
      |
      v
ML Model Analyses Data
      |
      v
Finds Similarities and Patterns
      |
      v
Groups or Discovered Structure
```

### Example
A model can group VLSI design runs with similar congestion levels or cell counts without being told the correct group for each run.

### When it is Suitable?
It is suitable when data is available but predefined labels are missing, and the goal is to discover groups, patterns, or unusual observations.

### Limitation
The patterns or groups discovered by the model may not have an obvious practical meaning and may require further analysis.

## Reinforcement Learning
Reinforcement learning involves an agent that interacts with an environment. The agent takes actions and receives rewards or penalties. Over time, it learns a strategy to maximise long-term reward.

### Diagram

```text
Agent
  |
  v
Takes an Action
  |
  v
Environment Responds
  |
  v
Reward or Penalty
  |
  v
Agent Improves Its Strategy
  |
  +----------> Repeats the Process
```
### Example
An agent could try different placement actions in a simulated VLSI design environment. It could receive rewards for improving a chosen objective, such as timing, while respecting area constraints.

### When it is Suitable?
It is suitable when a problem involves sequential decisions, actions, and feedback, and the system needs to improve its decisions through experience.

### Limitation
Training can require many interactions and may be expensive or risky if actions are performed in a real environment rather than a simulator.

## Self-Supervised Learning
Self-supervised learning creates training targets automatically from the data itself. It does not require a person to manually label every training example.

### Diagram

```text
Unlabelled Data
      |
      v
Create a Prediction Task
      |
      v
Generate a Target from the Data
      |
      v
Model Predicts the Target
      |
      v
Model Learns Patterns
```
### Example
Consider the sentence: "The chip is working well."

A word can be hidden to create a training task: "The chip is working ____."

The model tries to predict the missing word, "well". The original sentence provides the target automatically.

### When it is Suitable?

It is suitable when large amounts of unlabelled data are available and useful training targets can be generated from the data itself.

### Limitation

The automatically generated training task may not teach the model everything required for a specific real-world task.

## When Should Each Approach Be Used?

| Situation | Suitable Approach | Reason |
|---|---|---|
| Predict an outcome using examples with known answers | Supervised Learning | The model learns from labelled examples. |
| Discover groups in data without known categories | Unsupervised Learning | The model identifies patterns without target labels. |
| Learn which actions produce better long-term results | Reinforcement Learning | The model learns from rewards and penalties. |
| Learn from large amounts of unlabelled data by generating prediction targets | Self-Supervised Learning | The data itself supplies the training targets. |

The approach depends on the problem, the available data, the training signal, and the desired result.

## Conclusion

Machine Learning systems learn in different ways depending on the information available. Supervised learning uses labelled answers, unsupervised learning discovers patterns in unlabelled data, reinforcement learning learns through actions and rewards, and self-supervised learning generates targets from the data itself.
Understanding these approaches helps us choose a suitable method for a problem. In VLSI Physical Design, they could support tasks such as timing prediction, design-run grouping, and exploring placement strategies.

## Sources

1. Google for Developers — Machine Learning
   https://developers.google.com/machine-learning/intro-to-ml/what-is-ml

2. IBM — Supervised vs. Unsupervised Learning
   https://www.ibm.com/think/topics/supervised-vs-unsupervised-learning

3. IBM — What Is Self-Supervised Learning?
   https://www.ibm.com/think/topics/self-supervised-learning
