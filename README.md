# EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns

## DEVELOPED BY:
```
REGISTER NUMBER:212223230036
NAME:DAKSHA SUBBAIAN
```

### AIM:
To implement Cluster and Visitor Segmentation for Navigation patterns in Python.

### Description:

Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, or services to meet the specific needs and preferences of each cluster.

### Procedure:

1. Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2. Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3. Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4. Visualize the result using matplotlib.

### Program:

```python
# Visitor segmentation based on characteristics

import pandas as pd
import matplotlib.pyplot as plt

# Read the data
df = pd.read_csv("clustervisitor.csv")

# Perform segmentation based on characteristics (e.g., age groups)

age_groups = {
    'Children (0-17)': (df['Age'] >= 0) & (df['Age'] <= 17),
    'Young Adults (18-35)': (df['Age'] >= 18) & (df['Age'] <= 35),
    'Middle Adults (36-60)': (df['Age'] >= 36) & (df['Age'] <= 60),
    'Seniors (Above 60)': (df['Age'] > 60)
}

segmented_visitors = {}

for group, condition in age_groups.items():
    segmented_visitors[group] = df[condition]
    print("\n", group)
    print(segmented_visitors[group])
```

### Output:
<img width="492" height="917" alt="image" src="https://github.com/user-attachments/assets/1245cd3c-d495-4f12-aabd-320fbc7a01e0" />

### Visualization:

```python
# Create a list to store counts of visitors in each age group

visitor_counts = []

# Count visitors in each age group

for group in age_groups:
    visitor_counts.append(len(segmented_visitors[group]))

# Define age group labels and plot a bar chart

age_group_labels = list(age_groups.keys())

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```

### Output:

<img width="977" height="742" alt="image" src="https://github.com/user-attachments/assets/267a321f-17eb-4342-8735-a8f6f119f4fc" />


### Result:

Thus, visitor segmentation based on age groups was successfully implemented and visualized using Python and Matplotlib.
