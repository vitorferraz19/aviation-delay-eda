# What Flight Delay Patterns Reveal About Operational Pressure

## Exploratory Data Analysis of Airline Delay Patterns Using Public BTS Data

This project explores airline delay patterns using public Bureau of Transportation Statistics (BTS) Reporting Carrier On-Time Performance data from **January 2023**.

The goal is not to rank airlines or assign delay responsibility to any single function. Instead, this analysis uses exploratory data analysis (EDA) to understand how operational pressure becomes visible through delay distributions, delay-cause categories, and operator-level delay profiles.

The project is designed as a portfolio EDA demonstrating Python, Pandas, data cleaning, statistical exploration, data visualisation, and operational interpretation in an aviation context.

---

## Project Objective

Airline operations are complex, tightly connected systems. Delays do not always behave as isolated events; they can concentrate, propagate, and appear differently across operating contexts.

The main question explored in this project is:

> **Which types of delays dominate airline operations, and what do they reveal about operational pressure?**

To answer this, the analysis focuses on four guiding questions:

1. **How are delay values distributed, and is disruption concentrated in a small number of flights?**
2. **Which delay causes account for the largest share of total delay?**
3. **Do delay patterns differ across operators?**
4. **What do these patterns reveal about operational pressure?**

---

## Dataset

The analysis uses public data from the:

**Bureau of Transportation Statistics (BTS)**  
**Reporting Carrier On-Time Performance Dataset**  
Period analysed: **January 2023**

The dataset includes flight-level delay information and broad delay-cause categories, including:

- Arrival delay
- Departure delay
- Carrier delay
- Weather delay
- National Aviation System (NAS) delay
- Security delay
- Late aircraft delay

The raw BTS data is not included in this repository. It can be downloaded directly from the BTS TranStats platform.

Dataset source:  
https://www.transtats.bts.gov/

---

## Scope and Framing

This analysis should be interpreted within the context of the **January 2023 BTS dataset** used for the project.

It does **not** attempt to:

- identify root causes at maintenance, Tech Ops, CAMO, or reliability level
- assign responsibility to individual functions
- rank operators by performance
- make universal claims about all airline operations

Instead, it explores how public delay data can support better operational questions, such as:

- where disruption appears to concentrate
- which delay categories dominate
- how delay profiles differ across anonymised operators
- how delay patterns may reflect operational pressure in a connected system

Operators are anonymised in the public notebook to keep the focus on patterns rather than brand-level comparison.

---

## Tools and Libraries

This project uses:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

Main techniques demonstrated:

- data loading and inspection
- missing-value handling
- dataframe copying and cleaning
- univariate analysis
- categorical vs numerical analysis
- summary statistics
- skewness and variability analysis
- grouped aggregation
- percentage-share calculations
- visualisation with bar charts and histograms
- operational interpretation of data patterns

---

## Analysis Structure

The notebook is organised as follows:

~~~text
1. Introduction
2. Data Loading and Overview
3. Data Cleaning
4. Exploratory Data Analysis
   4.1 Delay Distribution
   4.2 Delay Types Analysis
   4.3 Operator-Level Delay Comparison
5. Key Findings
6. Operational Interpretation
7. Conclusion and Possible Next Steps
~~~

---

## Key Findings

### 1. Delay values are highly unevenly distributed

Delay values are not evenly spread across all flights. Most flights record low or zero delay minutes, while a smaller number of flights account for much larger delay values.

This is visible through:

- low or zero medians
- means higher than medians
- strong positive skewness
- high maximum values

This suggests that disruption is concentrated in a minority of flights rather than spread evenly across the operation.

---

### 2. Total delay is concentrated in a small number of delay causes

In the January 2023 dataset, total delay is not evenly distributed across all delay categories.

The largest contributors are:

1. **Late Aircraft delay**
2. **Carrier delay**
3. **NAS delay**

The remaining categories contribute comparatively less.

This pattern suggests that a significant portion of delay is associated with propagation effects across aircraft rotations and broad operator-controlled categories.

---

### 3. Delay-cause profiles differ across anonymised operators

