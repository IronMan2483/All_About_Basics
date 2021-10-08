# __Visualization__

1. Import Packages
2. Matplotlib
3. Seaborn
4. Plotly
5. Maps

---

---

## __1. Import packages__ 

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

import plotly.express as px


---

---

## __2. Matplotlib__

#### barplot:
plt.figure(figsize=(16,10))

plt.xticks(rotation = 45)
_--> rotation 45° means the values on the x axis_

plt.xlabel=("_feature/column_name_for_x_axis_")

plt.ylabel=("_feature/column_name_for_y_axis_")

plt.title=("_title_")

plt.scatter(x= _category1_['_feature/column_name_'], y=_category1_['Count'], color='red', label = '_category1_')

plt.scatter(x= _category2_['_feature/column_name_'], y=_category2_['Count'], color='lightblue', label = '_category2_')

plt.scatter(x= _category3_['_feature/column_name_], y=_category3_['Count'], color='darkgreen', label = '_category3_')

_--> 3 categories means 3 categories in the legend_

plt.legend(loc='best')
_--> important to also see the legend is to have this command on the last step before plt.show()_
_--> loc means location of the legend: upper right, upper left, best (upper right), lower left, lower right_

plt.show()


<br />

---

#### scatterplot:

plt.scatter(x, y, c=y, cmap='rainbow');

---

---

## __3. Seaborn__

#### barplots:

* __version 1:__

plt.axhline(y=scores.mean(), color='y', linestyle='-')

_--> this means the mean of the dataset is in a yellow line_

sns.barplot(x=[1,2,3,4, 5],y=scores).set_title('_title_name_');

<br />

* __version2:__

plt.figure(figsize=(14,6))   

plt.ylim(0, 1000)
_--> y axis limit at 1000 to better see smaller values_

plt.xticks(rotation = 45)

sns.barplot(x='_column_name1_', y='_Count_feature/column_name2_', hue='_column_name_(e.g. gender)', data=gender_top10);
_--> gender_top10_ is a created subset of the original dataset and the name of it | also possible to name it as the dataset name without .csv_

<br />

---

#### countplot:

plt.title('_column/feature name Count_')

sns.countplot(x=_dataset_name.feature/column_name_);

<br />

---

#### heatmaps:

* heatmap to show correlation instead of a pairplot

sns.heatmap(df.corr())

_--> df is the dataset name and corr() shows the correlation between the different features (columns)_
_--> to also see the values __add annot=True);__ 

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

---

#### histogram:

sns.histplot(df["_column_name/feature_"])

<br />

---

#### pairplot:

sns.pairplot(_dataset_name_, hue="_column_name/feature_", height=3);

---

#### scatterplot:

sns.scatterplot(x='_feature_one_', y='_feature_two_', data=_dataset_name_)


