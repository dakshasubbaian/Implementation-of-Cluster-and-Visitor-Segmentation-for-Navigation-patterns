# EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns

## DEVELOPED BY:
```
REGISTER NUMBER: 212223230036
NAME: DAKSHA SUBBAIAN
```

### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.

### Description:

Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, or services to meet the specific needs and preferences of each cluster.

### Procedure:

1. Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2. Define Gender Groups by creating two groups: Male and Female.
3. Segment Visitors by filtering the visitors into respective gender groups.
4. Visualize the result using matplotlib.

### Program:

```python
# Visitor segmentation based on characteristics

import pandas as pd
import matplotlib.pyplot as plt

# Read the data
df = pd.read_csv("clustervisitor.csv")

# Perform segmentation based on characteristics (e.g., gender groups)

male_cluster = df[df["Gender"].str.lower() == "male"]
female_cluster = df[df["Gender"].str.lower() == "female"]

print("Cluster 1 - Male Visitors:")
print(male_cluster)

print("\nCluster 2 - Female Visitors:")
print(female_cluster)
```

### Output:
<img width="405" height="768" alt="image" src="https://github.com/user-attachments/assets/eb2d3dab-86b7-4429-9f1d-9820057568db" />

### Visualization:

```python
# Create a list to store counts of visitors in each gender group

visitor_counts = []

# Count visitors in each gender group

visitor_counts.append(len(male_cluster))
visitor_counts.append(len(female_cluster))

# Define gender group labels and plot a scatter plot

gender_group_labels = ["Male", "Female"]

plt.figure(figsize=(8, 6))

plt.scatter(
    male_cluster.index,
    [1] * len(male_cluster),
    label="Male",
    color="blue"
)

plt.scatter(
    female_cluster.index,
    [2] * len(female_cluster),
    label="Female",
    color="red"
)

plt.xlabel("Visitor Index")
plt.ylabel("Cluster")
plt.title("Visitor Segmentation - Male and Female")
plt.yticks([1, 2], gender_group_labels)
plt.legend()
plt.grid(True)
plt.show()
```

### Output:

<img width="773" height="598" alt="image" src="https://github.com/user-attachments/assets/32263371-5a4c-4bfd-9e3f-4126a5bb7bde" />


### Result:

Thus, visitor segmentation based on gender was successfully implemented and visualized using Python and Matplotlib.