The operator-level comparison shows that different anonymised operators have different delay-cause profiles.

This suggests that delay behaviour is not uniform across all operating contexts. Differences may reflect:

- network structure
- scheduling design
- operational exposure
- recovery margins
- resource availability
- exposure to external system pressures

---

## Operational Interpretation

The analysis suggests that operational pressure does not appear evenly across airline operations. It tends to concentrate in specific flights, specific delay categories, and different operator profiles.

The skewed delay distributions show that a relatively small number of disrupted flights can carry a disproportionate share of total delay. From an operational perspective, this matters because average values alone can hide where disruption is actually concentrated.

The delay-cause analysis also suggests that delay should not be interpreted only as an isolated event. Some delay categories, especially those linked to aircraft arriving late from previous sectors, can reflect propagation effects across rotations.

The operator-level comparison reinforces this point. Different anonymised operators show different delay-cause profiles, which suggests that operational pressure may be shaped by operating context rather than by one universal factor.

The value of this analysis is to show how public operational data can support better questions:

- Where does disruption concentrate?
- Which delay categories dominate?
- How do operating profiles differ?
- Where might further analysis be useful?

---

## Visualisations

The notebook includes:

- Histograms of arrival and departure delay distributions
- Log-scale histograms for delay-cause distributions
- Percentage-share chart of total delay by cause
- Stacked bar chart showing delay-cause profiles by anonymised operator
- Summary tables for delay causes and operator profiles

Visualisation choices were made to improve readability while preserving the underlying data. For example, some histograms are zoomed to the 1st–99th percentile range for readability, while full-range values remain available in the summary statistics.

---

## Limitations

This project is intentionally scoped as an early-stage exploratory analysis.

Key limitations:

- The analysis only covers **January 2023**
- The dataset contains broad BTS delay categories, not detailed operational root causes
- Operator identities are anonymised in the public notebook
- Time-of-day analysis is not included because the selected dataset fields do not contain the required time variables
- Airport-level and route-level analyses are not included in this version
- The analysis does not include predictive modelling or machine learning

These limitations are intentional to keep the project focused, interpretable, and appropriate for an EDA portfolio project.

---

## Possible Next Steps

Future analysis could extend this project by exploring:

- airport-level delay concentration
- route-level delay patterns
- time-of-day effects
- delay propagation across operating days
- comparison across multiple months
- early predictive modelling once additional features are included

These are possible future directions, not conclusions from the current analysis.

---

## How to Run the Notebook

1. Clone this repository:

~~~bash
git clone https://github.com/your-username/aviation-delay-eda.git
~~~

2. Install the required Python libraries:

~~~bash
pip install pandas numpy matplotlib seaborn jupyter
~~~

3. Download the BTS Reporting Carrier On-Time Performance data for January 2023 from:

~~~text
https://www.transtats.bts.gov/
~~~

4. Place the CSV file in the appropriate project folder.

5. Open the notebook:

~~~bash
jupyter notebook aviation_delay_patterns_eda.ipynb
~~~

6. Run the notebook from top to bottom.

---

## Repository Structure

Suggested structure:

~~~text
aviation-delay-eda/
│
├── README.md
├── notebooks/
│   └── aviation_delay_patterns_eda.ipynb
├── images/
│   └── selected_visualisations.png
└── data/
    └── data_source_instructions.md
~~~

The raw dataset is not included in this repository. Please download it directly from BTS.

---

## What This Project Demonstrates

This project demonstrates the ability to:

- structure an exploratory data analysis project
- clean and inspect public operational data
- use Pandas for grouped analysis and summary statistics
- create readable visualisations with Matplotlib and Seaborn
- interpret data patterns in an aviation operations context
- communicate findings clearly and respectfully
- connect technical analysis to operational decision-making

---

## Credits

Data source:

- Bureau of Transportation Statistics (BTS), Reporting Carrier On-Time Performance dataset

---

## License

This project is shared for portfolio and educational purposes.

If you reuse or adapt this work, please cite the original data source and respect the terms of use of the Bureau of Transportation Statistics dataset.
