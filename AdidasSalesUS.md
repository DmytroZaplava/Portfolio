## Adidas US Sales Project in RStudio


##### This R enrvronment comes with many helpful analytics libraries installed
```R
install.packages("readxl")
install.packages("dplyr")
install.packages("tidyr")
install.packages("ggplot2")
install.packages("scales")

library(readxl)
library(dplyr)
library(tidyr)
library(ggplot2)
library(scales)
```

```R
file_path <- "...Downloads/Adidas US Sales Datasets.xlsx"
df <- read_excel(file_path, sheet = 1)
```
```R
Adidas_US_Sales_Datasets_1_ <- read_excel("...Downloads/Adidas US Sales Datasets.xlsx") 
View(Adidas_US_Sales_Datasets_1_)
```

## Correct Total Sales and Operating Profit columns
## 
```R
df$`TotalSales` <- df$`PricePerUnit` * df$`UnitsSold` 
df$`OperatingProfit` <- df$`TotalSales` * df$`OperatingMargin` ##
```
```R
retailer_counts <- table(df$Retailer)
top_retailers <- names(sort(retailer_counts, decreasing = TRUE)[1:6]) 
```

# Bar plot of Retailer's sales count
```R
retailer_counts_df <- data.frame(Retailer = names(retailer_counts), Count = as.numeric(retailer_counts))
retailer_counts_df$text <- paste(retailer_counts_df$Count)
ggplot(retailer_counts_df, aes(x = reorder(Retailer, -Count), y = Count, label = text)) +
  geom_bar(stat = "identity", fill = "blue") +
  geom_text(vjust = -0.2, size = 3) +
  labs(title = "Retailer's sales count",
       x = "Retailer Name",
       y = "Count") +
  theme_minimal()
```
  ![image1](https://github.com/user-attachments/assets/ccf4f05d-f128-4f8d-bb9e-c3874ceb8eae)


  # Retailer wise Sales Volume
```R
sales_df <- df %>%
  group_by(Retailer) %>%
  summarise(`TotalSales` = sum(`TotalSales`), `OperatingProfit` = sum(`OperatingProfit`)) %>%
  mutate(`SalesPercentage` = round((`TotalSales` / sum(`TotalSales`)) * 100, 2))
```
  # Bar plot of Retailer-wise Total Sales and Operating Profit
```R
ggplot(sales_df, aes(x = Retailer, y = TotalSales, fill = Retailer)) +
  geom_bar(stat = "identity") +
  geom_line(aes(y = OperatingProfit * 0.7), color = "red", size = 1, group = 1) +
  scale_y_continuous(labels = function(x) format(x, scientific = FALSE)) +
  labs(title = "Retailer wise Total Sales and Operating Profit",
       x = "Retailer",
       y = "Sales",
       fill = "Retailer") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
  ![image2](https://github.com/user-attachments/assets/41aa09c4-0672-4cfa-9374-89c4d55b15d1)
```R
  product_sales <- df %>%
  group_by(Retailer, Product) %>%
  summarise(`TotalSales` = sum(`TotalSales`))
```
# Bar plot of Product sales by Retailer
```R
ggplot(product_sales, aes(x = Retailer, y = `TotalSales`, fill = Product)) +
  geom_bar(stat = "identity", position = "dodge") +
  scale_y_continuous(labels = function(x) format(x, scientific = FALSE)) +
  labs(title = "Retailer wise Product sales data",
       x = "Retailer",
       y = "TotalSales",
       fill = "Product") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
![image3](https://github.com/user-attachments/assets/1ea70d76-5d74-40e0-8faf-8f0665c22309)


  # Season wise Sales data
```R
season_sales <- df %>%
  group_by(Season, Year) %>%
  summarise(`TotalSales` = sum(`TotalSales`))
```

# Line chart for Season Wise Sales Analysis
```R
ggplot(season_sales, aes(x = Season, y = `TotalSales`, group = Year, color = factor(Year))) +
  geom_line(size = 1) + 
  scale_y_continuous(labels = function(x) format(x, big.mark = ",", scientific = FALSE)) +
  labs(title = "Season Wise Sales Analysis",
       x = "Season",
       y = "Sales") +
  theme_minimal()
```
  ![image4](https://github.com/user-attachments/assets/e8bd2597-e6aa-40a0-87ea-6d943d56e70e)

# Product sales by Season
```R
product_sales_season <- df %>%
  group_by(Season, Product) %>%
  summarise(`UnitsSold` = sum(`UnitsSold`))
```
# Bar plot of Product sales by Season
```R
ggplot(product_sales_season, aes(x = Season, y = `UnitsSold`, fill = Product)) +
  geom_bar(stat = "identity", position = "dodge") +
  labs(title = "Season-wise sales of different products",
       x = "Season",
       y = "Units Sold",
       fill = "Product") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
  
![image5](https://github.com/user-attachments/assets/c485ad8b-be4d-48f5-b6d3-92ddfd17a944)

# Region wise popular product(by units sold)
# Bar plot of Region wise product sales
```R
region_product_sales <- df %>%
  group_by(Region, Product) %>%
  summarise(`UnitsSold` = sum(`UnitsSold`))
```
```R
ggplot(region_product_sales, aes(x = Product, y = `UnitsSold`, fill = Product)) +
  geom_bar(stat = "identity") +
  scale_y_continuous(labels = function(x) format(x, big.mark = ",", scientific = FALSE)) +
  labs(title = "Region wise unit sold of products",
       x = "Product",
       y = "Units Sold",
       fill = "Product") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
  ![IMAGE6](https://github.com/user-attachments/assets/56068297-3239-407f-be8a-97a481846fa2)

  # Time Series Analysis
```R
df$Month <- format(as.Date(df$Month, format = "%m"), "%b")
df$`Month-year` <- format(df$`InvoiceDate`, "%Y - %b")
```
# Line chart for Time Series Analysis of Sales
```R
time_series_sales <- df %>%
  group_by(`Month-year`) %>%
  summarise(`TotalSales` = sum(`TotalSales`))

ggplot(time_series_sales, aes(x = `Month-year`, y = `TotalSales`, group = 1)) +
  geom_line(color = "green") +
  geom_point(color = "green") +
  scale_y_continuous(labels = function(x) format(x, big.mark = ",", scientific = FALSE)) +
  labs(title = "Time Series Analysis of Sales",
       x = "Time",
       y = "Sales") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
  ![image7](https://github.com/user-attachments/assets/912c9e85-1688-4c6b-865a-13afb78ab5d8)

## Review

Loading Libraries and Data: We load necessary libraries (readxl, dplyr, tidyr, ggplot2, scales) and read the Excel file containing the AdidasUS sales data.

Data Cleaning: Remove unnecessary rows and set column names appropriately. Calculate TotalSales and OperatingProfit based on existing columns.

Analysis: Perform various analyses such as retailer-wise sales count, retailer-wise total sales and operating profit, season-wise sales, product-wise sales, time-series analysis, and region-wise product sales.

Visualization: Use ggplot2 for creating visualizations such as bar plots, and line charts to represent the analyzed data.

This R script mirrors the Python code's functionality but uses R-specific libraries and syntax for data manipulation and visualization. Adjustments may be needed based on your specific dataset and environment setup in RStudio.

## 

[Download RStudio Here](https://posit.co/download/rstudio-desktop/)

