# Interactive dashboards in R
## We can code our way through to creating a simple dashboard for stakeholder concerned with output.
### We shall use a simple sales data to create four-charts with basic aesthetics.
```ruby
---
title: "New Dashboard"
output: 
  flexdashboard::flex_dashboard:
    orientation: rows
    vertical_layout: fill
    social: ["twitter", "facebook", "menu"]
---

```{r}



library(knitr)
library(DT)
library(rpivotTable)
library(ggplot2)
library(plotly)
library(dplyr)
library(openintro)
library(highcharter)
library(readxl)

```

```ruby
```{r}

data <- read_excel("Sales.xlsx")

data$`FG Class` <- data$food_class
data$`Solution Class` <- data$food_class

```
```
