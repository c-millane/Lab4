# Lab4
---
title: "Lab 4"
output: html_document
---
*Alexandrea, Cecilia, Joshua*
*Group 1*

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

```{r}
av <- read.csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/avengers/avengers.csv", stringsAsFactors = FALSE)

library(tidyr)
library(tidyverse)
library(readr)

death <- av %>% gather(key = TimeD, value = Death, 11,13,15,17,19)

head(death)

deaths <- death %>% mutate(TimeD = parse_number(TimeD))

head(deaths)


return <- ave %>% gather(key = TimeR, value = Return, 11:15)
head(return)

returns <- return %>% mutate(TimeR = parse_number(TimeR))
head(returns)


```
  
**Out of 173 listed Avengers, my analysis found that 69 had died at least one time after they joined the team. **
  
  
```{r}
deaths %>% filter(TimeD==1) %>% count(Death)

deaths %>% filter(TimeD==1) %>% count()

```



**This shows that 69 had died at least once and that there are 173 Avengers.**
