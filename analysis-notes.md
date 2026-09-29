# CO₂ Emissions Root Cause Analysis — Analysis Notes

## 1. Project Objective

The objective of this analysis is to investigate the factors associated with vehicle CO₂ emissions using Microsoft Power BI.

The analysis focuses on identifying relationships between CO₂ emissions and the following vehicle characteristics:

* Engine Size (cm3)
* Powertrain
* Transmission
* Fuel Type

---

## 2. Dataset

The analysis uses a `Vehicles` table containing information about individual vehicles.

### Main fields

| Field               | Description                   |
| ------------------- | ----------------------------- |
| `car_id`            | Unique vehicle identifier     |
| `CO2 emission`      | Vehicle CO₂ emission          |
| `Engine Size (cm3)` | Engine displacement           |
| `Powertrain`        | Vehicle propulsion technology |
| `Transmission`      | Transmission type             |
| `Fuel Type`         | Fuel category                 |

---

## 3. Dataset Scope

A KPI card was created to count the number of vehicles included in the analysis.

### Configuration

```text
Field: car_id
Aggregation: Count
Title: Vehicles analyzed
```

The KPI provides an immediate overview of the dataset size.

---

## 4. Key Influencers Analysis

The Power BI **Key Influencers** visual was used to investigate factors associated with CO₂ emissions.

### Analyze

```text
CO2 emission
```

### Explain by

```text
Engine Size (cm3)
Transmission
Fuel Type
Powertrain
```

The visual automatically evaluates relationships between the target metric and the explanatory variables.

This analysis was used as the starting point for identifying potentially important vehicle characteristics.

---

## 5. Engine Size Analysis

A scatter plot was created to investigate the relationship between engine size and average CO₂ emissions.

### Configuration

```text
X-axis: Engine Size (cm3)
Y-axis: Average of CO2 emission
```

Average CO₂ emission was selected instead of the sum to compare typical emission levels across engine sizes.

This visualization complements the Key Influencers analysis by providing a direct visual representation of the relationship.

---

## 6. Top Segments Analysis

Power BI's **Top Segments** functionality was used to identify combinations of attributes associated with differences in CO₂ emissions.

The analysis highlighted dimensions such as:

* Engine Size
* Powertrain
* Transmission

This step allowed the analysis to move from individual explanatory variables toward combinations of characteristics.

---

## 7. Powertrain and Transmission Analysis

A dedicated visualization was created to compare CO₂ emissions across powertrain and transmission categories.

### Configuration

```text
Axis: Powertrain
Legend: Transmission
Value: CO2 emission
```

This visualization makes it possible to compare different propulsion technologies while considering transmission type.

---

## 8. Fuel Type Analysis

Fuel Type was analyzed to understand how emissions are distributed across fuel categories.

### Configuration

```text
Legend: Fuel Type
Values: CO2 emission
```

A donut chart was selected because the analysis involved a relatively small number of fuel categories.

The visualization provides a high-level view of the contribution of each fuel category to total emissions represented in the dataset.

---

## 9. Decomposition Tree

A Power BI **Decomposition Tree** was created to allow interactive exploration of average CO₂ emissions.

### Analyze

```text
Average CO2 emission
```

### Explain by

```text
Engine Size (cm3)
Powertrain
Transmission
Fuel Type
```

The decomposition tree allows users to progressively drill down into different vehicle characteristics.

---

## 10. Engine Size Binning

The original `Engine Size (cm3)` field contains many possible values.

Using individual values directly in a decomposition tree can make the analysis difficult to navigate.

To improve usability, the engine size values were grouped into five equal-sized bins.

### Transformation

```text
Engine Size
       ↓
New Group
       ↓
5 equal-sized bins
```

The grouped field was then used instead of the original engine-size field in the decomposition tree.

### Purpose

The grouping makes it easier to identify broader engine-size ranges and reduces the complexity of the decomposition tree.

---

## 11. AI-Assisted Analysis

Power BI's AI-assisted functionality was used within the decomposition tree to explore branches associated with lower average CO₂ emissions.

The analysis started with:

```text
Powertrain
```

The **Low value** option was then used to identify branches with lower values of the analyzed metric.

An example analytical path was:

```text
Powertrain
      ↓
Low value
      ↓
Engine Size Group
      ↓
Low value
      ↓
Transmission
      ↓
Low value
```

This provides an interactive way of exploring combinations of vehicle characteristics associated with lower average CO₂ emissions within the dataset.

---

## 12. Visualization Selection

Each visualization was selected according to the analytical question.

| Question                                      | Power BI Visual    |
| --------------------------------------------- | ------------------ |
| How many vehicles are analyzed?               | KPI Card           |
| Which factors influence CO₂ emissions?        | Key Influencers    |
| How does engine size relate to emissions?     | Scatter Plot       |
| Which combinations of factors are relevant?   | Top Segments       |
| How do Powertrain and Transmission compare?   | Bar/Column Chart   |
| How are emissions distributed by fuel?        | Donut Chart        |
| How can emissions be explored hierarchically? | Decomposition Tree |

---

## 13. Analytical Workflow

The complete analysis followed this workflow:

```text
Data Exploration
       ↓
Dataset Scope
       ↓
Key Influencers
       ↓
Engine Size Analysis
       ↓
Top Segments
       ↓
Powertrain & Transmission
       ↓
Fuel Type Analysis
       ↓
Decomposition Tree
       ↓
Engine Size Binning
       ↓
AI-Assisted Analysis
       ↓
Final Dashboard
```

---

## 14. Main Observations

The analysis identified several dimensions that were useful for investigating differences in vehicle CO₂ emissions.

### Engine Size

Engine size was an important analytical dimension and was further investigated using a scatter plot and grouped bins.

### Powertrain

Powertrain was used extensively in the analysis and in the decomposition tree.

### Transmission

Transmission provided additional information when analyzed together with powertrain.

### Fuel Type

Fuel Type was useful for understanding the distribution of emissions across different fuel categories.

### Combined Factors

The analysis demonstrates that CO₂ emissions can be explored through combinations of:

```text
Engine Size
+
Powertrain
+
Transmission
+
Fuel Type
```

---

## 15. Power BI Skills Demonstrated

This project demonstrates practical experience with:

* Data exploration
* KPI creation
* Key Influencers
* Top Segments
* Decomposition Tree
* AI-assisted analysis
* Scatter plots
* Donut charts
* Category comparisons
* Data grouping
* Numerical binning
* Interactive report design
* Root cause analysis

---

## 16. Screenshots

The screenshots associated with this analysis are stored in:

```text
screenshots/
```

Main screenshots:

```text
01-data-exploration.png
02-key-influencers.png
03-engine-size-scatter.png
04-top-segments.png
05-powertrain-transmission.png
06-fuel-type.png
07-engine-size-binning.png
08-decomposition-tree.png
09-ai-low-value-analysis.png
10-final-dashboard.png
```

---

## 17. Final Outcome

The final Power BI report combines automated analytical capabilities with traditional visualizations to provide an interactive exploration of vehicle CO₂ emissions.

The report allows users to move from:

```text
General Overview
       ↓
Identifying Influencing Factors
       ↓
Exploring Relationships
       ↓
Finding Segments
       ↓
Investigating Root Causes
       ↓
Interactive Dashboard
```

The project demonstrates how Power BI can be used not only for reporting but also for exploratory analysis and root cause investigation.
