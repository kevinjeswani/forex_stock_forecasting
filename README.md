# Foreign Exchange Rate (& Stock Price) Forecasting
Forecasting foreign exchange rates and stock prices with classical, boosted tree regressors, and deep learning methods. (Machine Learning Capstone)

## Summary
-	Locally-warehoused 11gb of financial API stock/ ForEx data in SQLite, using Dask for parallelizing API calls. Initially used H5Tables for smaller forex dataset.
-	Developed additional normalized financial technical indicators to create exogenous variable time-series
-	Studied classical forecasting techniques (ARIMA, VARMAX) to determine ForEx trend and seasonality dependence
-	Performed a grid-search cross-validation hyperparamter tuning of XGBoost, RandomForest, CatBoost, & LGBoost time-series regressors (SkForecast) and built a LSTM-RNN (Keras) regressor, incorporating exogenous variables

## Workflow
The set of scripts in the folder 'FOREX_Forecasting_Scripts' are segmented for the purpose of clarity & convenience <br>
The following is the suggested order for running the scripts:
- '1_KJ_Forex_TS_Forecasting_DataGathering_Processing.ipynb' - Gathering data from the EODHD API, inspecting, cleaning, merging the forex data
- '2_KJ_Forex_TS_Forecasting_EDA_VARMAX_Prophet.ipynb' - Exploratory data analysis (correlation), classical time series analysis (ACF/PACF) + VARMAX, Facebook Prophet
- '3_KJ_Forex_TS_Forecasting_SkForecast.ipynb' - Boosted tree  (XGB, LGBM, CatBoost, RandomForest ensemble) time series regression models, with backtesting/timeseries cross validation.
- '4_KJ_Forex_TS_Forecasting_LSTM.ipynb' - LSTM (RNNs) models.
- 'AppA_KJ_SQLite_Warehousing.ipynb' - Using EODHD API to gather stocks, options, forex, indicators, fundamental data to develop SQLITE databases

## Data is gathered from:
- The EOD Historical Data API: https://eodhistoricaldata.com/
- Unofficial Python SDK for EODHD: https://github.com/LautaroParada/eod-data
- OECD.Stats
