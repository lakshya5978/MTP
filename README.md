# Ganges River Water-Level Forecasting

A time-series forecasting project built around historical Ganges river water-level data. The repository contains data preparation, stationarity diagnostics, ARIMA/ARMA modeling, Holt-Winters exponential smoothing, daily and monthly forecasting experiments, and the accompanying project report.

## Project objective

The project studies whether classical time-series methods can model and forecast river water levels using historical observations.

The analysis covers:

1. data cleaning and interpolation of missing observations;
2. exploratory time-series analysis and seasonal decomposition;
3. stationarity testing with the Augmented Dickey-Fuller test;
4. ACF/PACF and automated order selection for ARIMA-family models;
5. train/test forecasting and error evaluation;
6. Holt-Winters exponential smoothing as an alternative seasonal model;
7. daily and monthly versions of the forecasting problem.

## Methods

### ARIMA / ARMA

The notebooks use `statsmodels` and `pmdarima` to:

- test stationarity;
- inspect autocorrelation and partial autocorrelation;
- select candidate model orders;
- fit ARIMA/ARMA models;
- generate out-of-sample predictions;
- evaluate forecast error;
- refit models on the full history for forward forecasts.

Examples implemented in the repository include a daily **ARIMA(5,1,3)** specification and a monthly **ARMA(3,2)** specification.

### Holt-Winters

A separate notebook applies Holt-Winters exponential smoothing with additive trend and additive seasonality, using a 365-day seasonal period for the daily series.

### Data preparation

The raw water-level series is supplemented by an interpolated dataset. Missing observations are filled using linear interpolation before selected modeling exercises.

## Repository structure

- [Ganges_river_water_level_all.csv](./Ganges_river_water_level_all.csv)  
  Historical water-level data used in the project.

- [Interpolated_Data.csv](./Interpolated_Data.csv)  
  Preprocessed/interpolated version of the series used by the forecasting notebooks.

- [MTP Code (ARIMA).ipynb](./MTP%20Code%20%28ARIMA%29.ipynb)  
  Daily-frequency ARIMA workflow including ADF testing, model selection, train/test forecasts and forecast-error evaluation.

- [MTP Code (HW).ipynb](./MTP%20Code%20%28HW%29.ipynb)  
  Data preprocessing, seasonal decomposition and Holt-Winters forecasting.

- [MTP Monthly.ipynb](./MTP%20Monthly.ipynb)  
  Monthly-frequency ARMA/ARIMA analysis, including stationarity diagnostics and out-of-sample forecasting.

- [MTP Report.pdf](./MTP%20Report.pdf)  
  Full written project report.

## Example diagnostics in the notebooks

The repository includes:

- Augmented Dickey-Fuller stationarity tests;
- ACF/PACF analysis;
- AIC/BIC-based model summaries;
- train/test forecast plots;
- mean squared error and RMSE evaluation;
- additive seasonal decomposition;
- daily and monthly forecast comparisons.

Because the notebooks explore multiple frequencies and model specifications, error values should be interpreted within the corresponding experiment rather than compared directly across all notebooks.

## Technology

Core tools used in the repository include:

`Python`, `pandas`, `numpy`, `matplotlib`, `statsmodels`, `pmdarima` and `scikit-learn`.

## Running the project

The notebooks are exploratory and can be opened independently, but they expect the CSV files in the repository root.

A practical sequence is:

1. review the raw and interpolated datasets;
2. run `MTP Code (HW).ipynb` for preprocessing and seasonal modeling;
3. run `MTP Code (ARIMA).ipynb` for daily ARIMA analysis;
4. run `MTP Monthly.ipynb` for the monthly-frequency experiment;
5. refer to `MTP Report.pdf` for the full project write-up.

## Notes and limitations

- The repository reflects an academic forecasting project rather than a production forecasting system.
- Different notebooks use different frequencies and model specifications, so reported errors are not directly comparable unless the same sample and forecast horizon are used.
- Linear interpolation is used in selected preprocessing steps and can affect subsequent model estimates.
- Classical time-series assumptions should be reassessed before applying the models to new periods or operational decisions.

## Author

**Lakshya Sharma**
