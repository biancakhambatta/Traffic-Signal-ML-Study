# Traffic Signal ML Study
### To what extent can machine learning predict idle CO2 emissions at traffic signals?

> IB Extended Essay | Grade: A

---

## Overview

This project applies a supervised machine learning model to predict 
the idle CO2 emissions produced by vehicles waiting at traffic signals. 
It was submitted as an IB Extended Essay and graded A under IB assessment 
standards.

The analysis is motivated by a striking statistic: studies show that 
around 25% of drivers' exposure to harmful carbon emissions occurs at 
traffic lights, which make up only about 2% of their total travel time. 
Reducing idle time at signals is therefore one of the most efficient 
levers available for cutting urban carbon emissions.

---

## Research Question

**To what extent can machine learning be applied to traffic signals to 
predict the amount of idle carbon emissions released?**

---

## Dataset

- **Source:** traffic-signal-control.github.io
- **Coverage:** 23,204 vehicles passing one intersection across multiple 
  routes over a 12 hour period (8AM to 8PM)
- **Key variables:** vehicle speed, acceleration, deceleration, idling 
  time, route taken, fuel type

---

## Methodology

**Vehicle Specific Power (VSP)**
The analysis centres on the VSP formula, which estimates the power 
demanded from a vehicle engine at any given moment. VSP is calculated 
using instantaneous speed, acceleration, and road grade values:
vsp = speed * (a * accel + g * slope + b) + (c * speed^3)

Where a = 1.1, b = 0.132, c = 0.000302 and g = 0.132 (Jimenez 1999).

**CO2 Emissions Calculation**
Using VSP mode values and fuel consumption rates, CO2 emissions per 
litre of petrol are calculated for each vehicle record. One litre of 
petrol produces approximately 2,392 grams of CO2 under full oxidation.

**K-Nearest Neighbor Regression**
A KNN regression model was trained on the top three predictive 
variables: time of day, idling duration, and fuel consumption rate. 
The optimal K value was determined through iterative testing.

---

## Results

| Dataset | Accuracy |
|---|---|
| Training data | 99.80% |
| Testing data | 99.79% |

The model demonstrated that machine learning can reliably predict idle 
CO2 emissions at traffic signals given sufficient training data. The 
strongest correlation was found between idling duration and emissions 
output, reinforcing the case for smart signal timing systems that 
minimise vehicle wait times.

---

## Key Findings

- A KNN regression model achieved 99.79% accuracy on unseen test data
- Idling time is the single strongest predictor of CO2 emissions at 
  a traffic signal
- Vehicles travelling at higher speeds immediately before stopping 
  produce significantly more emissions due to greater engine workload
- Fuel type (petrol vs diesel) materially affects emission levels 
  across identical driving conditions
- The model supports the case for smart traffic signal systems and 
  in-vehicle intelligent transport systems as tools for reducing 
  urban carbon footprints

---

## Tools and Libraries

| Tool | Purpose |
|---|---|
| Python | Core analysis language |
| Pandas | Data manipulation and processing |
| NumPy | Numerical computation and random simulation |
| Scikit-learn | KNN regression model and train/test split |
| Jupyter Notebook | Development environment |

---

## Project Structure

Traffic-Signal-ML-Study/

│

├── Traffic_Lights-Updated.ipynb    # Full analysis notebook

├── traffic_data_12_hours.csv       # Vehicle dataset

├── EE_Traffic_Signals.pdf          # Full research paper

└── README.md                       # You are here

---

## Research Paper

The full IB Extended Essay documenting the theoretical framework, 
methodology, analysis and conclusions is included in this repository.

[Read the paper](EE_BAK.pdf)

---

## About

Built by **Bianca Khambatta** as part of the IB Diploma Programme.
Graded A under IB Extended Essay assessment criteria.

[LinkedIn](https://www.linkedin.com/in/bianca-khambatta-4b8a37400) · 
[GitHub](https://github.com/biancakhambatta)
