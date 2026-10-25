# Week 3 — AI Tools Exploration

## 1. Objective
The objective of this activity is to explore AI tools for learning and engineering tasks, improve prompts by adding context and constraints, compare AI-generated explanations, and verify important technical claims using reliable sources.

## 2. AI Tools Explored

| **AI Tool** | **Purpose** | **Observation** |
|---|---|---|
| ChatGPT | Explaining concepts, improving prompts, and generating practice questions | Provides structured explanations and can break complex concepts into simpler steps |
| Gemini | Exploring concepts, comparing explanations, and supporting research | Can provide alternative explanations and help explore technical topics |
| Claude | Reviewing longer text, explaining concepts, and summarising information | Can be useful for detailed explanations and analysing longer documents |

## 3.Prompt Improvement Experiment
### Prompt 1 — Basic Prompt
**Prompt:**

Explain machine learning.

**Observation:**

This prompt gives a general explanation of machine learning. It does not specify my background, knowledge level, or the type of example I need.

### Prompt 2 — Context Added

**Prompt:**

I am an ECE graduate learning VLSI Physical Design. Explain machine learning with one example from semiconductor design.

**Observation:**

This prompt provides information about my educational background and learning track. It asks for a beginner-friendly explanation and a semiconductor-related example.

## Prompt 3 — Context, Constraints and Output Format

**Prompt:**

I am a beginner in AI and learning VLSI Physical Design. Explain machine learning. Use a small semiconductor example, a step-by-step explanation, a comparison with rule-based programming. Avoid advanced mathematics.

**Observation:**

This prompt provides context, specifies the difficulty level, sets constraints, and requests a particular output format. It helps me focus on the concepts I need to learn.

### Overall Observation

Prompt 3 is expected to provide the most structured and relevant response because it clearly specifies the context, constraints, and expected output. The actual responses should be compared to determine whether these improvements made the explanation more useful.
## 4. Comparing Three AI Tools

**Prompt used for comparison:**

"Explain the difference between supervised learning and unsupervised learning, with one semiconductor engineering example for each. Use beginner-friendly language. For each approach, explain the type of data required, how it learns, and what output it produces. Include one limitation of each approach. Do not invent experimental results, and provide reliable sources for factual claims."

### Comparison Table

| **Factor** | **ChatGPT** | **Gemini** | **Claude** |
|---|---|---|---|
| Clarity | Can organise concepts into simple explanations and comparison tables | Can explain concepts using structured explanations and bullet points | Can provide detailed explanations with supporting context |
| Supervised learning example | Predicting whether a design is likely to meet timing requirements using labelled historical data | Classifying wafer defects using labelled inspection data | Classifying wafer defect patterns using labelled examples |
| Unsupervised learning example | Grouping chip designs according to congestion and utilization patterns | Identifying unusual patterns in wafer inspection data | Clustering similar wafer maps to identify patterns |
| Main strength | Structured explanations and step-by-step learning support | Alternative explanations and exploration of technical topics | Detailed explanations and analysis of longer text |
| Limitation to consider | Technical answers still require independent verification | Generated explanations and cited sources need to be checked | Detailed explanations may still contain errors or unsupported claims |
| Verification | Check important claims against official documentation | Check sources for relevance and reliability | Check technical claims against original sources |

### Observations

The three AI tools can support learning by explaining technical concepts in different ways. ChatGPT can help organise information into a structured explanation, Gemini can provide an alternative explanation of the same topic, and Claude can help explore concepts in greater detail.

For the semiconductor examples, supervised learning can be used to predict timing outcomes from labelled design-run data or classify wafer defects using labelled inspection data. Unsupervised learning can be used to group similar design runs or identify unusual patterns in wafer inspection data.

These are illustrative engineering applications, not experimental results produced by the tools. Their suitability depends on the available data, the problem being investigated, and proper evaluation.

The usefulness of each tool should be judged by comparing its actual response, checking the technical details, and examining whether its sources support the claims. No AI tool should be assumed to be correct simply because its explanation sounds convincing.

### Conclusion

I learned that different AI tools can provide different explanations of the same technical concept. Comparing their responses helps me identify useful explanations, examples, and areas that require further verification.

A clear prompt that includes context, constraints, and the required output format can make AI responses more relevant. AI tools can support engineering learning, but their answers must be checked against reliable sources before being used for technical decisions.

## 5. Verification of an AI-Generated Claim

**Claim checked:**

OpenROAD supports digital chip physical-design implementation.

**Verification source:**

OpenROAD Official Documentation  
https://openroad.readthedocs.io/en/latest/main/README.html

**Verification method:**

I checked the official documentation to understand the purpose of OpenROAD and identify the physical-design operations supported by the tool.

**Finding:**

The documentation describes OpenROAD as an open-source digital-design application and provides information about its physical-design capabilities and workflow.

**Conclusion:**

The official documentation supports the claim that OpenROAD is used for digital physical-design implementation. This demonstrates why technical claims generated by AI should be checked against original documentation before being accepted as correct.

## 6. Responsible AI Use

AI-generated explanations are useful starting points for learning, but important technical claims should be checked against reliable sources. I should review AI-generated content critically, test code before using it, and avoid uploading confidential RTL, netlists, timing constraints, or proprietary design data to public AI tools.

## Summary

This activity helped me understand how AI tools can support technical learning, how prompt improvement can make answers more relevant, and why independent verification is important. By exploring AI tools and investigating an open-source VLSI tool, I can develop better learning habits and apply AI more responsibly to Physical Design.


