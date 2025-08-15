# Air Passengers Univariate Time Series Analysis

A comprehensive time series analysis project analyzing monthly airline passenger data from 1949-1960 using various forecasting models.

## Project Overview

This project analyzes the classic "AirPassengers" dataset containing monthly totals of international airline passengers from 1949 to 1960. The analysis explores data patterns, builds forecasting models, and compares their performance using various time series techniques.

## Dataset Information

- **Source**: AirPassengers dataset (built-in R dataset)
- **Time Period**: January 1949 to December 1960
- **Frequency**: Monthly data
- **Total Observations**: 144 months
- **Variable**: #Passengers (number of passengers in thousands)

## Project Structure

```
air-passengers-univariate-timeseries-analysis/
├── data/
│   └── AirPassengers.csv          # Raw dataset
├── lab/
│   └── Time_Series.ipynb          # Main analysis notebook
├── requirements.txt               # Python dependencies
├── .gitignore                     # Git ignore file
└── README.md                      # This file
```

## Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd air-passengers-univariate-timeseries-analysis
```

2. Create and activate a virtual environment:
```bash
python -m venv myenv
source myenv/bin/activate  # On Windows: myenv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Analysis Workflow

### 1. Data Exploration
- Load and inspect the dataset
- Visualize passenger trends over time
- Identify patterns and anomalies

### 2. Time Series Decomposition
- Separate trend, seasonal, and residual components
- Analyze seasonal patterns (12-month cycle)
- Examine long-term trends

### 3. Stationarity Testing
- Augmented Dickey-Fuller (ADF) test
- First and second-order differencing
- Transform non-stationary data to stationary

### 4. Model Development
The project implements and compares multiple forecasting models:

#### A. AutoRegressive (AR) Model
- Uses past values to predict future values
- Parameters: lag order selection

#### B. Moving Average (MA) Model
- Uses past forecast errors to predict future values
- Parameters: order of moving average

#### C. ARMA Model
- Combines AR and MA components
- Parameters: (p, d, q) where d=0 for ARMA

#### D. ARIMA Model
- ARMA with differencing for non-stationary data
- Parameters: (p, d, q) with differencing order d

#### E. SARIMA Model
- Seasonal ARIMA for data with seasonal patterns
- Parameters: (p, d, q) × (P, D, Q, s) where s=12 for monthly data

#### F. Prophet Model
- Facebook's forecasting tool
- Handles seasonality and trends automatically

### 5. Model Evaluation
- Backtesting with walk-forward validation
- Performance metrics: MSE, MAE, MAPE
- Forecast visualization and confidence intervals

## Key Findings

1. **Strong Seasonal Pattern**: Clear 12-month seasonal cycle with peaks in summer months
2. **Upward Trend**: Steady growth in passenger numbers over the 12-year period
3. **Model Performance**: SARIMA and Prophet models show best performance for this dataset
4. **Forecasting**: Models successfully predict future passenger numbers with reasonable accuracy

## Usage Instructions

### Running the Analysis

1. **Jupyter Notebook**: Open `lab/Time_Series.ipynb` in Jupyter Lab or VS Code
2. **Run cells sequentially**: The notebook is designed to run from top to bottom
3. **Interactive exploration**: Modify parameters and rerun cells to explore different scenarios

### Key Sections to Explore

- **Data Loading**: Cells 1-3 load and visualize the raw data
- **Decomposition**: Cells 4-6 perform seasonal decomposition
- **Stationarity**: Cells 7-11 test and transform for stationarity
- **Model Building**: Cells 12-26 build and compare different models
- **Forecasting**: Cells 27-40 generate forecasts for future periods

### Customization

- **Change forecast horizon**: Modify `forecast_steps` variable in forecasting sections
- **Try different models**: Adjust model parameters in the backtesting functions
- **Different datasets**: Replace the AirPassengers.csv with your own time series data

## Dependencies

All required packages are listed in `requirements.txt`:
- pandas (data manipulation)
- numpy (numerical operations)
- matplotlib/seaborn (visualization)
- statsmodels (time series analysis)
- scikit-learn (metrics)
- prophet (forecasting)

## Example Output

The analysis produces:
- Time series plots showing trends and seasonality
- Decomposition charts (trend, seasonal, residual)
- ACF/PACF plots for model identification
- Forecast visualizations with confidence intervals
- Model performance comparison tables

## Contributing

Feel free to fork this repository and submit pull requests for improvements. Suggestions for additional models or analysis techniques are welcome.

## License

This project is open source and available under the MIT License.
