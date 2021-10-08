# __Visualization__

1. Import Packages
2. Matplotlib
3. Seaborn
4. Plotly
5. Maps


---

## __Import packages__ 

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

import plotly.express as px


---

## __Matplotlib__

#### scatterplot:

plt.scatter(x, y, c=y, cmap='rainbow');

---

## __Seaborn__

#### barplots:

plt.axhline(y=scores.mean(), color='y', linestyle='-')

_--> this means the mean of the dataset is in a yellow line_

sns.barplot(x=[1,2,3,4, 5],y=scores).set_title('_title_name_');

<br />

#### countplot:

plt.title('_column/feature name Count_')
sns.countplot(x=_dataset_name.feature/column_name_);

<br />

#### heatmaps:

sns.heatmap(df.corr())

_--> df is the dataset name and corr() shows the correlation between the different features (columns)_

<br />

* heatmap for a confusion matrix using pandas crosstab: 

confusion_matrix = pd.crosstab(y_test, y_pred, rownames=['_row_name_'], colnames=['_column_name_'])

sns.heatmap(confusion_matrix, annot=True);

_--> annot=True); to show also the values in the matrix_

<br />

* heatmap for a confusion matrix using confusion_matrix from sklearn:

cfm = metrics.confusion_matrix(y_test, y_pred)

sns.heatmap(cfm, cmap='YlGnBu', annot=True, fmt='d', linewidths=.5);

<br />

#### histogram:

sns.histplot(df["_column_name/feature_"])

<br />

#### pairplot:

sns.pairplot(_dataset_name_, hue="_column_name/feature_", height=3);


#### scatterplot:

sns.scatterplot(x='_feature_one_', y='_feature_two_', data=_dataset_name_)


