# Ozone Concentration Forecasting using Prophet

## Project Overview

This project focuses on time series forecasting to predict ozone (O3) concentration levels. Utilizing the Prophet library, developed by Facebook, the model analyzes historical ozone data to forecast future trends and seasonal patterns. The primary goal is to build a reliable model that can predict O3 concentrations for the upcoming year, providing valuable insights for environmental monitoring and public health advisories.

The project follows a structured data science workflow, including:

  - **Data Loading and Exploration**: Importing and understanding the time series data.
  - **Data Preprocessing**: Cleaning and transforming the data into the format required by Prophet.
  - **Model Training**: Building and training a forecasting model using historical data.
  - **Hyperparameter Tuning**: Optimizing the model's parameters using `GridSearchCV` to improve its predictive accuracy.
  - **Forecasting**: Generating future predictions with uncertainty intervals.
  - **Model Evaluation**: Assessing the model's performance using standard regression metrics.
  - **Visualization**: Plotting the forecast, trends, and seasonal components to interpret the results.

The target of this forecasting task is the daily ozone concentration, `O3`.


## Dataset Description

The dataset used in this project is a time series of daily ozone concentration levels. It contains two primary columns:

| Column Name | Description | Data Type |
|-------------|--------------------------------------------|-------------|
| `Date` | The date of the observation. | Datetime |
| `O3` | The measured concentration of ozone on that day. | Numerical |

For the Prophet model to work, the columns were renamed to `ds` (datestamp) and `y` (numeric value to be predicted), respectively.


## Project Pipeline

The project is structured into the following key stages:

### 1\. Data Preparation

  - The historical ozone data (`Ozone_Level.csv`) is loaded into a pandas DataFrame.
  - The `Date` column is converted to a datetime object to enable time series analysis.
  - The columns are renamed to `ds` and `y` to meet Prophet's input requirements.

### 2\. Model Training (Initial)

  - An initial Prophet model is instantiated and trained on the entire historical dataset.
  - A future DataFrame is created to hold predictions for the next 365 days.
  - The model generates a forecast, which includes the predicted value (`yhat`), along with lower and upper uncertainty bounds (`yhat_lower`, `yhat_upper`).
  - The initial forecast and its components (trend, weekly, and yearly seasonality) are visualized.

### 3\. Hyperparameter Tuning with GridSearchCV

To enhance the model's performance, a systematic search for the best hyperparameters was conducted using Scikit-learn's `GridSearchCV`. This is a more robust approach than manual tuning.

  - **Cross-Validation Setup**: A `KFold` cross-validation strategy with 3 splits was defined to ensure that the model's performance is stable across different subsets of the data.
  - **Hyperparameter Grid**: The following parameters were tuned:
      - `changepoint_prior_scale`: Controls the flexibility of the trend. Values searched: `[0.01, 0.1, 0.5]`.
      - `seasonality_prior_scale`: Controls the flexibility of the seasonality components. Values searched: `[0.1, 1.0, 10.0]`.
      - `seasonality_mode`: Defines whether seasonalities are additive or multiplicative. Values searched: `['additive', 'multiplicative']`.
  - **Training and Selection**: The `GridSearchCV` object was trained on the data, and it automatically identified the best combination of parameters based on the negative mean squared error scoring metric.

### 4\. Final Model Training and Forecasting

  - A new Prophet model was instantiated using the best hyperparameters found during the grid search.
  - This optimized model was trained on the entire dataset.
  - A final, more accurate forecast for the next 365 days was generated.

### 5\. Model Evaluation

The performance of the optimized model was rigorously evaluated using cross-validation.

  - **Metrics**: Standard regression metrics were used to assess accuracy:
      - **R² (R-squared)**: Indicates the proportion of the variance in the dependent variable that is predictable from the independent variable(s).
      - **Mean Absolute Error (MAE)**: Measures the average magnitude of the errors in a set of predictions, without considering their direction.
      - **Mean Squared Error (RMSE)**: Is the square root of the average of squared differences between prediction and actual observation.
  - The `cross_validate` function from Scikit-learn was used to compute these metrics over the 3-fold cross-validation, providing a reliable assessment of the model's generalization performance.

### 6\. Visualization of Results

  - The final forecast from the optimized model was plotted, showing the historical data, the predicted values, and the confidence interval.
  - The individual components of the forecast—trend, weekly seasonality, and yearly seasonality—were also plotted to provide deeper insights into the patterns learned by the model.


## Technologies and Libraries Used

  - **Programming Language**: Python 3
  - **Core Libraries**:
      - **Pandas**: Used for data loading, manipulation, and preprocessing. Essential for handling the time series data.
      - **Prophet (by Facebook)**: The core library for time series forecasting. It is robust to missing data and shifts in the trend and handles seasonality well.
      - **Scikit-learn**: A fundamental machine learning library used for:
          - `GridSearchCV`: For automated and exhaustive hyperparameter tuning.
          - `KFold` & `cross_validate`: For setting up and executing a robust cross-validation strategy.
          - `r2_score`, `mean_absolute_error`, `mean_squared_error`: For calculating model performance metrics.
      - **Matplotlib & Seaborn**: Used for creating high-quality visualizations of the forecast and its components.
  - **Tools**:
      - **Jupyter Notebook**: The interactive development environment used for writing code, visualizing data, and documenting the entire analysis process.


## How to Run the Project

1.  **Clone the Repository:**

    ```sh
    git clone [URL_OF_YOUR_REPOSITORY]
    ```

2.  **Install Dependencies:**
    It is highly recommended to use a virtual environment to manage dependencies.

    ```sh
    pip install pandas prophet scikit-learn matplotlib seaborn
    ```

3.  **Place the Dataset:**
    Ensure that the `Ozone_Level.csv` file is located in the same directory as the Jupyter Notebook.

4.  **Execute the Notebook:**
    Open and run the `Model_O3_prophet.ipynb` notebook in a Jupyter environment to execute the complete pipeline, from data loading to final forecasting and evaluation.

## Final Output

The primary output of this project is a forecast of ozone concentration for the next 365 days, complete with uncertainty intervals. The notebook also produces visualizations of this forecast and its underlying components, as well as a quantitative evaluation of the final model's accuracy.
