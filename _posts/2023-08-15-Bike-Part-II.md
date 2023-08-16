---
layout: distill
title: Bike Rental System, Part II
description: Exploratory Data Analysis
tags: distill formatting
giscus_comments: true
date: 2023-08-15
featured: true
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
Here we have some statical reports on both dataset.

## Data visualization
### trips per hour in a month:
bikeshare
{% include figure.html path="assets/img/GNN/b1.png" class="img-fluid rounded z-depth-1" %}
divvybikes
{% include figure.html path="assets/img/GNN/d1.png" class="img-fluid rounded z-depth-1" %}
### Histogram of Number of Stations with a certain number of Arrivals+Departures in a Week:
bikeshare
{% include figure.html path="assets/img/GNN/b2.png" class="img-fluid rounded z-depth-1" %}
divvybikes
{% include figure.html path="assets/img/GNN/d2.png" class="img-fluid rounded z-depth-1" %}

## Trends
We also analyze patterns in the monthly, weekly, and daily periods of both datasets to extract valuable information.
### weekly
divvybikes
{% include figure.html path="assets/img/GNN/d3.png" class="img-fluid rounded z-depth-1" %}
bikeshare
{% include figure.html path="assets/img/GNN/b3.png" class="img-fluid rounded z-depth-1" %}
### working days vs weekend
divvybikes
{% include figure.html path="assets/img/GNN/d4.png" class="img-fluid rounded z-depth-1" %}
bikeshare
{% include figure.html path="assets/img/GNN/b4.png" class="img-fluid rounded z-depth-1" %}
### daily
divvybikes
{% include figure.html path="assets/img/GNN/d5.png" class="img-fluid rounded z-depth-1" %}
bikeshare
{% include figure.html path="assets/img/GNN/b5.png" class="img-fluid rounded z-depth-1" %}
## Data analysis