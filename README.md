# ECE-2112-PA-4
Jhan Gabriel V. Caragay | 2ECE-D

This programming assignment uses **Python Data Analysis** (Pandas) and a **Python plotting library** (Matplotlib) to demonstrate different techniques for filtering tabular data, constructing focused DataFrames, summarizing categorical data, and visualizing group means using the ECE Board Exam 2 dataset.

We first import the Python Data Analysis library ```Pandas```:

```python
import pandas as pd
```
> We rename it as pd to make it shorter and more efficient.

This should be done first because the remaining code in all three problems relies on functions and operations provided by the ```Pandas``` library.

Next, we also import the **Python plotting library** ```Matplotlib```:

```python
import matplotlib.pyplot as plt
```

> We rename it as plt to make it shorter and more efficient.

The last problem utilizes this library to create bar charts and visualize the mean Average across different categories.

# A. VISAYAS COMMUNICATION DATAFRAME

### **OBJECTIVE**

The first problem requires creating a new **DataFrame** named ```VisComm``` by filtering the source dataset for students whose **Hometown** is ```Visayas``` and whose **Track** is ```Communication```. From the filtered data, the required columns **Name**, **Gender**, **Math**, **Electronics**, and **Average** are selected in the specified order. The resulting DataFrame and its number of rows are then displayed.

### **DISCUSSION**

### **OVERALL STRUCTURE**



# B. VISAYAS FEMALE DATAFRAME

### **OBJECTIVE**

The second problem requires creating ```VisFemale``` by filtering students from **Visayas** who are ```Female```, then selecting **Name**, **Track**, **GEAS**, **Electronics**, and **Average**. It also displays students with an **Average** of at least ```60``` without overwriting VisFemale.


### **DISCUSSION**

### **OVERALL STRUCTURE**

# C. CATEGORY-AVERAGE VISUALIZATION

### **OBJECTIVE**

The third problem requires examining how the recorded Average differs across the categorical features **Track**, **Gender**, and **Hometown**. For each feature, the **mean** of ```Average``` is computed for every category using ```Pandas```, and the resulting summary tables are displayed. A single figure is then created containing three ```bar charts``` showing the **mean Average** by **Track**, **Gender**, and **Hometown**. Finally, three **concise statements** identify the category with the highest sample mean for each feature based on the observed dataset.

### **DISCUSSION**

### **OVERALL STRUCTURE**


# History

September 14, 2026 - README.md file edited.
September 11, 2026 - README.md file created.
