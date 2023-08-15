# Rental Bike Project

## Problem Definition

The problem at hand revolves around predicting bike trip durations and the number of incoming and outgoing trips on a daily basis. The predictions will be based on various environmental and seasonal settings, which are likely to influence the patterns of bike usage. By understanding and modeling these influential factors, we aim to gain valuable insights into the dynamics of bike sharing systems and improve the overall efficiency and user experience.

Bike sharing systems have become increasingly popular in urban areas, providing a convenient and sustainable mode of transportation for residents and visitors alike. These systems often involve a fleet of bicycles distributed across multiple docking stations throughout the city. Users can rent a bike from one station and return it to another, enabling flexible point-to-point travel.

To effectively manage and optimize the bike sharing system, it is essential to have a reliable prediction model that can anticipate the demand for bikes at different stations and during different time intervals. By accurately forecasting trip durations and trip volumes, system operators can make informed decisions about resource allocation, station maintenance, and capacity planning.
## Table of Contents

##### 1-Data Collection
- Importing the necessary libraries & packages
- Loading data
- Data representation
##### 2-Exploratory Data Analysis (EDA)
- Data visualization
- Trends
- Data analysis
##### 3-Data Preprocessing
- Outlier analysis
- Data cleaning
- Feature scaling 
##### 4-Graph Creation
- Node features
- Edge creation
- Static & dynamic edges
- Graph creation
##### 5-Train & Test Split 
##### 6-Optimization
- Dimensionality reduction
- hyperparameter optimization
##### 7-Model Development
##### 8-Cross Validation Prediction
##### 9-Models Performances
- Optimization impacts on models
- Models comparison
##### 10-Model Evaluation Metrics
##### 11-Conclusion 


## Goal and Hypothesis

The primary goal of this project is to develop a predictive model that can accurately forecast bike trip durations and the number of incoming and outgoing trips on a daily basis in a bike sharing system. The model will utilize environmental and seasonal settings as input features to capture the various factors that influence bike usage patterns. By achieving this goal, we aim to enhance the efficiency and reliability of the bike sharing system, leading to improved user satisfaction and a more sustainable and accessible transportation option for urban communities.

Based on the graph dataset and the available environmental and seasonal settings, we hypothesize that certain factors will significantly impact bike trip durations and the volume of incoming and outgoing trips. We expect that variables such as day of the week, time of day, and seasonal variations will play a crucial role in determining bike usage patterns.

By testing and analyzing these hypotheses through data exploration and modeling techniques, we aim to gain a deeper understanding of the relationships between the input features and the target variables. This knowledge will allow us to build a robust predictive model that accurately captures the dynamics of the bike sharing system and aids in making informed decisions for system optimization and planning.

Let's start our journey by collecting and exploring the data to uncover valuable insights for our rental bike project!


#### We have two datasets named bikeshare and divvtbikes. In the following, we will examine these two.

Here we have some statical reports on both dataset.

trips per hour in a month:
    bikeshare
        {% include figure.html path="assets\img\GNN\b1.png" class="img-fluid rounded z-depth-1" %}

    divvybikes
        {% include figure.html path="assets\img\GNN\d1.png" class="img-fluid rounded z-depth-1" %}

Histogram of Number of Stations with a certain number of Arrivals+Departures in a Week:
    bikeshare
        {% include figure.html path="assets\img\GNN\b2.png" class="img-fluid rounded z-depth-1" %}

    divvybikes
        {% include figure.html path="assets\img\GNN\d2.png" class="img-fluid rounded z-depth-1" %}

We also analyze patterns in the monthly, weekly, and daily periods of both datasets to extract valuable information.

weekly (divvybikes):
    {% include figure.html path="assets\img\GNN\d3.png" class="img-fluid rounded z-depth-1" %}

working days vs weekend (divvybikes):
    {% include figure.html path="assets\img\GNN\d4.png" class="img-fluid rounded z-depth-1" %}

daily (divvybikes):
    {% include figure.html path="assets\img\GNN\d5.png" class="img-fluid rounded z-depth-1" %}


Graph creation is an important step but before this cell we have to take some steps such as Edge creation, Static & dynamic edges and etc.

Now we create a dataset object for temporal signals defined on a dynamic graph.
{% raw %}
from torch_geometric_temporal.signal import DynamicGraphTemporalSignal
dataset = DynamicGraphTemporalSignal(
            edge_indices, edge_features, xs, ys, y_indices=y_indices
        )
{% endraw %}

edge_indices: A tensor containing the indices of the edges in the graph.
edge_features: A tensor containing the features of the edges in the graph.
xs: A tensor containing the node features for each time step.
ys: A tensor containing the target values for each time step.
y_indices: A tensor containing the indices of the target values in the ys tensor (optional).
The resulting dataset object can be used for training and testing machine learning models that operate on spatiotemporal data.









