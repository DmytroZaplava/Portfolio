# Table of Context

[Scenario Overview](#scenario-overview)

[Project Objective](#project-objective)

[Data Sources](#Data-Sources)

[Data Preparation](#Data-Preparation)

[Creating the Dashboard in Power BI](#Creating-the-Dashboard-in-Power-BI)

[Deliverables](#Deliverables)

[Conclusion](#Conclusion)

[Limitations](#Limitations)

[References](#References)

## Scenario Overview

Create a comprehensive HR dashboard to support data-driven decision-making within a fictional mid-sized company. 
The objective is to build an interactive dashboard using Power BI that provides actionable insights into HR metrics such as employee demographics, turnover rates, recruitment effectiveness, and performance evaluations.

## Project Objective

To develop a Power BI dashboard that offers a detailed overview of the company's HR data, helping HR professionals to:
* Monitor and analyze employee demographics and diversity.
* Assess turnover trends and identify underlying causes.
* Evaluate recruitment processes and their efficiency.
* Track employee performance and satisfaction metrics.
  
## Data Sources

- Employee Data:
  - Contains employee details such as demographics (age, gender), job roles, departments, and performance scores.
- Turnover Data:
   - Includes information on employee exits, reasons for leaving, and tenure.
- Recruitment Data:
  - Details the recruitment process, time-to-fill metrics, and sources of hire.
- Survey Data:
  - Provides employee satisfaction and engagement survey results.
    
## Data Preparation

1. #### Data Collection:
    * Employee Data: Employee demographics, job roles, departments, performance scores.
    * Turnover Data: Exit dates, reasons for leaving, tenure.
    * Recruitment Data: Hiring dates, recruitment sources, time-to-fill positions.
    * Survey Data: Satisfaction scores, feedback comments.
2. ##### Data Cleaning:
    * Handle missing values by imputing or removing them as necessary.
    * Remove duplicates to ensure data accuracy.
    * Standardize formats for consistency.
3. ##### Data Transformation:
    * Merge datasets to create a unified data model.
    * Create calculated columns for metrics such as turnover rates and average performance scores.
    * Define measures for aggregation and analysis.
      
## Creating the Dashboard in Power BI

1. #### Import Data
    * Import the cleaned and transformed datasets into Power BI.
    * Establish relationships between tables to integrate data sources.
2. #### Design Data Models
    * Create a data model that connects employee data, turnover data, recruitment data, and survey data.
    * Build calculated columns and measures to support key metrics.
3. #### Build Visualizations
   
- Employee Demographics
  - *Visualization: Bar Chart or Pie Chart*
  - *Metrics: Age distribution, gender ratio, department headcount*
  - *Description: Visualize the distribution of employees by age, gender, and department to understand workforce composition and diversity.*
      
- Turnover Analysis
  - *Visualization: Line Chart or Column Chart*
  - *Metrics: Monthly turnover rates, reasons for leaving, average tenure*
  - *Description: Display turnover trends over time, categorize reasons for exits, and analyze the average tenure of employees who left.*
    
- Recruitment Metrics
  - *Visualization: Funnel Chart or Stacked Column Chart*
  - *Metrics: Time-to-fill positions, recruitment sources effectiveness, hires per department*
  - *Description: Track the efficiency of the recruitment process, assess the effectiveness of different recruitment sources, and monitor hiring metrics by department.*

- Employee Performance and Satisfaction
  - *Visualization: Heatmap or Scatter Plot*
  - *Metrics: Performance ratings, satisfaction scores, performance vs. satisfaction correlation*
  - *Description: Evaluate employee performance ratings alongside satisfaction scores to identify trends and correlations.
    
4. #### Add Interactive Elements
    * Filters and Slicers: Include filters for departments, job roles, and time periods to allow users to drill down into specific segments.
    * Tooltips: Provide additional context and details when users hover over visualizations.
    * Bookmarks: Create bookmarks for different views or scenarios (e.g., annual turnover analysis vs. quarterly hiring trends).
5. #### Design the Dashboard Layout
    * Arrange visualizations in a logical, user-friendly layout.
    * Ensure the dashboard is visually appealing and easy to navigate.
    * Add titles, labels, and legends for clarity.
6. #### Publish and Share
    * Publish the dashboard to the Power BI service.
    * Share the dashboard with HR stakeholders and set appropriate permissions for access.

## Deliverables
* A Power BI dashboard that provides insights into:
    * Employee demographics and diversity
    * Turnover rates and trends
    * Recruitment efficiency and metrics
    * Employee performance and satisfaction
* A user guide explaining how to navigate and interact with the dashboard.
  
## Conclusion

The HR dashboard will offer a powerful tool for the HR department at the company, enabling them to make informed decisions based on comprehensive data analysis. 
By visualizing key HR metrics, the dashboard will help the team understand workforce dynamics, improve recruitment processes, manage turnover effectively, and enhance overall employee satisfaction. 
This project demonstrates your ability to leverage Power BI to create actionable insights and support strategic HR management.

<img width="791" alt="Знімок екрана 2024-08-12 о 6 44 47 пп" src="https://github.com/user-attachments/assets/dada8e57-4eb2-48bf-8c93-f7454bc7de75">

<img width="589" alt="Знімок екрана 2024-08-12 о 6 45 14 пп" src="https://github.com/user-attachments/assets/83a6b8a3-17f3-4afc-8083-fa6694074ff9">


## Limitations

* Data Completeness: Some data points might be missing or incomplete, which could affect the accuracy of the analysis.
* Outliers: There may be outliers in the data that could skew results. While efforts will be made to identify and address these, they may still impact the analysis.
  
## References
1. [Power BI Documentation](https://learn.microsoft.com/en-us/power-bi/)
