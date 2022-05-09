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

```
``` ruby
```{r}

mycolour<-c("blue", "green")

```
```ruby

### Chart A

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n())
%>% plot_ly(x= ~ data$Country, y= ~ data$`Sales Quantity`, color = "purple")
p1
```

```ruby
### Chart B

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n())
%>% plot_ly(x= ~ data$Period, y= ~ data$`Sales Quantity`)
p1
```
```ruby

### Chart C

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n())
%>% plot_ly(x= ~ data$Country, y= ~ data$Value, type = "bar", color = "blue")
p1
```

```ruby

### Chart D

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n()) 
%>% plot_ly(x= ~ data$Period, y= ~ data$Value, type = "scatter", color = "green")
p1

```

