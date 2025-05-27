# Time Series Forecasting with Prophet | Nowa Analytics
A machine learning project for robust time series prediction and interactive web deployment

## Project Overview  
This project implements **Prophet** for time series forecasting, focusing on business-friendly analytics. It includes:  
- **End-to-end modeling**: Data preprocessing, trend/seasonality decomposition, and forecast evaluation.  
- **Performance optimization**: Hyperparameter tuning and cross-validation for robust predictions.  
- **Web deployment**: An interactive Streamlit app for visualizing historical data and forecasts.  
- **Full CI/CD pipeline**: Deployed for stakeholder access.  

Built for **Nowa Analytics** to demonstrate scalable time series solutions for client use cases.  

## Key Features  
### 1. **Time Series Analysis**  
- Decompose trends, seasonality, and holidays using Prophet.  
- Handle missing data and outliers.  

### 2. **Model Evaluation**  
- Metrics: RMSE, MAE, MAPE.  
- Cross-validation with `cross_validation` and `performance_metrics`.  

### 3. **Web Application (Streamlit)**  
- Interactive plots for historical data + forecasts.  
- Adjustable forecast horizons and confidence intervals.  

### 4. **Deployment**  
- Containerized with Docker.  
- Deployed on [Streamlit Cloud](https://streamlit.io/) / [Heroku](https://www.heroku.com/).  


## Repository Structure  
 
├── data/                    # Raw/processed datasets  
├── notebooks/               # EDA and model prototyping (Jupyter)  
├── src/  
│   ├── app.py               # Streamlit application  
│   ├── model.py             # Prophet training/prediction logic  
│   └── utils.py             # Data preprocessing helpers  
├── requirements.txt         # Python dependencies  
└── Dockerfile               # Containerization  


## Results  
![Forecast Visualization](docs/forecast_plot.png) *Example: Retail sales prediction with 95% confidence intervals.*  

**Validation Metrics**:  
| Metric | Value  |  
|--------|--------|  
| RMSE   | 12.4   |  
| MAPE   | 8.2%   |  

## Why Prophet?  
- **Business Interpretability**: Clear trend/seasonality insights.  
- **Scalability**: Automatic handling of missing data and outliers.  
- **Fast Prototyping**: Minimal code for production-ready models.  

## Contact  
**Nowa Analytics**  
- Email: analytics@nowa.ai  
- GitHub: [@nowa-analytics](https://github.com/nowa-analytics)  


### License  
MIT © 2024 Nowa Analytics.  

