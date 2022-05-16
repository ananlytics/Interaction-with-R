# Interactive dashboards in R
## We can code our way through to creating a simple dashboard for stakeholder concerned with output.
### We shall use a simple sales data to create four-charts with basic aesthetics.
We can divide our code in different chunks, making it easier to find error and better execution.

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
![A](https://user-images.githubusercontent.com/104814594/167584729-bda9a06f-828e-48c0-8d3b-79ba049c4955.JPG)

```ruby
### Chart B

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n())
%>% plot_ly(x= ~ data$Period, y= ~ data$`Sales Quantity`)
p1
```
![B](https://user-images.githubusercontent.com/104814594/167584784-4b6b7d91-8a4e-49e6-86ce-5852230ee40a.JPG)

```ruby

### Chart C

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n())
%>% plot_ly(x= ~ data$Country, y= ~ data$Value, type = "bar", color = "blue")
p1
```
![C](https://user-images.githubusercontent.com/104814594/167584819-88626ab5-d5fa-4bde-a6d2-182eb3f8ea7f.JPG)

```ruby

### Chart D

```{r}

p1<-data %>% group_by(data$`category`) %>% summarise(count = n()) 
%>% plot_ly(x= ~ data$Period, y= ~ data$Value, type = "scatter", color = "green")
p1

```
![D](https://user-images.githubusercontent.com/104814594/167584870-659e4d59-2783-4f54-a9b7-0f91860258b7.JPG)


#Final Dashboard with comprise of 4 charts as mentioned above and displayed below.
![1](https://user-images.githubusercontent.com/104814594/167584188-398b158c-6ae0-4ccf-a1fa-7bb342fcf51b.JPG)




