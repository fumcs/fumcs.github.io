---
layout: distill
title: Bike Rental System, Part I, Introduction
description: Introduction to Bike Rental Platforms, Datasets and Methods
tags: distill formatting
giscus_comments: true
date: 2023-07-10
featured: true
thumbnail: assets/img/GNN/one-wheel.jpg
authors:
  - name: M. Amintoosi
    url: "https://mamintoosi.github.io/"
    affiliations:
      name: FUM, CS Faculty
  - name: P. MottahariNejad
    url: ""
    affiliations:
      name: FUM, CS Student
  - name: E. Hosseini
    url: ""
    affiliations:
      name: FUM, CS Student

---

# Bike Rental System: Introduction, Datasets, Graph Neural Networks

Welcome to Part I of our blog series on building a Bike Rental software system! In this post, we will provide an introduction to the Bike rental system, discuss the datasets involved, and explore the concept of graph neural networks and their application to this domain.

## Introduction to Bike Rental System

Bike rental systems have gained popularity across the globe as a convenient and eco-friendly mode of transportation. These systems typically allow users to rent bicycles for short periods, making it ideal for commuters, tourists, or anyone looking for an alternative mode of transport. With the increasing demand for such systems, building efficient software becomes crucial.

The primary goal of our Bike Rental software system is to enable users to easily browse and rent bikes, track usage, and manage logistics. This requires a comprehensive understanding of the rental process, user interaction, and efficient data management.

## Datasets

To build a successful Bike Rental software system, we need access to high-quality datasets that capture the relevant information. These datasets will serve as the foundation for various tasks such as exploratory data analysis and machine learning.

Some examples of datasets that can be utilized in this context include:

- [Ride on, Chicago](https://divvybikes.com/)
- [The Metro Bike Share system](https://bikeshare.metro.net/about/data/)

These datasets, along with their proper preprocessing and integration, lay the groundwork for meaningful analysis, model building, and system implementation.

One of the new aaprocahes for prediction in a bike rental system is Temporal Graph Neural Networks (TGNN), a type of Graph Neural Networks. 
**The main porpose of these blog post series, is to show how we make the above dataset, suitable for TGNN.** 
It is related to [Converting a Tabular Dataset to a Temporal Graph Dataset](https://www.youtube.com/watch?v=XPTwvvlHaUA). We will provide the details of our approach.


## Graph Neural Networks and Temporal Graph Neural Networks

Graph Neural Networks (GNNs) have gained significant attention in various domains due to their ability to model and extract information from graph-structured data. In the context of bike rental systems, GNNs offer a promising approach to capture the complex relationships between bike stations, users, and other relevant entities.

GNNs allow us to represent the bike rental system as a graph, with bike stations as nodes and rental patterns as edges. By incorporating graph convolutions, GNNs can aggregate and propagate information across the network, enabling us to make predictions and draw insights.

Temporal Graph Neural Networks (TGNs) extend the capabilities of GNNs by considering temporal dynamics within the graph. As bike rentals exhibit temporal dependencies, TGNs enable us to capture the change in user behavior over time, improve prediction accuracy, and better understand long-term trends.

Utilizing GNNs and TGNs, we can harness the power of graph-based modeling to tackle challenges such as demand prediction, anomaly detection, and recommendation systems within the Bike Rental software system.

## Conclusion and Next Steps
In this blog post, we provided an introduction to the Bike Rental software system, discussed relevant datasets, and explored the application of graph neural networks and temporal graph neural networks.

In Part II of this series, we will dive into the process of transforming tabular data to PyG-Temporal format for bike datasets. Stay tuned for a detailed guide on data preparation and pre-processing techniques!

Other parts of these series (under construction):

- Part II: [Exploratory Data Analysis on Bike Rental dataset]({% post_url 2023-08-15-Bike-Part-II %})
- Part III: [How to transform bike tabular data to PyG-Temporal format?](/blog/2023/Bike-Part-III/)
- Part IV: [Machine learning on Bike rental dataset](#)

## References:
- Bike Sharing Dataset. (2018). Retrieved from https://www.kaggle.com/hmavrodiev/london-bike-sharing-dataset
- Hamilton, W., Ying, Z., & Leskovec, J. (2017). Inductive representation learning on large graphs. In Advances in Neural Information Processing Systems (pp. 1025-1035).
- Su, J., Vargas, D. V., & Sakurai, K. (2019). A survey on heterogeneous data mining: from unstructured data to graphs. ACM SIGKDD Explorations Newsletter, 20(2), 5-23.

[Thumbnail image source](https://www.amazon.ae/Unicycles-Mountain-Outdoor-Unicycle-18Inch/dp/B098F53K7X)