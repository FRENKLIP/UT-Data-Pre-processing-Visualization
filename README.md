# Why Do Employees Leave?

## HR Attrition Analysis — IBM Dataset

This project analyzes employee attrition using the IBM HR Employee Attrition dataset. The goal is to understand which factors are most connected to employees leaving the company and to present the findings through clear data cleaning, feature engineering, exploratory analysis, and visualizations in R Markdown.

The analysis focuses on practical HR questions such as:

- Which employees are most likely to leave?
- Does overtime increase attrition?
- Are younger employees more likely to resign?
- Which departments have the highest attrition risk?
- Does commute distance or pay explain employee turnover?

## Key Findings

| Factor | Main Finding |
|---|---|
| Overtime | Employees working overtime leave at **30.5%**, compared with **10.4%** for employees without overtime. |
| Age | Employees aged **18–25** have the highest attrition rate at **35.8%**. |
| Department | **Sales** and **Human Resources** show above-average attrition. |
| Distance from Home | Employees living farther from work tend to leave more often. |
| Pay | Daily pay does not strongly explain attrition in this dataset. |

The overall company attrition rate is **16.1%**, meaning roughly 1 in 6 employees left.

## Project Structure

```text
.
├── HR-Employee-Attrition.csv   # Dataset used in the analysis
├── analysis.Rmd                # Main R Markdown report
├── analysis.html               # Rendered HTML report, if generated
└── README.md                   # Project documentation
```

> Note: The `.Rmd` file in this repository may have a different filename. It contains the full analysis, visualizations, and conclusions.

## Tools and Libraries

This project was built with **R** and **R Markdown**.

Main R packages used:

- `dplyr` — data cleaning and transformation
- `readr` — loading CSV data
- `ggplot2` — data visualization
- `skimr` — dataset summary
- `corrplot` — correlation heatmap
- `gridExtra` — combining multiple plots
- `RColorBrewer` — color palettes

## How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
```

### 2. Install Required R Packages

Open R or RStudio and run:

```r
install.packages(c(
  "dplyr",
  "readr",
  "ggplot2",
  "skimr",
  "corrplot",
  "gridExtra",
  "RColorBrewer"
))
```

### 3. Add the Dataset

Make sure the dataset file is in the project folder:

```text
HR-Employee-Attrition.csv
```

The R Markdown file reads the data using:

```r
HR_Employee_Attrition <- read_csv("HR-Employee-Attrition.csv")
```

### 4. Render the Report

In RStudio, open the `.Rmd` file and click **Knit**.

Or render it from the R console:

```r
rmarkdown::render("analysis.Rmd")
```

Replace `analysis.Rmd` with the actual filename if it is different.

## Analysis Workflow

The project follows these steps:

1. **Load the dataset**  
   Import the IBM HR Employee Attrition dataset.

2. **Inspect the data**  
   Review rows, columns, missing values, and constant variables.

3. **Clean the data**  
   Keep the most relevant columns, rename variables, check missing values, remove duplicates, and convert Yes/No variables into numeric format.

4. **Engineer features**  
   Create age groups, commute distance groups, readable education labels, and scaled pay values.

5. **Explore attrition patterns**  
   Calculate attrition rates by overtime, department, age group, and distance from home.

6. **Create visualizations**  
   Build bar charts, heatmaps, boxplots, histograms, scatterplots, and a correlation heatmap.

7. **Create a risk score**  
   Combine overtime, age, and department risk factors into a simple attrition risk score.

8. **Summarize conclusions and recommendations**  
   Provide actionable HR recommendations based on the findings.

## Main Visualizations

The report includes:

- Attrition rate by age group
- Attrition rate by overtime status
- Attrition rate by department
- Attrition rate by distance from home
- Combined visualization of four key attrition drivers
- Department × Overtime heatmap
- Pay, age, and commute distance boxplots
- Pay distribution histogram
- Age vs. daily pay scatterplot
- Correlation heatmap
- Composite attrition risk score chart

## Risk Score Explanation

A simple attrition risk score is created using the strongest observed factors:

| Risk Factor | Points |
|---|---:|
| Works overtime | +3 |
| Age 18–25 | +2 |
| Age 26–35 | +1 |
| Works in Sales or Human Resources | +1 |

The risk score ranges from **0 to 6**. Employees with no risk factors have much lower attrition, while employees with several combined risk factors show much higher attrition.

## Recommendations

Based on the analysis, the company should prioritize:

1. **Reducing overtime**, especially in Sales.
2. **Supporting younger employees** with mentorship and career development.
3. **Investigating Sales and HR attrition** through surveys or exit interviews.
4. **Offering flexibility for long-distance commuters**, such as remote or hybrid work options.

## Authors

**Frenkli Paluku** and **Fatir Beqollari**  
Data Science, Faculty of Natural Sciences, University of Tirana

