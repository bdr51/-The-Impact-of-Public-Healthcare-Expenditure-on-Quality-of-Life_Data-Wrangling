# README.md
## DATA201/422 Group Assignment: The Impact of Public Healthcare Expenditure on Quality of Life

**Authors:** Bree Drinkwater, Sarah Tervoort, Dom Woodhouse  
**Date:** 13/10/2023  
**Course:** DATA201/DATA422  
**Institution:** University of Canterbury

---

### Table of Contents
1. [Project Overview](#project-overview)
2. [Research Question](#research-question)
3. [Data Sources](#data-sources)
4. [Methodology](#methodology)
5. [Key Findings](#key-findings)
6. [Technical Implementation](#technical-implementation)
7. [How to Use This Notebook](#how-to-use-this-notebook)
8. [Dependencies](#dependencies)
9. [Project Structure](#project-structure)

---

### Project Overview

This project investigates the relationship between public healthcare expenditure, taxation, and quality of life indicators across multiple countries. Our analysis explores whether greater government healthcare spending leads to improved life expectancy and better health outcomes, while considering factors such as poverty, COVID-19 impact, and specific health conditions like cardiovascular disease.

**Countries Analyzed:** United States, New Zealand, Australia, Japan, Sweden, Great Britain, Bulgaria, Syria, Afghanistan, Iraq, China, Jamaica, Fiji, Zimbabwe (with focus on a subset for detailed analysis)

**Time Period:** 1980-2023 (varies by dataset availability)

### Research Question

**Primary Question:** Does greater government healthcare expenditure lead to greater life expectancy?

**Secondary Investigations:**
- How does healthcare expenditure correlate with poverty rates?
- What impact did COVID-19 have on different healthcare systems?
- How do factors like cardiovascular disease, obesity, and high blood pressure relate to healthcare spending?
- What role does taxation play in healthcare quality?

### Data Sources

1. **Our World in Data:**
   - Life expectancy data (`life-expectancy.csv`)
   - Public healthcare expenditure as percentage of GDP (`public-health-expenditure-share-GDP-OWID.csv`)
   - Poverty data (`poverty-explorer.csv`)
   - Population data (`population-and-demography.csv`)

2. **World Health Organization (WHO):**
   - COVID-19 global data (`WHO-COVID-19-global-data.csv`)

### Methodology

#### Data Wrangling Techniques Applied:

1. **Data Loading and Initial Exploration:**
   - Imported CSV files using `read_csv()`
   - Examined data structure and content

2. **Data Cleaning:**
   - Renamed columns for consistency (e.g., `Entity` → `Country`)
   - Filtered data to focus on selected countries and time periods
   - Handled missing values and inconsistencies

3. **Data Transformation:**
   - Created per-capita calculations for fair comparisons
   - Extracted year information from date columns
   - Aggregated COVID-19 data by year and country

4. **Data Merging:**
   - Used `Country` and `Year` as primary keys
   - Successfully merged healthcare expenditure, life expectancy, poverty, and population data
   - Created a comprehensive final dataset for analysis

5. **Visualisation:**
   - Created static plots using `ggplot2`
   - Developed interactive visualisations using `plotly`
   - Generated various plot types: box plots, scatter plots, line charts
   - Implemented faceting for multi-country comparisons

### Key Findings

#### Healthcare Expenditure Patterns:
- **China and Bulgaria** exhibited significantly lower healthcare expenditure compared to other studied countries
- **Japan** demonstrated the highest life expectancy despite having healthcare expenditure similar to other developed nations

#### Correlations Identified:
1. **Positive correlation** observed between life expectancy and public healthcare expenditure in most countries
2. **China showed unique patterns** - significant improvements in poverty reduction with relatively low healthcare spending
3. **Limited correlation** found between healthcare expenditure and extreme poverty in most developed nations
4. **Sweden and Bulgaria** showed higher COVID-19 cases per capita, suggesting policy responses may outweigh expenditure impacts

#### COVID-19 Insights:
- Sweden's high case numbers potentially linked to "herd immunity" approach
- Per-capita analysis provided fairer comparisons between countries of different sizes

#### Data Challenges Addressed:
- Created per-capita metrics for poverty and COVID-19 data
- Handled inconsistent year coverage across datasets
- Managed varying data availability for different countries
- Successfully merged datasets with different structures

### Technical Implementation

#### Code Structure:
The Jupyter Notebook is organised chronologically:

1. **Setup and Data Loading** (Lines 1-100)
2. **Life Expectancy Analysis** (Lines 101-200)
3. **Healthcare Expenditure Analysis** (Lines 201-300)
4. **COVID-19 Analysis** (Lines 301-400)
5. **Poverty Analysis** (Lines 401-500)
6. **Data Integration** (Lines 501-600)
7. **Comprehensive Analysis** (Lines 601-700)

#### Key Functions and Techniques:
- **Data Filtering:** `filter()` with specific country and year criteria
- **Data Merging:** `merge()` using common keys
- **Feature Engineering:** Creating new columns for per-capita calculations
- **Visualisation:** Combination of `ggplot2` and `plotly` for static and interactive plots
- **Data Export:** Saving plots as PNG and HTML files

### How to Use This Notebook

#### Prerequisites:
1. Basic understanding of R programming
2. Familiarity with tidyverse packages
3. RStudio or similar environment installed

#### Setup Instructions:
1. **Install Required Packages:**
   ```r
   install.packages(c("tidyverse", "ggplot2", "plotly", "htmlwidgets", "webshot"))
   ```

2. **Prepare Data Files:**
   - Ensure all CSV files are in the working directory
   - Update file paths in the notebook if necessary

3. **Set Working Directory:**
   ```r
   setwd("C:/Your/Project/Directory")
   ```

4. **Run the Notebook:**
   - Execute code cells sequentially
   - Note: Some interactive plots require HTML widget support

#### Navigation Tips:
- The notebook is designed to run from start to finish
- Each major section begins with comments describing its purpose
- Intermediate results are saved as variables for later use
- Final visualisations are exported for presentation purposes

### Dependencies

#### Required R Packages:
```r
# Core data manipulation
library(tidyverse)    # Includes dplyr, ggplot2, etc.
library(dplyr)        # Data manipulation
library(ggplot2)      # Static plotting

# Interactive visualisation
library(plotly)       # Interactive plots
library(htmlwidgets)  # Saving interactive plots as HTML
library(webshot)      # Converting interactive plots to static images

# Optional for extended analysis
library(reticulate)   # Python integration (if needed)
```

#### Data Files Required:
1. `life-expectancy.csv`
2. `public-health-expenditure-share-GDP-OWID.csv`
3. `WHO-COVID-19-global-data.csv`
4. `poverty-explorer.csv`
5. `population-and-demography.csv`

### Project Structure

```
Project Directory/
│
├── DATA201_Group_Assignment.ipynb        # Main Jupyter Notebook (complete analysis)
└── README.md                             # This documentation file
```

### Notes for Reproduction

1. **Data Availability:** Some datasets may have been updated since the analysis. Check source websites for the most recent versions.
2. **Interactive Elements:** HTML outputs require a web browser to view interactive features.
3. **Computational Requirements:** The analysis can be run on standard desktop computers with 8GB RAM.
4. **Time Considerations:** Complete execution takes approximately 5-10 minutes depending on system specifications.

### Contact Information

For questions about this analysis, please contact the project team members.

---

*This project was completed as part of the DATA201/422 coursework. All analysis is based on publicly available data as of October 2023.*
