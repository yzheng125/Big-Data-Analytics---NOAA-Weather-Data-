# Project-Group-2
Group Member: Ansheng Huang, Hao Ni, Yue Zheng, Ziwei Yang

## Overview
The dataset we used is about daily global surface summary from over 9000 weather stations from 1929 to now.
The daily elements included in the dataset (as available from each station) are: Mean temperature (.1 Fahrenheit) Mean dew point (.1 Fahrenheit) Mean sea level pressure (.1 mb) Mean station pressure (.1 mb) Mean visibility (.1 miles) Mean wind speed (.1 knots) Maximum sustained wind speed (.1 knots) Maximum wind gust (.1 knots) Maximum temperature (.1 Fahrenheit) Minimum temperature (.1 Fahrenheit) Precipitation amount (.01 inches) Snow depth (.1 inches)
Indicator for occurrence of: Fog, Rain or Drizzle, Snow or Ice Pellets, Hail, Thunder, Tornado/Funnel

We intend to analyze the relationship between weather condition and the temperature as well as the trend of temperature and precipitation changed over the last 92 years, then using techniques of data analysis to build several models.

## Exploratory Analysis Section
The average temperature for each year:

<img src='images/1.png'>

Although temperatures increased overall during the 20th century, three distinct periods can be observed. Global warming occurued both at the beginning and at the end of the 20th century, but a cooling trend is seen from about 1940 to 1975.Early and late 20th century warming has been explained primarily by increasing solar activity and increasing CO2 concentrations, respectively, with other factors contributing in both periods. So what caused the cooling period that interrupted the overall trend in the middle of the century? The answer seems to lie in solar dimming, a cooling phenomenon caused by airborne pollutants.

<img src='images/8.png'>

As we can see from the above chart, the 'visib' value (Mean visibility for the day in miles to tenths) is continuously increasing during the past 40 years (from 1980 to 2020). And that means the overall air condition is becoming worse and worse.

<img src='images/tornado_yr.PNG'>
From the plot, the tornado frequency was relatively high from 1975 to 1990, and its frequency is decreasing in general during the past 40 years (from 1980 to 2020).

<img src='images/hail_yr.PNG'>
From the plot, the frequency to hail was highest before 1940, and then its frequency became stable in general.

The average temperature of different countries:

<img src='images/2.png'>

Djibouti has the highest average temperature (86.5 F), and Congo has the second highest temperature (85 F).

Top stations which has the most observations (999999 means unknow):

<img src='images/3.png'>

It seems that station unknown and station 949999 have the most observations of tempreture.

Plot the average temperature for each month:

<img src='images/4.png'>

The probability to rain through all the monthes:

<img src='images/rain_mo.PNG'>

The probability to rain is highest from June to September, which means it's more likely to rain in summer.

The probability to have fog through all the monthes:

<img src='images/fog_mo.PNG'>

The probability to have fog is highest from November to Febrary, which means it's more likely to have fog in winter.

Weather analysis in US by sates:

<img src='images/temp_st_h.PNG'>

As we can see from the list above, the top 2 states or areas with the highest average temperatures are US insular areas or freely associated states. And among only the federal states in US, HI (Hawaii) has the highest average temperature (74.81 F).

<img src='images/temp_st_l.PNG'>

From the table shown below, AK (Alaska) has the lowest temperatures among all the federal states in US. The states ND and MN also have very low average temperatures compared to other states.

<img src='images/tornado_st.PNG'>

The top 1 state PR is not in mainland US. So the federal state with the highest tornado frequency is FL (Florida). The states, HI(Hawaii), LA(Louisiana), and MS(Mississippi) also have the relatively high tornado frequency. The result shows that the southeast area in US have the most tornado from the historical data.

## Method Section
Data preparation: We checked the NA and null values for our dataset,replacing them with mode or mean, and dropped the repeated and useless columns. Also, We merged two tables with station number to find out more insights.

We used the linear regression to predict temperature. First, we removed the string type columns and remained all the numeric type columns, then we get the coefficients of the model and the R-square. 
We also used the linear regression to predict total preciptation. 


## Conclusion Section
### Linear Regression For Temperature
In linear regression for temperature, the R-square value is 0.405448, and the RMSE value is 18.473093. The coefficents for the features are shown as below:
<img src='images/temp_coe.PNG'>
The features snow_ice_pellets, stp, and thunder have the relatively significant effects on temperature.

### Linear Regression For Preciptation
From the coefficients, we can find that stp (Mean station pressure for the day in millibars to tenths), fog, rain drizzle, snow ice pellets and hail have relatively significant effects on the total precipitation during a day. This is true since precipitation usually makes of rain or melted snow. So, Whether it rains or snows throughout the day has a crucial impact on the amount of precipitation. Also, fog and hail would also influence the precipitation.

![311593656238_ pic_hd](https://user-images.githubusercontent.com/58396034/86309049-5737cd80-bc4d-11ea-94a7-1c5fea6c2174.jpg)

RMSE measures the differences between predicted values by the model and the actual values. However, RMSE alone is meaningless until we compare with the actual “prcp” value, such as mean, min and max. After such comparison, our RMSE looks  good. However, we must be cautious that the performance on the training set may not a good approximation of the performance on the test set.

![321593656244_ pic](https://user-images.githubusercontent.com/58396034/86309189-b72e7400-bc4d-11ea-9482-7b99ecf4d63d.jpg)

In our test data, the RMSE is similar with that in train data. Our RMSE looks  not bad. 

![341593656255_ pic](https://user-images.githubusercontent.com/58396034/86309241-d200e880-bc4d-11ea-9e64-f02ed45e96a7.jpg)

Now we can use our Linear Regression model to make some predictions

![331593656250_ pic_hd](https://user-images.githubusercontent.com/58396034/86309246-d4fbd900-bc4d-11ea-8299-efec41c201a7.jpg)

## Future Work
For this project, we tried to build models to predict the probability to have fog and tornado. But we haven't found the appropriate machine learning models to apply. So we plan to do more research and try more to create models for prediction. Besides, this dataset has more than 30 features, and we can't have very deep and comprehensive analysis for all of them at this time. Absolutely, there're still information hiden from the data which we could explore more deeply.

## Challenge
It was challenging for us to create the advanced machine learning models for the dataset.

## Labor distribution
Everyone contributes equally.

## Take away from this course
We learned many useful technical tools and skills to analyze big data. These skills are very important for us in many positions. It's really interesting to know about how Hadoop, Map and reduce, and Spark work. We really enjoyed knowing about how these tools work to handle big data. By doing lab, assignments, and project, we got familiar with these big data tools.

