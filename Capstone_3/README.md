# U.S. Car Accidents per State Time Series

## Car Accidents

<p float="center">
<img src="https://github.com/soccershowman/Springboard/blob/master/Capstone_3/figures/traffic.jpg" height="400" width="1000"/> 
 </p>

It is fair to say that accidents on the road are a major problem in urban areas.  Traffic congentions in rush hour are often made worse by an accident on the road.  The real problem is that the injuries caused by car accidents are a major problem in the healthcare industry because the truth is that [road traffic creasshes are a leading couse of death in the United States for people 1 - 54](https://www.cdc.gov/injury/features/global-road-safety/index.html).  The covid-19 pandemic may have affcted the number of accidents due to the various stay at home policies adapted per state.  This project will seek to forecast the number of accidents per state for the first quarter of 2021.

## 1. The [Data](https://www.kaggle.com/sobhanmoosavi/us-accidents)

The dataset was found in [kaggle](https://www.kaggle.com/sobhanmoosavi/us-accidents) and it contains over 4 million data on accidents in the U.S. from 2016 to 2020.  Each row of the dataset reffers to a speciffic accident.  Due to the simplistic nature of this project, the only parts of this dataset that I will use are the state in which the accident happened and the time it claims the accident happened.

## 2. Methodology

Since this project seeks to forecast the first quarter of 2021, I do not need some of the specific information that is present in the dataset.  The things I took into consideration was:

1. The data contained a robust amount of information for each individual accident record.

2. Though the plan is forecast a quarter, having the amount of accidents per day would be precise enough to understand what happens in a monthly or quarterly sampling.

3. The location information in the dataset is quite rich in precision.  My plan is to simplify that to a state only data.

## 3. [Data Wrangling & Exploratory Data Analysis](https://github.com/soccershowman/Springboard/blob/master/Capstone_3/us_accidents_data_wranggling_and_eda.ipynb)

As I mentioned before, the intent of the project is to build a simple model that will be able to forecast the number of accidents per state for the first quarter of 2021.  To accomplish that goal, I initiated the project by simply getting the 'State' and 'Start_Time' from the original dataset, the 'Start_Time' column was changed to a datetime type and its name was changed to 'Date' to inply the fact that the precision needed was a daily amount.  I then created a new columns named count and gave it a value of 1 for each row.  This new column will aid in counting the total daily accidents.  The next step was to make the 'Date' column into the index and pivot the dataset making the States the new columns and the count the value.  Doing that helped when it came time to resample the data to become daily data, which automatically summed up the amount of accidents that happened in each state per day.  Now the data is ready to be used for the project.

The next part was to check on the data for the first time so a simple plot was done and it looked as follows:
<p float="center">
<img src="https://github.com/soccershowman/Springboard/blob/master/Capstone_3/figures/first_plot.jpg" height="750" width="1250"/> 
</p>

The plot illustrates that in some states the data may not have some deficiencies in 2016 and 2017 due to extreme low counts of accidents on parts or all of that priod.  To ensure a good quality model, I decided to only use the data from 2018 and beyond.  After plotting that here is how it looked:
<p float="center">
<img src="https://github.com/soccershowman/Springboard/blob/master/Capstone_3/figures/first_plot_2.jpg" height="600" width="1000"/> 
</p>

The next step in the exploratory data analysis was to check for seasonality and trends whithin the dataset.  To do that, I resampled the data by month and plotted accordingly.  Below is a sample of plots that may show some of of those traits.

<p float="left">
<img src="./figures/seasonality.jpg" height="450" width="305" /> 
<img src="./figures/trend.jpg" height="450" width="305" />
</p>
