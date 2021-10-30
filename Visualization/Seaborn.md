# __Seaborn__

## __Import__

To be able to use Seaborn you need to import Matplotlib before!
````
import seaborn as sns
import matplotlib.pyplot as plt
sns.set_theme(style="ticks", color_codes=True)
````
---
---

## __Plot with categorical data__

[Seaborn Tutorial](http://seaborn.pydata.org/tutorial/categorical.html?highlight=bar%20plot)

### __Categorical scatterplots:__

* stripplot() (with kind="strip"; the default)
* swarmplot() (with kind="swarm")

### __Categorical distribution plots:__

* boxplot() (with kind="box")
* violinplot() (with kind="violin")
* boxenplot() (with kind="boxen")

### __Categorical estimate plots:__

* pointplot() (with kind="point")
* barplot() (with kind="bar")
* countplot() (with kind="count")

---
---

## __CODE SNIPPETS__

#### barplots:

* __version 1:__
````
  plt.axhline(y=scores.mean(), color='y', linestyle='-')

  sns.barplot(x=[1,2,3,4, 5],y=scores).set_title('_title_name_');
````
<br />

  _--> this means the mean of the dataset is in a yellow line_

<br />

* __version2:__
````
  plt.figure(figsize=(14,6)) 

  plt.ylim(0, 1000)
  
  plt.xticks(rotation = 45)

  sns.barplot(x='_column_name1_', y='_Count_feature/column_name2_', hue='_column_name_(e.g. gender)', data=gender_top10);
````  
<br />

  _--> y axis limit at 1000 to better see smaller values_

  _--> gender_top10_ is a created subset of the original dataset and the name of it | also possible to name it as the dataset name without .csv_


---

#### boxplots:
````
  sns.boxplot(x='_feature/column name1_', y='_feature/column name2_', data=_name of the dataset/data_drop_, palette='hls');
````
---

#### countplot:
````
  plt.title('_column/feature name Count_')

  sns.countplot(x=_dataset_name.feature/column_name_);
````  
__OR as a 1-liner__
````  
  sns.countplot(data=_data_name_, x='_feature/column_name1_', hue='_feature/column_name2_')
````  
  _--> seaborn automatically creates the bars in the plot, the colours, the legend including sns-created categories (e.g. column "sex" - categories "male" "female" "not named")_
  
__OR as another 1-Liner__
````
  sns.countplot(x='_category_',data=_dataset_name_, palette='hls');
````  
  _--> to check if it also works with categories not an int (here 1 or 0)
  

---

#### displot:
````
sns.displot(_dataset_name_['_feature/column_name_'], bins=20)
````
_--> bins means number of bars_

---

#### heatmaps:

* heatmap to show correlation /independence between features instead of a pairplot
````
  sns.heatmap(df.corr())
````
__OR__
````
  sns.heatmap(titanic_dmy.corr(), annot=True);
````
<br />

  _--> df is the dataset name and corr() shows the correlation between the different features (columns)_

  _--> to also see the values __add annot=True);__ _

<br />

* heatmap for a confusion matrix using pandas crosstab: 
````
  confusion_matrix = pd.crosstab(y_test, y_pred, rownames=['_row_name_'], colnames=['_column_name_'])

  sns.heatmap(confusion_matrix, annot=True);
````  
<br />

  _--> __annot=True);__ to show also the values in the matrix_

<br />

* heatmap for a confusion matrix using confusion_matrix from sklearn:
````
  cfm = metrics.confusion_matrix(y_test, y_pred)

  sns.heatmap(cfm, cmap='YlGnBu', annot=True, fmt='d', linewidths=.5);
````
---

#### histogram:
````
  sns.histplot(df["_column_name/feature_"])
````

---

#### lineplot:

````
plt.figure(figsize=(12, 6), dpi=80)

sns.lineplot(data = datasetname, x = datasetname['column1'], y = datasetname['column2'])

plt.tick_params(rotation=45, axis='x')

plt.title('title')

plt.xlabel('x name')

plt.ylabel('y name')

plt.legend()

plt.show();
````

<br />

_--> plt.legend() must be the last step before plt.show()


---

#### pairplot:
````
  sns.pairplot(dataset_name);

  sns.pairplot(_dataset_name_, hue="_column_name/feature_", height=3);
```` 

---

#### scatterplot:
````  
  sns.scatterplot(x='_feature_one_', y='_feature_two_', data=_dataset_name_)


---
