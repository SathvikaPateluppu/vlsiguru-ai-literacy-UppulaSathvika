# MISSION 8 — Does This Problem Actually Need ML?

## Research Question: When should an engineer use ML instead of a fixed rule or conventional program?

## Defining the Problem and Desired Outcome

**Problem:** Identify whether a semiconductor chip is operating within its safe temperature limit.

**Desired outcome:** Detect unsafe temperatures and alert the engineer before the chip exceeds its specified temperature limit.

The engineer should first understand the problem, the available inputs, the required output, and the consequences of an incorrect decision.

## Rule-Based Solution vs ML Solution

### Rule-Based Solution

A rule-based system follows predefined conditions written by a programmer.

### Machine Learning Solution

A machine learning model learns patterns from historical data and uses them to make predictions.

## Comparison of Rule-Based and ML Solutions

| Aspect | Rule-Based Solution | ML Solution |
|---|---|---|
| Working Method | Follows predefined rules and conditions. | Learns patterns from training data. |
| Data Requirements | Usually needs the relevant inputs and known thresholds; a training dataset is not required. | Requires suitable, representative training data and reliable target labels or learning signals. |
| Complexity | Simple to develop when conditions are clear. | Can be more complex to develop, train, and maintain. |
| Best Use Case | Problems with clear rules and fixed limits. | Problems involving complex patterns that are difficult to describe using fixed rules. |
| Adaptability | Changes require manually updating the rules. | Can adapt through retraining with appropriate new data. |
| Explainability | Usually easy to understand and trace. | Depends on the model and may be harder to explain. |
| Cost | Often lower development and maintenance costs for simple problems. | May require more computing resources, data collection, testing, and monitoring. |
| Failure Modes | Incorrect thresholds, missing conditions, or programming errors. | Biased or poor-quality data, overfitting, data drift, and incorrect predictions. |
| Evaluation | Check whether the rules meet the required specifications. | Evaluate using suitable metrics and independent test data. |
| Safety | Clear rules can enforce known limits, but implementation errors are still possible. | Predictions may be wrong, so important decisions may need independent safety checks. |

## When we should choose Rule-Based Programming

A rule-based solution is suitable when:

- The problem has clear and well-defined conditions.
- Fixed thresholds are sufficient to achieve the desired result.
- The required behaviour can be described using simple rules.
- Reliable training data is unavailable.
- The system needs predictable behaviour that is easy to verify.

**Example:** Generating an alert whenever a measured chip temperature exceeds a specified maximum limit.

For this problem, a simple rule may be sufficient. ML is not automatically necessary.

## When we should Choose Machine Learning

ML may be suitable when:

- The problem contains complex patterns that are difficult to express as fixed rules.
- Sufficient, relevant, and reliable data is available.
- The model can learn useful relationships from historical examples.
- The model's predictions provide value beyond a simple baseline.
- The expected benefits justify the additional development and maintenance costs.

**Example:** Predicting the likelihood of chip overheating several minutes in advance using workload, voltage, current, temperature trends, and cooling information.

An ML model may identify patterns that a single temperature threshold cannot capture. However, it must be evaluated to determine whether it actually improves prediction quality.

## How Can We Measure Success?

Success can be measured by checking whether the solution meets the required objectives, produces correct results, and works reliably under real-world conditions.

| Evaluation Metric | Rule-Based Solution | ML Solution |
|---|---|---|
| Correctness | Check whether the programmed rules produce the expected result. | Compare model predictions with actual outcomes. |
| Accuracy | Check whether the system correctly identifies conditions such as temperature exceeding a specified limit. | Measure the proportion of correct predictions. |
| False Alarms | Count how often the system generates unnecessary alerts. | Measure how often the model predicts overheating when it does not occur. |
| Missed Events | Count how often the rules fail to detect an actual overheating event. | Measure how often the model fails to detect actual overheating events. |
| Response Time | Measure how quickly the system detects a condition and generates an alert. | Measure how quickly the model produces a prediction. |
| Reliability | Test whether the rules work correctly across the required operating conditions. | Test whether model performance remains consistent across different workloads and operating conditions. |
| Safety | Verify that the system follows the required temperature limits and protection procedures. | Verify that predictions meet safety requirements and use independent protection mechanisms where needed. |

## What Happens If a Prediction Is Incorrect?

Incorrect predictions can have different consequences.

| Type of Error | Possible Consequence | Possible Control |
|---|---|---|
| False Alarm | Unnecessary alerts, inspections, or production delays. | Tune thresholds or improve the model using verified data. |
| Missed Overheating Event | Chip damage, reduced reliability, or a safety risk. | Use independent temperature limits and hardware protection. |
| Incorrect ML Prediction | Engineers may make decisions based on unreliable results. | Validate predictions and require human review for high-risk decisions. |
| Unexpected Operating Conditions | The model may perform poorly on conditions it has not learned. | Monitor performance and test across different conditions. |

For safety-critical systems, an ML prediction should not replace mandatory protection mechanisms unless the complete system has been appropriately validated and approved.

## Trade-Offs and Final Decision

For the chip temperature problem, the best solution depends on what the engineer wants to achieve.

- If the goal is to alert when the measured temperature exceeds a known limit, a rule-based solution is simpler and more predictable.
- If the goal is to predict overheating before the temperature reaches the limit, ML may provide additional value by learning patterns from historical measurements.
- A hybrid solution can use ML for early warnings and fixed rules or hardware protection for enforcing known safety limits.

Therefore, the engineer should begin with the simplest solution that meets the requirements. ML should be selected only when it provides measurable benefits that justify its additional complexity.

## Conclusion

Machine learning is not necessary for every engineering problem. Rule-based programming is often better when the problem has clear conditions and fixed limits. ML is useful when reliable data is available and the problem involves complex patterns that are difficult to express through conventional rules.

Before choosing ML, an engineer should define the problem, assess data availability, establish success metrics, consider the consequences of incorrect predictions, and compare the model against a simple baseline.

In VLSI and semiconductor engineering, combining ML with conventional programming and independent safety checks can be more effective than relying on ML alone.

## Sources

1. Google Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
2. scikit-learn — Choosing the right estimator: https://scikit-learn.org/stable/machine_learning_map.html
3. NIST — Artificial Intelligence Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework

## Verification Note

The temperature values and scenarios in this mission are illustrative examples. The actual thresholds, data requirements, and evaluation criteria should be selected according to the device specifications and engineering requirements.

