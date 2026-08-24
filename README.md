# Application-of-Fuzzy-in-Quality-4.0
Quality 4.0 is the integration of quality management practices with Industry 4.0 technologies such as Artificial Intelligence (AI), Machine Learning (ML), Internet of Things (IoT), cloud computing, big data analytics, and cyber-physical systems. 
These technologies enable organizations to create quality systems that are predictive, adaptive, data-driven, and self-correcting, allowing problems to be identified and addressed before they affect production or product quality.
Maintenance is the set of activities performed to keep equipment and machinery operating efficiently, safely, and reliably throughout their service life. Effective maintenance minimizes breakdowns, reduces downtime, and improves productivity.
## Predictive Maintenance
Predictive Maintenance (PdM) is a maintenance strategy that uses equipment condition data, sensor measurements, and operational parameters to predict when a machine is likely to fail. Instead of performing maintenance at fixed intervals, maintenance activities are carried out only when indicators suggest a potential future failure.
## Objectives

- To design and develop a **Fuzzy Inference System (FIS)** for predictive maintenance.
- To use machine condition parameters as inputs and evaluate equipment health.
- To generate a **Maintenance Score (0–1)** indicating the maintenance requirement of the equipment.
- To support maintenance decision-making by handling uncertainty through fuzzy logic and expert knowledge.
## Methodology

### 1. Dataset Selection and Analysis
- The **AI4I 2020 Predictive Maintenance Dataset** containing **10,000 data points** was used for this project.
- Exploratory Data Analysis (EDA) was performed to understand the relationship between machine parameters and failures.
- Box plots were generated for **failure (1)** and **non-failure (0)** classes to identify parameter ranges associated with equipment failures.
- The insights obtained from this analysis were used to define the fuzzy membership functions.

### 2. Input Parameter Selection
- Relevant machine condition parameters were selected from the dataset based on their impact on machine failures.

### 3. Fuzzification
- Numerical input values were converted into linguistic variables such as **Low**, **Medium**, and **High**.
- Membership functions were designed using the parameter ranges observed during data analysis.

### 4. Rule Base Development
- A set of **IF–THEN** rules was developed using process knowledge and insights obtained from the dataset.
- These rules represent the relationship between machine conditions and maintenance requirements.

### 5. Fuzzy Inference
- The fuzzy inference engine evaluates the rules and combines the effects of all input parameters.

### 6. Defuzzification
- The fuzzy output is converted into a crisp **Maintenance Score** ranging from **0 to 1**.

### 7. Maintenance Decision
- The generated Maintenance Score is used to assess machine health and determine the urgency of maintenance actions.

## Workflow

```text
AI4I 2020 Dataset
        ↓
 Exploratory Data Analysis
 (Box Plot Analysis)
        ↓
 Input Parameter Selection
        ↓
      Fuzzification
 (Low, Medium, High)
        ↓
 Rule Base Development
        ↓
   Fuzzy Inference
        ↓
   Defuzzification
        ↓
 Maintenance Score (0–1)
        ↓
 Maintenance Decision
```
## Fuzzy Inference System Design

### Input Variables

The fuzzy model uses machine condition parameters obtained from the AI4I 2020 Predictive Maintenance Dataset:

- Air Temperature
- Process Temperature
- Rotational Speed
- Torque
- Tool Wear

These parameters were selected because of their influence on machine health and failure occurrence.

### Input Membership Functions

- Each input variable is divided into three linguistic categories:
  - Low
  - Medium
  - High
- Triangular membership functions are used.
- Membership ranges are defined using insights obtained from exploratory data analysis and box-plot visualization.

### Output Variable

The output of the fuzzy system is a **Maintenance Score** ranging from **0 to 1**.

| Score Range | Interpretation |
|------------|---------------|
| 0.0 – 0.4 | Healthy (Green) |
| 0.4 – 0.6 | Warning (Yellow) |
| 0.6 – 1.0 | Maintenance Required (Red) |

The Maintenance Score acts as an indicator of machine health and maintenance urgency.

---

## Rule Base

The fuzzy rule base was developed using process knowledge and machine behavior observed in the dataset.

A total of **9 fuzzy rules** were implemented in the final system.

Example rules include:

- IF Tool Wear is High THEN Maintenance is Red
- IF Tool Wear is High AND Torque is High THEN Maintenance is Red
- IF Speed is Low AND Torque is High THEN Maintenance is Red
- IF Process Temperature is High THEN Maintenance is Yellow
- IF Tool Wear is Medium THEN Maintenance is Yellow
- IF Speed is Low AND Tool Wear is Medium THEN Maintenance is Yellow
- IF Tool Wear is Low AND Torque is Low AND Process Temperature is Low THEN Maintenance is Green

The complete rule set combines expert knowledge with observed machine behavior to estimate maintenance requirements.

---

## Results and Analysis

### Data Analysis

Exploratory data analysis was performed using box plots to compare failure and non-failure observations.

Key observations:

- Certain parameter ranges exhibited a higher concentration of failure cases.
- Tool Wear and Torque showed strong relationships with machine failures.
- These observations were used while defining the membership functions and fuzzy rules.

### Fuzzy System Output

All data points from the AI4I 2020 dataset were evaluated using the developed fuzzy inference system.

The system generates a Maintenance Score between 0 and 1 for every observation.

### Interpretation of Results

- Most failure points received high Maintenance Scores.
- Several non-failure points also received elevated scores.
- This behavior is expected because the objective of the system is not strict failure classification.
- The goal is to provide an early indication of deteriorating machine conditions.
- Maintenance can therefore be planned before an actual failure occurs.

### Threshold-Based Maintenance Decision

A threshold value can be selected to identify machines requiring maintenance attention.

Example:

- Maintenance Score < 0.40 → Healthy
- 0.40 ≤ Score < 0.65 → Monitor Condition
- Score ≥ 0.65 → Maintenance Recommended

---

## Conclusion

This project demonstrates the application of Fuzzy Logic within the Quality 4.0 framework for predictive maintenance.

A fuzzy inference system was developed using machine condition parameters from the AI4I 2020 dataset. The model converts numerical measurements into linguistic variables and applies rule-based reasoning to generate a Maintenance Score between 0 and 1.

The results show that fuzzy logic can effectively incorporate process knowledge, handle uncertainty, and provide an interpretable maintenance indicator. Rather than predicting failures directly, the system provides an early warning signal that can support proactive maintenance planning and improve equipment reliability.

---

## Future Scope

- Integrate real-time IoT sensor data.
- Combine fuzzy logic with machine learning models.
- Optimize membership functions using data-driven techniques.
- Develop adaptive fuzzy systems with automatic rule tuning.
- Deploy the model as a web dashboard for real-time monitoring.
- Extend the system to different industrial assets and manufacturing environments.

---

## References

1. Timothy J. Ross, *Fuzzy Logic with Engineering Applications*, Wiley.
2. M. Mazzoleni et al., *Fault Diagnosis and Condition Monitoring of Industry 4.0 Manufacturing Processes*.
3. AI4I 2020 Predictive Maintenance Dataset, UCI Machine Learning Repository.
4. Research articles on fuzzy systems, predictive maintenance, and Quality 4.0.
