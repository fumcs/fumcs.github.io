---
layout: distill
title: Bike Rental System, Part II, EDA
description: Exploratory Data Analysis
tags: distill formatting
giscus_comments: true
date: 2023-08-15
featured: false
thumbnail: assets/img/GNN/two-wheels.jpg
authors:
  - name: E. Hosseini
    url: ""
    affiliations:
      name: FUM, CS Student
  - name: P. MottahariNejad
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

{% include figure.html path="assets/img/GNN/trips_per_hour-scatterplot-divvybikes.png" class="img-fluid rounded z-depth-1" style="max-width: 50%; max-height: 400px;" %}


### Histogram of Number of Stations with a certain number of Arrivals+Departures in a Week:

{% include figure.html path="assets/img/GNN/Arrivals+Departures-histogram-divvybikes.png" class="img-fluid rounded z-depth-1" %}

- The histogram provides a concise representation of the distribution of bike stations, categorized by the quantity of arrivals and departures within a week. The analysis reveals that the majority of bike stations exhibit limited engagement, with comparatively fewer incoming and outgoing journeys. Conversely, only a minor portion of stations encounter notably elevated trip figures.


## Trends + analysis

We also analyze patterns in the monthly, weekly, and daily periods of dataset to extract valuable information.

### weekly

{% include figure.html path="assets/img/GNN/weekly-bar-divvybikes.png" class="img-fluid rounded z-depth-1" %}


- The bar plot provides an efficient visualization of the distribution of bike trips based on the day of the week over a three-month period. The data analysis uncovers clear patterns in bike-sharing demand, with higher usage during weekends (Saturday and Sunday) and Tuesday, and moderate demand on weekdays (Monday, Thursday, and Friday). This information can be valuable for bike-sharing operators to plan for the distribution of stations across the service area.

### working days vs weekend

{% include figure.html path="assets/img/GNN/days_vs_weekend-bar-divvybikes.png" class="img-fluid rounded z-depth-1" %}


- The bar plot provides a clear visualization of the disparity in bike-sharing demand between working days and weekends. The analysis reveals that bike trips are significantly more frequent and widespread on working days, primarily driven by higher commuting and daily transportation needs. In contrast, bike-sharing experiences a decrease in usage during weekends, as individuals engage in recreational activities and have reduced work commitments.


### daily

{% include figure.html path="assets/img/GNN/daily-bar-divvybikes.png" class="img-fluid rounded z-depth-1" %}


- The line plot provides an effective visualization of the temporal distribution of bike trips throughout the day. The data analysis uncovers distinctive trends in bike-sharing demand during different hours, with significant peaks observed during the morning and evening rush hours. This information can be valuable for bike-sharing operators to plan for the distribution of bikes and stations across the service area.

---

- Part I: [Introduction to Bike Rental Platforms, Datasets and Methods](/blog/2023/Bike-Part-I/)
- Part III: [How to transform bike tabular data to PyG-Temporal format?](/blog/2023/Bike-Part-III/)
