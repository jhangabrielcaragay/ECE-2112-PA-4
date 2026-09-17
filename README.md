# ECE-2112-PA-4
Jhan Gabriel V. Caragay | 2ECE-D

This programming assignment uses **Python Data Analysis** ```(Pandas)``` and a **Python plotting library** ```(Matplotlib)``` to demonstrate different techniques for filtering tabular data, constructing focused DataFrames, summarizing categorical data, and visualizing group means using the ECE Board Exam 2 dataset.

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

We load the **.xlsx file** into a DataFrame named ```board2``` and computed for the student's average using the code:

```python
board2 = pd.read_excel('board2.xlsx')
board2['Average'] = (board2['Math'] + board2['Electronics'] + board2['GEAS'] + board2['Communication']) / 4
board2
```

> This will then be used in the entirety of the programming assignment.

Calling the DataFrame will show the following data:

| Name | Gender | Track | Hometown | Math | Electronics | GEAS | Communication | Average |
|------|--------|-------|----------|------|-------------|------|---------------|---------|
| S1   | Male   | Instrumentation  | Luzon    | 58 | 89 | 75 | 78 | 75.00 |
| S2   | Female | Communication    | Mindanao | 52 | 75 | 90 | 52 | 67.25 |
| S3   | Female | Instrumentation  | Mindanao | 83 | 74 | 77 | 57 | 72.75 |
| S4   | Male   | Instrumentation  | Visayas  | 65 | 58 | 91 | 68 | 70.50 |
| S5   | Male   | Communication    | Luzon    | 59 | 86 | 43 | 88 | 69.00 |
| S6   | Female | Microelectronics | Visayas  | 88 | 45 | 86 | 83 | 75.50 |
| S7   | Female | Instrumentation  | Luzon    | 66 | 60 | 60 | 48 | 58.50 |
| S8   | Male   | Instrumentation  | Luzon    | 49 | 81 | 64 | 53 | 61.75 |
| S9   | Male   | Instrumentation  | Luzon    | 50 | 36 | 63 | 42 | 47.75 |
| S10  | Male   | Microelectronics | Mindanao | 80 | 84 | 61 | 44 | 67.25 |
| S11  | Female | Communication    | Visayas  | 48 | 56 | 48 | 67 | 54.75 |
| S12  | Male   | Communication    | Visayas  | 89 | 67 | 84 | 64 | 76.00 |
| S13  | Female | Microelectronics | Luzon    | 88 | 35 | 83 | 43 | 62.25 |
| S14  | Female | Microelectronics | Luzon    | 83 | 77 | 89 | 73 | 80.50 |
| S15  | Female | Microelectronics | Mindanao | 69 | 41 | 40 | 86 | 59.00 |
| S16  | Female | Communication    | Luzon    | 71 | 70 | 87 | 81 | 77.25 |
| S17  | Female | Microelectronics | Mindanao | 81 | 79 | 77 | 45 | 70.50 |
| S18  | Male   | Communication    | Visayas  | 81 | 40 | 81 | 52 | 63.50 |
| S19  | Male   | Microelectronics | Luzon    | 79 | 63 | 79 | 71 | 73.00 |
| S20  | Female | Communication    | Mindanao | 59 | 60 | 62 | 85 | 66.50 |
| S21  | Female | Microelectronics | Visayas  | 83 | 51 | 68 | 72 | 68.50 |
| S22  | Female | Communication    | Visayas  | 64 | 39 | 89 | 58 | 62.50 |
| S23  | Male   | Instrumentation  | Luzon    | 84 | 70 | 74 | 47 | 68.75 |
| S24  | Female | Microelectronics | Visayas  | 85 | 45 | 60 | 41 | 57.75 |
| S25  | Male   | Communication    | Luzon    | 74 | 91 | 94 | 42 | 75.25 |
| S26  | Female | Instrumentation  | Visayas  | 71 | 47 | 83 | 62 | 65.75 |
| S27  | Male   | Microelectronics | Visayas  | 70 | 47 | 40 | 86 | 60.75 |
| S28  | Male   | Communication    | Visayas  | 85 | 53 | 80 | 53 | 67.75 |
| S29  | Male   | Instrumentation  | Mindanao | 73 | 48 | 71 | 62 | 63.50 |
| S30  | Male   | Instrumentation  | Luzon    | 78 | 81 | 57 | 56 | 68.00 |

