# Car Market & Vehicle Specifications Analysis | Excel

**Data Analytics Portfolio Project — Coders Lab**  
**Tools:** Microsoft Excel · XLOOKUP · IF · PivotTables · Descriptive Statistics · Pearson Correlation · Charts

## 📥 Open the Excel Project

**[View or download the complete Excel workbook](Cars_Analysis.xlsx)**

The workbook contains the original working sheets, data tables, calculated columns, formulas, PivotTables, and embedded charts. GitHub may not preview all Excel features; download the file and open it in Microsoft Excel to explore the full analysis.

## Project Overview

This project explores how automobile prices, vehicle specifications, fuel efficiency, model years, and drivetrain configurations vary across a dataset of **32,262 vehicle records**. The primary analysis table (`cars`) includes **29 columns**, with additional lookup tables for engine specifications and model names.

The analysis combines data enrichment, descriptive statistics, data aggregation, visualization and exploratory correlation analysis. It is a descriptive learning project, **not a predictive pricing or machine-learning model**.

## Questions Explored

- How many vehicle records are associated with each manufacturer, model year, and category?
- Which vehicle types and drivetrains have higher average MSRP or fuel economy?
- What is the distribution of engine displacement, horsepower, vehicle weight and range?
- How do MSRP and vehicle age relate in the available records?
- How strongly are horsepower, torque, engine displacement and other features associated with MSRP?
- What relationships appear between engine displacement and fuel efficiency, and between vehicle size/weight and range?

## Dataset and Workbook Structure

| Section / sheets | Purpose |
| --- | --- |
| `cars` | Main 32,262-row analysis table: manufacturer, model year, category, MSRP, MPG, drivetrain, dimensions, engine data and derived attributes |
| `cars_engines`, `car_names` | Supporting tables used to look up engine specifications and model names by `car_id` |
| `Introduction_questions`, `Additional questions` | Question-based PivotTable summaries and written conclusions |
| `EDA`, `EDA_Slack1.i2.ZADATAK` | Descriptive statistics, percentiles, quartiles, spread and outlier-related calculations |
| `in_depth_analysis`, `bonus` | Pearson correlations and additional price-related feature comparisons |
| `Pivot_brojevi_vozila`, `Pivot_tables` | Grouped vehicle counts and averaged vehicle characteristics |
| `Grafikoni` | Data and charts for visual exploration |
| `Slack3.`, `Slack4.zadatak` | Additional exercises on Volkswagen prices and model-year proportions |

The workbook contains **14 sheets**, numerous PivotTables and several embedded column and scatter charts.

### Key Data Fields

`car_id`, `manufacturer`, `model_year`, `category`, `msrp`, `mpg`, `drivetrain`, `base_curb_weight`, `wheelbase`, `height`, `fuel_tank_capacity`, `model_name`, `engine`, `displacement`, `net_torque`, `horsepower`, `range_miles`, and `car_age`.

## Methods & Excel Skills Demonstrated

**Data enrichment and calculations**
- `XLOOKUP` to bring vehicle names and engine specifications from supporting tables into the primary dataset using `car_id`.
- `IF` to adjust selected engine displacement values in the supporting data.
- Calculated fields including approximate range (`mpg × fuel_tank_capacity`) and vehicle age relative to **2019** (`2019 - model_year`).

**Exploratory data analysis**
- Descriptive statistics using `MIN`, `MAX`, `AVERAGE`, `MEDIAN`, `STDEV.S`, `VAR.S`, `SKEW`, `PERCENTILE.INC`, and `QUARTILE.INC`.
- Quartiles, interquartile range (IQR) and outlier-threshold calculations in the EDA exercise.
- PivotTables to compare counts and averages by manufacturer, category, drivetrain, engine configuration, model year, and other attributes.
- Column and scatter charts to explore vehicle groups and numerical relationships.
- `CORREL` to evaluate Pearson linear correlations between selected variables.

## Selected Results

### MSRP distribution

| Statistic | Workbook result |
| --- | ---: |
| Mean MSRP | **$37,707.46** |
| Median MSRP | **$30,557.50** |
| Minimum MSRP | **$6,929** |
| Maximum MSRP | **$548,800** |
| 25th percentile | **$23,140** |
| 75th percentile | **$40,758.75** |

The highest-MSRP record identified by the workbook's lookup is a **2015 Lamborghini Aventador**, with an MSRP of **$548,800**.

### Sample vehicle distributions

| Dimension | Result |
| --- | ---: |
| Manufacturer: Ford | 4,186 records |
| Manufacturer: Chevrolet | 2,976 records |
| Manufacturer: Toyota | 2,739 records |
| Vehicle category: Car | 13,788 records |
| Vehicle category: Pickup | 7,750 records |
| Vehicle category: SUV | 7,706 records |

Some fields also contain `UNDEFINED` categories; those values should be considered when interpreting group totals.

### Exploratory correlations

| Variables | Pearson r | Interpretation |
| --- | ---: | --- |
| Horsepower vs MSRP | **+0.657** | Moderate-to-strong positive relationship |
| Net torque vs MSRP | **+0.595** | Positive relationship |
| Engine displacement vs MSRP | **+0.334** | Positive relationship |
| Engine displacement vs MPG | **−0.679** | Negative relationship |
| Vehicle height vs estimated range | **+0.458** | Positive relationship |
| Curb weight vs estimated range | **−0.158** | Weak negative relationship |

These correlations describe the analyzed data and **do not demonstrate causation**. The `range_miles` field is calculated from fuel economy and tank capacity, not independently observed driving range.

## Limitations

- The data represents a course dataset and should not be treated as a current inventory or a complete picture of the vehicle market.
- `msrp` reflects listed manufacturer's suggested retail price, **not confirmed transaction/sale price**.
- Some records have `UNDEFINED` attributes, and zeros or fallback values in derived fields may affect analyses.
- Vehicle age is computed against **2019**, the reference year used in this workbook.
- PivotTable views may contain filters or omit undefined categories, so their displayed subtotals can differ from whole-column statistics.

## Files

| File | Contents |
| --- | --- |
| [`Cars_Analysis.xlsx`](Cars_Analysis.xlsx) | Complete Excel project: source/lookup data, formulas, pivot analyses and charts |
| `README.md` | Project documentation and selected findings |

---

*Completed as part of the Coders Lab Data Analytics learning program.*
