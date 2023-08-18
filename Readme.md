Kshitij Prabhu  

NEU ID: 002769231

Email: prabhu.ks@northeastern.edu

# Basic Data Statistics

## Introduction

Basic data statistics involve analyzing and summarizing data to gain insights into its characteristics. Python offers several libraries, such as NumPy and pandas, that provide tools for performing statistical analysis on datasets.

```python
import numpy as np
import pandas as pd
#importing all the required libraries
```

```python
data = np.array([2, 2, 4, 6, 8, 10]) #creating a numpy array using np.array()
data_dict = {'values': [2, 4, 6, 8, 10]} 
df = pd.DataFrame(data_dict) #creating a dataframe
```

## Mean, Median, and Mode

When analyzing data, it is important to understand the central tendency of the data. The three measures of central tendency are the mean, median, and mode.

The mean is the average of all the values in the data set. To calculate the mean in Python, we can use the `mean()` function from the NumPy library.

```python
#data = np.array([2, 2, 4, 6, 8, 10]) 
mean = np.mean(data)#using the mean() function on data array
# the output we get shoulf be **5.33**
```

The median is the middle value in the data set when the values are arranged in order. To calculate the median in Python, we can use the `median()` function from the NumPy library.

```python
#data = np.array([2, 2, 4, 6, 8, 10]) 
median = np.median(data)#using the median() function on data array
# the output we get should be **5.0**
```

The **mode** is the value that occurs most frequently in the data set. To calculate the mode in Python, we can use the `bincount()` function and `argmax()` from the NumPy library.

```python
#data = np.array([2, 2, 4, 6, 8, 10]) 
mode = np.bincount(data).argmax()
# the output we get should be **2.0**
```

## Standard Deviation and Variance

The standard deviation and variance are measures of the spread of the data. The standard deviation is the square root of the variance.

The variance is the average of the squared differences from the mean. To calculate the variance in Python, we can use the `var()` function from the NumPy library.

```python
#data = np.array([2, 2, 4, 6, 8, 10]) 
variance = np.var(data)
# the output we get should be **8.88**
```

The **standard deviation** is the square root of the variance. To calculate the standard deviation in Python, we can use the `std()` function from the NumPy library.

```python
#data = np.array([2, 2, 4, 6, 8, 10]) 
std_dev = np.std(data)
# the output we get should be **2.98**
```

## Correlation and Covariance

Correlation is a measure of the relationship between two variables. A correlation of 1 indicates a perfect positive relationship, a correlation of -1 indicates a perfect negative relationship, and a correlation of 0 indicates no relationship.

To calculate the correlation in Python, we can use the `corr()` function from the Pandas library.

```python
#using the dataframe that was previously created
correlation_matrix = df.corr()
```

Covariance is a statistical measure that quantifies the degree to which two random variables change together. In other words, it indicates whether the values of two variables tend to increase or decrease together or move in opposite directions. Covariance helps us understand the relationship and pattern of variability between two variables.

To calculate the correlation in Python, we can use the `cov()` function from the Pandas library.

```python
#using the dataframe that was previously created
covariance_matrix = df.cov()
```

# Exploratory Data Analysis(EDA)

## Introduction

Exploratory Data Analysis (EDA) is a crucial step in the data analysis process that involves visually and quantitatively summarizing, understanding, and interpreting the main features of a dataset. 

EDA helps data analysts and scientists to uncover patterns, relationships, anomalies, and trends within the data. Python, with its rich ecosystem of libraries, is a popular choice for performing EDA effectively.

Click on this to download the dataset : [Dataset](https://www.kaggle.com/datasets/brendan45774/test-file?resource=download)

### Importing Data

The first step in EDA is loading your dataset. Popular libraries for data manipulation include pandas, NumPy, and CSV.

```python
import pandas as pd

data = pd.read_csv('tested.csv')
```

### Data Summary

Understanding the basic characteristics of your data is essential. Use functions like **`.head()`**, **`.info()`**, **`.describe()`** to get a sense of the data's structure, types, and summary statistics.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/01a4207c-7944-41f3-a8a9-cdc899c15140/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bafee5d8-1fe6-4f33-8e50-163248e8cf4e/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/01a9d5cf-0db6-4774-a46f-e9241a2039b7/Untitled.png)

### Handling Missing Data

Missing data can skew your analysis. Identify missing values and decide on appropriate strategies for imputation or removal.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3f77d9fd-d191-438e-9621-573d53031133/Untitled.png)

### Data Visualization

Visualization is a powerful EDA tool. Libraries like Matplotlib, Seaborn, and Plotly offer various plotting options.

```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.hist(data['Survived'])
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ef4990a6-0265-4163-87d6-4c8e22000621/Untitled.png)

### Data Distribution

Understanding the distribution of your data helps in selecting appropriate statistical methods.

```python
sns.distplot(data['Survived'], bins=20)
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/56f0a778-bbb3-40f2-8c92-19ea3b7c37c5/Untitled.png)

### Correlation Analysis

Understanding relationships between variables is crucial. Calculate correlation coefficients and visualize using heatmaps. We will use the `.corr()` function we previously used.

```python
correlation_matrix = data.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/89aa93eb-c63c-4982-8489-c3e2690b0756/Untitled.png)

## Conclusion

Exploratory Data Analysis is a flexible process, where the techniques applied depend on the dataset and the insights you're seeking. Python's versatility and powerful libraries make it an excellent choice for effectively performing EDA and gaining a deep understanding of your data.
