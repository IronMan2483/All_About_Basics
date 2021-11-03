# __Matplotlib__

#### barplot:

  plt.figure(figsize=(16,10))
  
  country.max().sort_values(by="points",ascending=False)["points"].plot.bar()

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
