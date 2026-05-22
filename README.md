### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22-05-26
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
df = pd.read_csv("clustervisitor.csv")
df

# Perform segmentation based on characteristics (e.g., age groups)
cluster = {'Young':(df['Age']<=30),'Middle':((df['Age']>30) & (df['Age']<=50)),'Old':(df['Age']>50)}
count=[]
for g,v in cluster.items():
    visitor = df[v]
    print(f"The visitors in {g} Group are\n",visitor)
    print("counts",len(visitor))
    count.append(len(visitor))


```
### Output:

<img width="439" height="214" alt="image" src="https://github.com/user-attachments/assets/3879955b-bb92-467e-9ac6-44234b26beee" />

<img width="416" height="548" alt="image" src="https://github.com/user-attachments/assets/56f4c7ca-9859-4a91-8998-872277f4dbea" />

### Visualization:
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:

<img width="833" height="630" alt="image" src="https://github.com/user-attachments/assets/1988685d-8e61-4c9d-a7b5-8151044c036f" />


### Result:

Thus the python program for implementing Cluster and Visitor Segmentation for Navigation patterns was executed Successfully.
