# Ozone (O3) Concentration Forecasting with Prophet

## Project Overview

This project analyzes and forecasts daily ozone (O3) concentration levels using Facebook's Prophet time series forecasting model. The dataset contains daily air quality measurements from March 2020 to February 2024, including various pollutants and temperature readings.

## Key Features

- **Time Series Analysis**: Visual exploration of O3 concentration trends over 4 years
- **Seasonal Patterns**: Monthly aggregation to identify seasonal variations
- **Forecasting**: Predictions for future O3 levels using Prophet
- **Interactive Visualizations**: Plotly charts for exploratory data analysis

## Data Description

The dataset contains 1,460 daily records with the following variables:
- `Data`: Date of measurement (YYYY-MM-DD)
- `PM2.5`: Particulate Matter 2.5 microns
- `PM10`: Particulate Matter 10 microns
- `SO2`: Sulfur Dioxide
- `NO2`: Nitrogen Dioxide
- `CO`: Carbon Monoxide
- `O3`: Ozone (target variable)
- `TEMP`: Temperature

## Analysis Highlights

1. **Time Series Visualization**:
   - Line chart showing daily O3 fluctuations
   - Clear seasonal patterns visible in the data

2. **Monthly Aggregation**:
   - Bar chart displaying average O3 levels by month
   - Highest concentrations typically occur in summer months

3. **Prophet Forecasting**:
   - Trained on 4 years of daily data
   - 365-day future forecast generated
   - Uncertainty intervals included in predictions

## How to Use

1. Clone the repository
2. Install dependencies: `pandas`, `prophet`, `plotly`, `numpy`
3. Run the Jupyter notebook to:
   - Explore the data visualizations
   - Train the forecasting model
   - Generate future predictions

## Future Enhancements

- Incorporate additional weather variables to improve accuracy
- Add multivariate analysis of pollutant relationships
- Implement anomaly detection for extreme O3 events
- Create a dashboard for real-time monitoring

## GitHub Analytics

This project demonstrates:
- Time series data preprocessing
- Seasonal decomposition techniques
- Prophet model configuration and interpretation
- Interactive data visualization best practices

The notebook includes clear markdown sections and comments to guide users through each analytical step.  

## Contact  
**Nowa Analytics**  
- Email: analytics@nowa.ai  
- GitHub: [@nowa-analytics](https://github.com/nowa-analytics)  


### License  
MIT © 2024 Nowa Analytics.  

