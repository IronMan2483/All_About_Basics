# __Altair__

#### lineplot:

alt.Chart(df_weather_groupdate).mark_line().encode(x = 'date_new', y = 'temp_max')

_--> df_weather_groupdate is the name of the dataset | date_new and temp_max are the features/column names_