> Again, this will then be used in the entirety of the programming assignment.

# A. VISAYAS COMMUNICATION DATAFRAME

### **OBJECTIVE**

The first problem requires creating a new **DataFrame** named ```VisComm``` by filtering the source dataset for students whose **Hometown** is ```Visayas``` and whose **Track** is ```Communication```. From the filtered data, the required columns **Name**, **Gender**, **Math**, **Electronics**, and **Average** are selected in the specified order. The resulting DataFrame and its number of rows are then displayed.

### **DISCUSSION**

We first create a DataFrame named ```VisComm```. We then use the uploaded ```.xslx file``` named **board2** together with the ```.loc``` function to specify our parameters using the code:
```python
VisComm = board2.loc[
    (board2['Hometown'] == 'Visayas') &
    (board2['Track'] == 'Communication'),
    ['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```
> This selects the specific **students** that are needed in this part. 

We then print out our **DataFrame** using the code:
```python
display(VisComm)
print('Number of rows:', VisComm.shape[0])
```
> ```.shape[0]``` was used to see the ```number of rows``` **only**.  

This code outputs:

| Index | Name | Gender | Math | Electronics | Average |
|------:|------|--------|-----:|------------:|--------:|
| 10 | S11 | Female | 48 | 56 | 54.75 |
| 11 | S12 | Male | 89 | 67 | 76.00 |
| 17 | S18 | Male | 81 | 40 | 63.50 |
| 21 | S22 | Female | 64 | 39 | 62.50 |
| 27 | S28 | Male | 85 | 53 | 67.75 |

```python
Number of rows: 5
```

### **OVERALL STRUCTURE**

```python
VisComm = board2.loc[
    (board2['Hometown'] == 'Visayas') &
    (board2['Track'] == 'Communication'),
    ['Name', 'Gender', 'Math', 'Electronics', 'Average']
]
display(VisComm)
print('Number of rows:', VisComm.shape[0])
```

| Index | Name | Gender | Math | Electronics | Average |
|------:|------|--------|-----:|------------:|--------:|
| 10 | S11 | Female | 48 | 56 | 54.75 |
| 11 | S12 | Male | 89 | 67 | 76.00 |
| 17 | S18 | Male | 81 | 40 | 63.50 |
| 21 | S22 | Female | 64 | 39 | 62.50 |
| 27 | S28 | Male | 85 | 53 | 67.75 |

```python
Number of rows: 5
```

# B. VISAYAS FEMALE DATAFRAME

### **OBJECTIVE**

The second problem requires creating ```VisFemale``` by filtering students from **Visayas** who are ```Female```, then selecting **Name**, **Track**, **GEAS**, **Electronics**, and **Average**. It also displays students with an **Average** of at least ```60``` without overwriting VisFemale.

### **DISCUSSION**

We first create a DataFrame named ```VisFemale```. We then use the uploaded ```.xslx file``` named **board2** together with the ```.loc``` function to specify our parameters using the code:

```python
VisFemale = board2.loc[
    (board2['Hometown'] == 'Visayas') &
    (board2['Gender'] == 'Female'),
    ['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
```

> This selects the specific **students** that are needed in this part. 

We then print out our DataFrame using the code:
```python
display(VisFemale)
```
This code outputs:

