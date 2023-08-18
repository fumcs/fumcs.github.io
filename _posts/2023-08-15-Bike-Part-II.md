---
layout: distill
title: Bike Rental System, Part II, EDA
description: Exploratory Data Analysis
tags: distill formatting
giscus_comments: true
date: 2023-08-15
featured: true
thumbnail: assets/img/GNN/two-wheels.jpg
authors:
  - name: P. MottahariNejad
    url: ""
    affiliations:
      name: FUM, CS Student
  - name: E. Hosseini
    url: ""
    affiliations:
      name: FUM, CS Student
  - name: M. Amintoosi
    url: "https://mamintoosi.github.io/"
    affiliations:
      name: FUM, CS Faculty


---
# Exploratory Data Analysis (EDA)
### We have two datasets named bikeshare and divvtbikes. In the following, we will examine these two.
Here we have some statical reports on a dataset.

## Data visualization
### trips per hour in a month:

divvybikes
{% include figure.html path="assets/img/GNN/trips per hour-scatterplot-divvybikes.png" class="img-fluid rounded z-depth-1" %}

### Histogram of Number of Stations with a certain number of Arrivals+Departures in a Week:

divvybikes

{% include figure.html path="assets/img/GNN/number of Arrivals+Departures- histogram- divvybikes.png" class="img-fluid rounded z-depth-1" %}

- The histogram effectively depicts the distribution of bike stations based on the number of arrivals and departures during a week. The analysis indicates that most bike stations have minimal activity or relatively lower numbers of incoming and outgoing trips. On the other hand, only a small fraction of stations experiences significantly higher trip counts.

## Trends + analysis

We also analyze patterns in the monthly, weekly, and daily periods of dataset to extract valuable information.

### weekly

divvybikes

{% include figure.html path="assets/img/GNN/weekly plot- bar- divvybikes.png" class="img-fluid rounded z-depth-1" %}

- The bar plot effectively illustrates the distribution of bike trips based on the day of the week over a three-month period. The data analysis reveals distinct patterns in bike-sharing demand, with higher usage during weekends (Saturday and Sunday) and Tuesday, and moderate demand on weekdays (Monday, Thursday, and Friday).


### working days vs weekend

divvybikes

{% include figure.html path="assets/img/GNN/days vs weekend- bar- divvybikes.png" class="img-fluid rounded z-depth-1" %}

- The bar plot effectively highlights the difference in bike-sharing demand between working days and weekends. The analysis indicates that bike trips are more frequent and popular on working days due to higher commuting and daily transportation requirements. On the other hand, bike-sharing experiences reduced usage during weekends when recreational activities and reduced work commitments are more prevalent.


### daily

divvybikes

{% include figure.html path="assets/img/GNN/daily- bar- divvybikes.png" class="img-fluid rounded z-depth-1" %}

- The line plot effectively illustrates the temporal distribution of bike trips throughout the day. The data analysis showcases distinctive trends in bike-sharing demand during different hours, with significant peaks observed during the morning and evening rush hours.
