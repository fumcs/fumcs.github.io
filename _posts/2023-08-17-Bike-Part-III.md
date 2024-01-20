---
layout: distill
title: Bike Rental System, Part III, PyG-Temporal dataset format
description: How to transform bike tabular data to PyG-Temporal format?
tags: distill formatting
giscus_comments: true
date: 2023-08-17
featured: false
thumbnail: assets/img/GNN/three-wheels.jpg
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
 
# Graph Creation

As previously discussed in the initial two sections, we possess a dataset requiring conversion into graphs subsequent to the Exploratory Data Analysis (EDA) phase. In the subsequent content, we will delve into the procedural steps of this particular stage.

divvybikes

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/dataset-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/dataset-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


Note: We need to create a new feature called "duration" for the DivvyBike dataset.

## Node features

The following code section adeptly processes the bike trip data, ultimately generating normalized node features that effectively encapsulate the distribution of incoming and outgoing trips for each individual bike station within the prospective graph dataset. This code section is crucial for analyzing and visualizing bike-sharing demand, which can be valuable for bike-sharing operators to plan for the distribution of stations across the service area.


{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/node_feature-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/node_feature-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}




## Edge creation

This section of the code effectively handles the trip data to calculate distances between stations and define edges for the graph. It involves the creation of a matrix that includes station pairs, their distances, and determines whether an edge should be formed between them based on a given threshold. The resulting edge matrix is a vital component in constructing the graph that represents the connectivity between bike stations.


{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/edge_creation-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/edge_creation-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}




## Static & dynamic edges

In this section of the code, we are establishing both static and dynamic edge features for the construction of the graph dataset. These features are crucial in defining the attributes and characteristics associated with the edges connecting bike stations within the graph. These components contribute to defining static and dynamic edge features for the graph dataset. Static edge features remain constant, providing important information about the connectivity between bike stations. On the other hand, dynamic edge features vary over time, capturing the evolving nature of bike-sharing demand and trip-specific attributes. This comprehensive approach ensures that the graph accurately represents the relationships and characteristics of the bike stations and their connections.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/static_dynamic_edge-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/static_dynamic_edge-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}




## Graph creation

This section of the code efficiently manages the creation of the graph dataset by iteratively processing time intervals, generating snapshots of data, calculating edge features, and organizing the necessary attributes for each interval. The outcome is a comprehensive dataset that can be utilized for training and analysis using graph-based machine learning models.


{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/graph_creation-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/graph_creation-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


This section of the code enables the presentation of a tangible example showcasing the components of the graph snapshot. It plays a crucial role in comprehending the dataset's structure and ensuring the uniformity of dimensions across different features and labels within each snapshot.


{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/exp-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/exp-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


In this code section, the utilization of the DynamicGraphTemporalSignal class from the torch_geometric_temporal.signal module enables the creation of a dynamic graph dataset. This dataset is constructed by incorporating the provided edge indices, edge features, node features, labels, and label indices.

---

The resulting dataset object, generated using the DynamicGraphTemporalSignal class, is now ready for utilization in various graph-based temporal analysis and machine learning tasks. It effectively encapsulates the dynamic graph data in a format that is compatible with PyTorch Geometric's temporal signal processing capabilities.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/DynamicGraphTemporalSignal-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/DynamicGraphTemporalSignal-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

---
edge_indices: A tensor containing the indices of the edges in the graph.

edge_features: A tensor containing the features of the edges in the graph.

xs: A tensor containing the node features for each time step.

ys: A tensor containing the target values for each time step.

y_indices: A tensor containing the indices of the target values in the ys tensor (optional).
The resulting dataset object can be used for training and testing machine learning models that operate on spatiotemporal data.
---

- Part I: [Introduction to Bike Rental Platforms, Datasets and Methods](/blog/2023/Bike-Part-I/)
- Part II: [Exploratory Data Analysis on Bike Rental dataset](/blog/2023/Bike-Part-II/)
