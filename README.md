# ClimformaticsInc.
Climformatics work Fall 2023 through Spring 2024
Climformatics Inc: Building proactive
climate-smart technologies to prevent heat-
related human health hazard and mortality

Mentors: Dr. Detelina Ivanova, Dr. Subarna Bhattacharyya, Divyam Goel | Students: Anvita Korrapati, Matthew Haynam, Fariha Babar,
Nithurhan Carthikeyan
Data Science Discovery Program - Climformatics, Inc.; University of California, Berkeley Data Discovery Program

Introduction
Our team used California data to 1) determine what classifies as a
heat wave by region (according to temperature), 2) predict
hospitalization rates during heat waves, to then 3) forecast
temperatures over an extended period of times to assess future
heat-wave related hospital rates during heat waves, and finally 4)
forecast temperatures over an extended period of times to assess
future heat wave events.

Data
1) To determine what makes an event a heat wave, 6-hourly and hourly
data for each county retrieved from publicly available data sets from
NASA and NOAA was used.

2) For heat stress hospitalization forecasting, the CDC’s Environmental
Health Public Tracking Program was used for weekly temperature and
heat-related hospitalization data from 2018 to 2023 over California,
Arizona, Hawaii, and Nevada.

3) For temperature forecasting, dat was obtained from NASA POWER
of temperature at 2 meters, wet bulb temperature at 2 meters, relative
humidity at 2 meters, and precipitation recorded hourly at each location
(data normalized before use).

Methods
1) In order to determine what a heat wave event is by
region, regional temperature data was collected and cleaned
with manual thresholds set. The thresholds were set
according to the California Department of Public Health’s
definition of a heatwave which is two or more consecutive
heat events. Thus, here a heat event is defined as when the
temperature is at or above the 95th percentile of daily
temperatures for that region (Figure 3).

2) For hospitalization forecasts, an LSTM model was used
on the timestamped weekly temperature and emergency
room admission count in order to predict hospitalizations
due to heat stress.

3) For the temperature forecasting, a LSTM model was
decided on as the temperature data for all the counties is

time-stamped. Through feature engineering hyper-
parameter tuning (adding a previous hour index as a

feature, decreased batch size, increased learning rate,
decreased time interval for prediction), an hourly model
forecast per location with high accuracy was found.

4) In order to forecasts temperatures over the next 9 months
and create a time series, a ridge regression was used on the
NSA Power and CIMIS data as the features are highly
correlated (all are related to temperature).

Results
1) In classifying heat waves using temperature thresholds, we
created a tool to help identify future heat waves by region
(Figure 4).

2) The predicted number of hospitalization per temperature
over the region was fairly accurate (Figure 1). Furthermore, the
forecasted number of hospitalizations due to heat stress
reasonably fluctuates over time, which is fitting given the warm
climate that spikes in the Southwest (Figure 2).

3) Prediction accuracy goes down with more variable weather
patterns, this can be remedied through more data, longer time
periods analyzed by the LSTM, and better feature engineering.
Although for purposes of this project the accuracy of the model
is satisfactory but could be increased in the future.
The accuracy of the model and the naive is presented as the
difference between predicted and actual for each hour. In
Figure 5, the red is when a value exceeds 1 which means that
the predicted is over 1 degree celsius above or below the actual
wet bulb temperature. The graphs of naive and the model are
similar in distribution of red and blue despite less red
(inaccurate predictions) in the model graph (Figure 5).

4) Temperature and future temperature have a positive
correlation, as expected (Figure 6). The 9 month time-series
forecast of data is fairly accurate in terms of temperature, as
opposed to the relative humidity (RH) forecast which varies
more (Figure 7). Using our own metrics of temperature
prediction from ridge regression models, we also got very
accurate results.
