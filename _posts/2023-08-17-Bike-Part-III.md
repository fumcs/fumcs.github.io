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

As previously discussed in the initial two sections, we possess two datasets requiring conversion into graphs subsequent to the Exploratory Data Analysis (EDA) phase. In the subsequent content, we will delve into the procedural steps of this particular stage.

bikeshare and divvybikes

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c1.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c1.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

note:We need to create a new feature called "duration" for the DivvyBike dataset.

## Node features

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c2.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c2.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}




## Edge creation

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c3.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c3.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


## Static & dynamic edges

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c4.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c4.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

## Graph creation

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c5.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c5.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c6.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c6.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}



Graph creation is an important step but before this cell we have to take some steps such as Edge creation, Static & dynamic edges and etc.

Now we create a dataset object for temporal signals defined on a dynamic graph.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/rental_bike/part_III/c7.ipynb"| relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/rental_bike/part_III/c7.ipynb %}{% endcapture %}
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

[Thumbnail image source](https://mymodernmet.com/sergii-gordieiev-cool-bike-with-two-half-wheels/)