| Name | Track | GEAS | Electronics | Average |
|------|-------|------|-------------|---------|
| S6   | Microelectronics | 86 | 45 | 75.50 |
| S11  | Communication | 48 | 56 | 54.75 |
| S21  | Microelectronics | 68 | 51 | 68.50 |
| S22  | Communication | 89 | 39 | 62.50 |
| S24  | Microelectronics | 60 | 45 | 57.75 |
| S26  | Instrumentation | 83 | 47 | 65.75 |

Lastly, we display the rows of ```VisFemale``` whose **Average** is at least 60 using the code:
```python
VisFemale.loc[VisFemale['Average']>60]
```
This outputs:
| Name | Track | GEAS | Electronics | Average |
|------|-------|------|-------------|---------|
| S6   | Microelectronics | 86 | 45 | 75.50 |
| S21  | Microelectronics | 68 | 51 | 68.50 |
| S22  | Communication    | 89 | 39 | 62.50 |
| S26  | Instrumentation  | 83 | 47 | 65.75 |




### **OVERALL STRUCTURE**

```python
VisFemale = board2.loc[
    (board2['Hometown'] == 'Visayas') &
    (board2['Gender'] == 'Female'),
    ['Name', 'Track', 'GEAS', 'Electronics', 'Average']
    ]
display(VisFemale)
```
| Name | Track | GEAS | Electronics | Average |
|------|-------|------|-------------|---------|
| S6   | Microelectronics | 86 | 45 | 75.50 |
| S11  | Communication | 48 | 56 | 54.75 |
| S21  | Microelectronics | 68 | 51 | 68.50 |
| S22  | Communication | 89 | 39 | 62.50 |
| S24  | Microelectronics | 60 | 45 | 57.75 |
| S26  | Instrumentation | 83 | 47 | 65.75 |

```python
VisFemale.loc[VisFemale['Average']>60]
```
| Name | Track | GEAS | Electronics | Average |
|------|-------|------|-------------|---------|
| S6   | Microelectronics | 86 | 45 | 75.50 |
| S21  | Microelectronics | 68 | 51 | 68.50 |
| S22  | Communication    | 89 | 39 | 62.50 |
| S26  | Instrumentation  | 83 | 47 | 65.75 |




# C. CATEGORY-AVERAGE VISUALIZATION

### **OBJECTIVE**

The third problem requires examining how the recorded Average differs across the categorical features **Track**, **Gender**, and **Hometown**. For each feature, the **mean** of ```Average``` is computed for every category using ```Pandas```, and the resulting summary tables are displayed. A single figure is then created containing three ```bar charts``` showing the **mean Average** by **Track**, **Gender**, and **Hometown**. Finally, three **concise statements** identify the category with the highest sample mean for each feature based on the observed dataset.

### **DISCUSSION**





### **OVERALL STRUCTURE**
```python
Track_Average = board2.groupby('Track')['Average'].mean().reset_index()
display(Track_Average)

Gender_Average = board2.groupby('Gender')['Average'].mean().reset_index()
display(Gender_Average)

Hometown_Average = board2.groupby('Hometown')['Average'].mean().reset_index()
display(Hometown_Average)

plt.figure(figsize=(20,5))
plt.subplot(1,3,1)
plt.bar(Track_Average['Track'], Track_Average['Average'])
plt.title('By Track')
plt.xlabel("Track")
plt.ylabel('Mean')

plt.subplot(1,3,2)
plt.bar(Gender_Average['Gender'], Gender_Average['Average'])
plt.title('By Gender')
plt.xlabel("Gender")
plt.ylabel('Mean')

plt.subplot(1,3,3)
plt.bar(Hometown_Average['Hometown'], Hometown_Average['Average'])
plt.title('By Hometown')
plt.xlabel("Hometown")
plt.ylabel('Mean')

```

# History

September 17, 2026 - .ipynb file and .xlsx file were attached and README.md file was edited.

September 14, 2026 - README.md file edited.

September 11, 2026 - README.md file created.
