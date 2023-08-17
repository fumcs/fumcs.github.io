---
layout: distill
title: Bike Rental System, Part III, PyG-Temporal dataset format
description: Transforming Tabular data to PyG-Temporal dataset format
tags: distill formatting
giscus_comments: true
date: 2023-08-17
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
 
# Graph Creation

As previously discussed in the initial two sections, we possess two datasets requiring conversion into graphs subsequent to the Exploratory Data Analysis (EDA) phase. In the subsequent content, we will delve into the procedural steps of this particular stage.

bikeshare and divvybikes

{% include figure.html path="assets/img/GNN/f1.png" class="img-fluid rounded z-depth-1" %}

note:We need to create a new feature called "duration" for the DivvyBike dataset.

## Node features

{% raw %}
```python
#considering the incoming & outgoing trips features of every node
outgoing_trips = trips.groupby("start_station_id").count()["id"].values
incoming_trips = trips.groupby("end_station_id").count()["id"].values

all_station_ids = set(trips["start_station_id"].unique()) | set(trips["end_station_id"].unique())

outgoing_trips = np.pad(outgoing_trips, (0, len(all_station_ids) - len(outgoing_trips)), mode='constant')
incoming_trips = np.pad(incoming_trips, (0, len(all_station_ids) - len(incoming_trips)), mode='constant')

outgoing_trips = (outgoing_trips - np.min(outgoing_trips)) / (np.max(outgoing_trips) - np.min(outgoing_trips))
incoming_trips = (incoming_trips - np.min(incoming_trips)) / (np.max(incoming_trips) - np.min(incoming_trips))

node_features = np.stack([outgoing_trips, incoming_trips]).transpose()
print("Full shape: ", node_features.shape)
node_features[:10]
```
{% endraw %}




## Edge creation

{% raw %}
```python
subset = ["start_lng", "start_lat", "start_station_id"]
all_starts = trips.drop_duplicates(subset="start_station_id", keep="first")[subset]

subset = ["end_lng", "end_lat", "end_station_id"]
all_ends = trips.drop_duplicates(subset="end_station_id", keep="first")[subset]
distance_matrix = all_ends.merge(all_starts, how="cross")
distance_matrix["distance"] = distance_matrix.apply(lambda x: geodesic((x["start_lat"], x["start_lng"]), 
                                                        (x["end_lat"], x["end_lng"])).meters, axis=1)
#considering a specific treshhold
distance_matrix["edge"] = distance_matrix["distance"] < 500
```
{% endraw %}


## Static & dynamic edges

{% raw %}
```python
edge_index = distance_matrix[distance_matrix["edge"] == True][["start_station_id", "end_station_id"]].values
edge_index = edge_index.transpose()

distance_feature = distance_matrix[distance_matrix["edge"] == True]["distance"].values
edge_type_feature = np.zeros_like(distance_feature)
trip_duration_feature = np.zeros_like(distance_feature)
static_edge_features = np.stack([distance_feature, edge_type_feature, trip_duration_feature]).transpose()
```
{% endraw %}



{% raw %}
```python
def extract_dynamic_edges(s):

    trip_indices = s[["start_station_id", "end_station_id"]].values
    trip_durations = s["duration"]


    distance_feature  = pd.DataFrame(trip_indices, 
                                    columns=["start_station_id", "end_station_id"]).merge(
                                        distance_matrix, on=["start_station_id", "end_station_id"], 
                                        how="left")["distance"].values
    edge_type_feature = np.ones_like(distance_feature) 
    trip_duration_feature = trip_durations
    edge_features = np.stack([distance_feature, edge_type_feature, trip_duration_feature]).transpose()
    return edge_features, trip_indices.transpose()
```
{% endraw %}

## Graph creation

{% raw %}
```python
start_date = datetime.strptime("2023-04-01 00:00:30", "%Y-%m-%d %H:%M:%S")
end_date = datetime.strptime("2023-05-01 00:00:00", "%Y-%m-%d %H:%M:%S")

interval = timedelta(minutes=60)

xs = []
edge_indices = []
ys = []
y_indices = []
edge_features = []


while start_date <= end_date:
    # 0 - 60 min 
    current_snapshot = trips[((start_date + interval) >= trips["end_date"])
                                & (start_date <= trips["end_date"])]
    # 60 - 120 min
    subsequent_snapshot = trips[((start_date + 2*interval) >= trips["end_date"])
                                & (start_date + interval <= trips["end_date"])]
    current_snapshot = current_snapshot.groupby(["start_station_id", "end_station_id"]).mean().reset_index()
    subsequent_snapshot = subsequent_snapshot.groupby(["start_station_id", "end_station_id"]).mean().reset_index()

    edge_feats, additional_edge_index = extract_dynamic_edges(current_snapshot)
    exteneded_edge_index = np.concatenate([edge_index, additional_edge_index], axis=1)
    extended_edge_feats = np.concatenate([edge_feats, static_edge_features], axis=0)

    y = subsequent_snapshot["duration"].values
    y_index = subsequent_snapshot[["start_station_id", "end_station_id"]].values

    xs.append(node_features)
    edge_indices.append(exteneded_edge_index) 
    edge_features.append(extended_edge_feats)
    ys.append(y) 
    y_indices.append(y_index.transpose()) 

    start_date += interval
```
{% endraw %}




Graph creation is an important step but before this cell we have to take some steps such as Edge creation, Static & dynamic edges and etc.

Now we create a dataset object for temporal signals defined on a dynamic graph.

{% raw %}

```python
from torch_geometric_temporal.signal import DynamicGraphTemporalSignal
dataset = DynamicGraphTemporalSignal(
            edge_indices, edge_features, xs, ys, y_indices=y_indices
        )
```

{% endraw %}


edge_indices: A tensor containing the indices of the edges in the graph.

edge_features: A tensor containing the features of the edges in the graph.

xs: A tensor containing the node features for each time step.

ys: A tensor containing the target values for each time step.

y_indices: A tensor containing the indices of the target values in the ys tensor (optional).
The resulting dataset object can be used for training and testing machine learning models that operate on spatiotemporal data.