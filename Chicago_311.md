# DATA ANALYTICS PROJECT

### Chicago City 311 Service analysis

## AGENDA

-  [Problem statement](#problem-statement)
-  [About data](#about-data)
-  [Key findings](#key-findings)
-  [Summary](#summary)
-  [Remarks](#remarks)
  
  ### PROBLEM STATEMENT

- The Department of Streets and Sanitation (DSS) is a government agency that keeps the streets and alleys of Chicago safe & clean. DSS has more than 2,000 employees that respond to 311 non-emergency service requests.
- DSS deals with 400,000+ requests in a year and has a relatively high overall ticket closing time. With limited resources, they need to know which services are struggling and where to prioritize improving first.
- By analyzing the data, my main goal is to help them allocate resources effectively to improve their overall resolution time and better fulfil the community’s needs.
  
  ### ABOUT DATA
  
  - Chicago city 311 service data
  - Data coverage: between 2018 and 2020 (not 3 full years)
  - Data size: 2.8 million rows, 15 columns (around 740,000 rows for DSS)
  - Fields: ticket category, agency, created date, close date, address, community area, etc.
    
### KEY FINDINGS
   
  #### Priority Metrics
  
 What make a service category more important and more urgent than others?
    <img width="713" alt="Знімок екрана 2024-08-14 о 5 11 06 пп" src="https://github.com/user-attachments/assets/b5cd766c-2e85-471f-bec5-49b68a9919a5">
    
#### Priority Categories

<img width="1030" alt="Знімок екрана 2024-08-14 о 5 14 33 пп" src="https://github.com/user-attachments/assets/2779bfef-2920-4a4e-9366-cc343e9218a1">

#### Validate Findings

How can we tell if these 3 services are problematic?
A cross checking with New York City 311 data for similar services shows that:
- NYC’s garbage-cart-related tickets have an average close time of 1-3 days .
-- Compared to 26 days for Chicago.
- NYC’s tree-related tickets have an average close time of 20-60 days.
-- Compared to 120 days for Chicago.

#### Close Time Distribution

Do all tickets have longer close time than NYC’s?
<img width="807" alt="Знімок екрана 2024-08-14 о 5 19 57 пп" src="https://github.com/user-attachments/assets/57bced9d-1e37-4cb5-a288-98d0ed04da65">

#### Priority Regions

Which regions are struggling more than others?
<img width="996" alt="Знімок екрана 2024-08-14 о 5 26 00 пп" src="https://github.com/user-attachments/assets/11750ef6-b805-4154-8b99-9c800452ddc8">  <img width="366" alt="Знімок екрана 2024-08-14 о 5 27 32 пп" src="https://github.com/user-attachments/assets/a30a3433-d909-43c0-9e83-a714d69d5664">

### SUMMARY

- Prioritize Garbage Cart Maintenance, Tree Trim, and Tree Removal Request since they have both high volume and close time. About 50% of more tickets within these categories have average close time much longer than NYC’s.
- Allocate more resources to the North and the West region as they have among the longest close time in all 3 prioritized categories. Regardless, the close time in all regions are still significantly higher than the standard.
- It would be helpful to understand what NYC is doing differently to resolve tickets in much shorter time, also to further investigate how a large portion of DSS tickets were closed faster than the average.
- Depending on the investigation, DSS should consider investing in better equipment, improving work efficiency, and balancing the number of staff in different locations to reduce the overall resolution time.
- 
### ADDITIONAL REMARKS

- Find more relevant data that might explain the longer time to close in certain regions and community areas such as number of trees, size of trees, number of DSS offices or employees covering the area, number of garbage carts, agency’s budget, etc.
- Identify frequency patterns in month or days of the week for the 3 focused categories to help DSS plan their resources for the whole year.
