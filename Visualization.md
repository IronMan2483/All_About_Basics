# __Visualization__

1. Import Packages
2. Matplotlib
3. Seaborn
4. Plotly
5. Altair
6. Maps

---

---

## __1. Import packages__ 

  import numpy as np

  import pandas as pd

  import matplotlib.pyplot as plt

  import seaborn as sns

  import plotly.express as px
  
  import altair as alt

---

---

## __2. Matplotlib__

#### barplot:

  plt.figure(figsize=(16,10))

  plt.xticks(rotation = 45)

  plt.xlabel=("_feature/column_name_for_x_axis_")

  plt.ylabel=("_feature/column_name_for_y_axis_")

  plt.title=("_title_")

  plt.scatter(x= _category1_['_feature/column_name_'], y=_category1_['Count'], color='red', label = '_category1_')

  plt.scatter(x= _category2_['_feature/column_name_'], y=_category2_['Count'], color='lightblue', label = '_category2_')

  plt.scatter(x= _category3_['_feature/column_name_], y=_category3_['Count'], color='darkgreen', label = '_category3_')

  plt.legend(loc='best')

  plt.show()

<br />

  _--> rotation 45° means the values on the x axis_

  _--> 3 categories means 3 categories in the legend_

  _--> important to also see the legend is to have this command on the last step before plt.show()_

  _--> loc means location of the legend: upper right, upper left, best (upper right), lower left, lower right_
  
  _--> an empty bracket behind plt.legend locates the legend in the upper left corner


---

#### lineplot:

___data preparation due to datetime:___

* data['date'] = pd.to_datetime(data['date'], format = '%Y/%m/%d')
* data['year'] = data.date.dt.year
* data['month'] = data.date.dt.month
* data['date_new'] = data.year.astype(str) + '-' + data.month.astype(str)

df_weather_groupdate = data.groupby('date_new').mean().reset_index().sort_values(['year', 'month'])

___plot:___

plt.figure(figsize=(12, 6), dpi=80)

plt.plot(df_weather_groupdate['date_new'], df_weather_groupdate['temp_max'], label = 'Max Temperature', color = 'red')

plt.plot(df_weather_groupdate['date_new'], df_weather_groupdate['temp_min'], label = 'Min Temperature', color = 'blue')

plt.tick_params(rotation=45, axis='x')

plt.title('Temperature development over time')

plt.xlabel('Time')

plt.ylabel('Temperature [°C]')

plt.legend()

plt.show();

<br />

_--> df_weather_groupdate is the name of the dataset | date_new, temp_max and temp_min are the features/column names_

_--> the first label is blue by default if you don't use color='red'_

---

#### scatterplot:

  plt.scatter(x, y, c=y, cmap='rainbow');

---

---

## __3. Seaborn__

#### barplots:

* __version 1:__

  plt.axhline(y=scores.mean(), color='y', linestyle='-')

  sns.barplot(x=[1,2,3,4, 5],y=scores).set_title('_title_name_');

<br />

  _--> this means the mean of the dataset is in a yellow line_

<br />

* __version2:__

  plt.figure(figsize=(14,6)) 

  plt.ylim(0, 1000)
  
  plt.xticks(rotation = 45)

  sns.barplot(x='_column_name1_', y='_Count_feature/column_name2_', hue='_column_name_(e.g. gender)', data=gender_top10);
  
<br />

  _--> y axis limit at 1000 to better see smaller values_

  _--> gender_top10_ is a created subset of the original dataset and the name of it | also possible to name it as the dataset name without .csv_


---

#### boxplots:

  sns.boxplot(x='_feature/column name1_', y='_feature/column name2_', data=_name of the dataset/data_drop_, palette='hls');

---

#### countplot:

  plt.title('_column/feature name Count_')

  sns.countplot(x=_dataset_name.feature/column_name_);
  
__OR as a 1-liner__
  
  sns.countplot(data=_data_name_, x='_feature/column_name1_', hue='_feature/column_name2_')
  
  _--> seaborn automatically creates the bars in the plot, the colours, the legend including sns-created categories (e.g. column "sex" - categories "male" "female" "not named")_
  
__OR as another 1-Liner__

  sns.countplot(x='_category_',data=_dataset_name_, palette='hls');
  
  _--> to check if it also works with categories not an int (here 1 or 0)
  

---

#### displot:

sns.displot(_dataset_name_['_feature/column_name_'], bins=20)

_--> bins means number of bars_

---

#### heatmaps:

* heatmap to show correlation /independence between features instead of a pairplot

  sns.heatmap(df.corr())

__OR__

  sns.heatmap(titanic_dmy.corr(), annot=True);

<br />

  _--> df is the dataset name and corr() shows the correlation between the different features (columns)_

  _--> to also see the values __add annot=True);__ _

<br />

* heatmap for a confusion matrix using pandas crosstab: 

  confusion_matrix = pd.crosstab(y_test, y_pred, rownames=['_row_name_'], colnames=['_column_name_'])

  sns.heatmap(confusion_matrix, annot=True);
  
<br />

  _--> __annot=True);__ to show also the values in the matrix_

<br />

* heatmap for a confusion matrix using confusion_matrix from sklearn:

  cfm = metrics.confusion_matrix(y_test, y_pred)

  sns.heatmap(cfm, cmap='YlGnBu', annot=True, fmt='d', linewidths=.5);


---

#### histogram:

  sns.histplot(df["_column_name/feature_"])


---

#### lineplot:

plt.figure(figsize=(12, 6), dpi=80)

sns.lineplot(data = df_weather_groupdate, x = df_weather_groupdate['date_new'], y = df_weather_groupdate['temp_max'])

sns.lineplot(data = df_weather_groupdate, x = df_weather_groupdate['date_new'], y = df_weather_groupdate['temp_min'])

plt.tick_params(rotation=45, axis='x')

plt.title('Temperature development over time')

plt.xlabel('Time')

plt.ylabel('Temperature [°C]')

plt.legend()

plt.show();

<br />

_--> df_weather_groupdate is the name of the dataset | date_new, temp_max and temp_min are the features/column names_


---

#### pairplot:

  sns.pairplot(dataset_name);

  sns.pairplot(_dataset_name_, hue="_column_name/feature_", height=3);
 

---

#### scatterplot:
  
  sns.scatterplot(x='_feature_one_', y='_feature_two_', data=_dataset_name_)


---

---

## __4. Plotly__

interactive plot to click in the values/data and enlarge if needed, need an extra command to see it in Jupyter Notebooks, in VSC visible

#### lineplot:

px.line(df_weather_groupdate, x=df_weather_groupdate['date_new'], y= df_weather_groupdate['temp_max'])

_--> df_weather_groupdate is the name of the dataset | date_new and temp_max are the features/column names_


---

---

## __5. Altair__

#### lineplot:

alt.Chart(df_weather_groupdate).mark_line().encode(x = 'date_new', y = 'temp_max')

_--> df_weather_groupdate is the name of the dataset | date_new and temp_max are the features/column names_
