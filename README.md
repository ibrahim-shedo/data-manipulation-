# README for Weather Data Dataset

## Description

This dataset contains weather observations with the following fields:
- **Date/Time**: The date and time of the observation.
- **Temp_C**: Temperature in degrees Celsius.
- **Dew Point Temp_C**: Dew point temperature in degrees Celsius.
- **Rel Hum_%**: Relative humidity as a percentage.
- **Wind Speed_km/h**: Wind speed in kilometers per hour.
- **Visibility_km**: Visibility in kilometers.
- **Press_kPa**: Atmospheric pressure in kilopascals.
- **Weather condition**: Description of the weather condition.

## Data Overview

The dataset consists of weather records from January 3, 2012, to December 30, 2012. Each record represents a unique timestamp with corresponding weather metrics.

## Questions and Answers

1. **Find all the unique 'wind speed' values in the data**  
   ```python
   unique_wind_speeds = df['Wind Speed_km/h'].unique()
Find the number of times when 'weather is exactly clear'

python
Copy code
clear_weather_count = df[df['Weather condition'] == 'Clear'].shape[0]
Find the number of times when 'wind speed is exactly 4 km/h'

python
Copy code
wind_speed_4_count = df[df['Wind Speed_km/h'] == 4].shape[0]
Find all the null values in the dataset

python
Copy code
null_values = df.isnull().sum()
Rename the column name 'Weather' to 'Weather conditions'

python
Copy code
df.rename(columns={'Weather condition': 'Weather conditions'}, inplace=True)
What is the mean 'visibility'?

python
Copy code
mean_visibility = df['Visibility_km'].mean()
What is the STD of the 'pressure' in this data?

python
Copy code
pressure_std = df['Press_kPa'].std()
What is the variance of 'relative humidity' in this data?

python
Copy code
humidity_variance = df['Rel Hum_%'].var()
Find all instances of when 'snow' is recorded

python
Copy code
snow_instances = df[df['Weather condition'].str.contains('snow', case=False)]
Find all the instances when 'wind speed is above 25 and visibility is 25'

python
Copy code
high_wind_and_visibility_25 = df[(df['Wind Speed_km/h'] > 25) & (df['Visibility_km'] == 25)]
What is the mean value of each column against each 'weather condition'?

python
Copy code
mean_values_by_weather = df.groupby('Weather condition').mean()
What is the min and max value of each column against each 'weather condition'?

python
Copy code
min_values_by_weather = df.groupby('Weather condition').min()
max_values_by_weather = df.groupby('Weather condition').max()
Show all the records where weather condition is fog

python
Copy code
fog_records = df[df['Weather condition'].str.contains('fog', case=False)]
Find all instances where 'weather is clear or visibility is above 40'

python
Copy code
clear_or_high_visibility = df[(df['Weather condition'] == 'Clear') | (df['Visibility_km'] > 40)]
Find all instances when 'weather is clear and relative humidity is greater than 40'

python
Copy code
clear_and_high_humidity = df[(df['Weather condition'] == 'Clear') & (df['Rel Hum_%'] > 40)]
Notes
Make sure to preprocess the dataset for any missing or malformed data before performing these operations.
Use appropriate libraries such as pandas in Python to handle the dataset and perform the analysis.
