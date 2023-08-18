---
layout: distill
title: Bike Rental System, Part III, PyG-Temporal dataset format
description: Transforming Tabular data to PyG-Temporal dataset format
tags: distill formatting
giscus_comments: true
date: 2023-08-17
featured: true
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

note: We need to create a new feature called "duration" for the DivvyBike dataset.

## Node features

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

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/graph_creation-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/graph_creation-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/exp-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/exp-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}



Graph creation is an important step but before this cell we have to take some steps such as Edge creation, Static & dynamic edges and etc.

Now we create a dataset object for temporal signals defined on a dynamic graph.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/DynamicGraphTemporalSignal-divvybikes.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/DynamicGraphTemporalSignal-divvybikes.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


edge_indices: A tensor containing the indices of the edges in the graph.

edge_features: A tensor containing the features of the edges in the graph.

xs: A tensor containing the node features for each time step.

ys: A tensor containing the target values for each time step.

y_indices: A tensor containing the indices of the target values in the ys tensor (optional).
The resulting dataset object can be used for training and testing machine learning models that operate on spatiotemporal data.

<!-- [Thumbnail image source00](https://mymodernmet.com/sergii-gordieiev-cool-bike-with-two-half-wheels/) -->

[Thumbnail image source](https://bicycle2work.com/guide-to-3-wheel-bicycles/)