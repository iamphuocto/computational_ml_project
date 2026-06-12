# Exchange Rate Predictor

A comprehensive machine learning web application for exchange rate prediction. This project demonstrates ML concepts, including data fetching, model training, prediction, and evaluation.

## 🎯 Project Overview

This starting project includes:

- **Exchange Rate Prediction**: Simple averaging model 
- **Web Interface**: Flask-based web application with user authentication
- **Data Management**: Automated data fetching and management system
- **Visualization**: Interactive charts showing historical rates and predictions
- **Model Evaluation**: RMSE calculation for prediction accuracy assessment
- **Logging System**: Comprehensive prediction logging and monitoring

## 🏗️ Architecture

### Core Components

1. **ExchangeRatePredictor**: Machine learning model class with train/predict methods
2. **ExchangeRateDataFetcher**: Data acquisition and management system
3. **Flask Web App**: User interface with authentication and controls
4. **Visualization Engine**: Plotly-based interactive charts

### Model Details

- **Algorithm**: Simple Moving Average (10-day window)
- **Purpose**: Educational demonstration of ML workflow
- **Data Source**: Yahoo Finance (30+ major currency pairs)
- **Historical Data**: Real historical exchange rate data going back years

## 🚀 Quick Start

### Prerequisites

- Python 3.10 (conda environment recommended)
- Internet connection for Yahoo Finance data

### One-Command Setup and Run

```bash
# Setup and run everything
conda activate py310 && pip install -r requirements.txt && python app.py
```

### Test Yahoo Finance Integration

```bash
# Test if everything is working
python test_api.py
```

### Step-by-Step Setup

1. **Environment Setup**:
   ```bash
   conda activate py310  # Use existing py310 environment
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run Application**:
   ```bash
   python app.py
   ```

4. **Access Web Interface**:
   - Open http://localhost:5000
   - Use demo credentials displayed on the homepage

## 📊 Usage Guide

### Demo Credentials

The application displays demo credentials on the homepage:
- **phuoc** / phuoc
- **demo** / password123  
- **admin** / phuoc_admin

### Basic Workflow

1. **Login** using demo credentials
2. **Fetch Data**: Click "Fetch Latest Data" to download exchange rate data
3. **Select Currency Pair**: Choose any two currencies (e.g., USD → EUR)
4. **Set Prediction Parameters**:
   - Prediction date (past dates show RMSE evaluation)
   - Number of days ahead (1-30)
5. **Make Prediction**: View results and charts
6. **Evaluate Model**: See RMSE scores for historical predictions

### Available Currency Pairs

The system supports 30+ major currency pairs, including:
- **Major**: USD/EUR, USD/GBP, USD/JPY, USD/CAD, USD/AUD, USD/CHF
- **Cross**: EUR/GBP, EUR/JPY, GBP/JPY, CHF/JPY
- **Asian**: USD/CNY, USD/INR, USD/KRW, USD/SGD, USD/THB, USD/VND
- **Others**: USD/BRL, USD/MXN, USD/ZAR, USD/RUB

## 🔧 Technical Details

### File Structure

```
ml_project/
├── app.py                 # Flask web application
├── predictor.py          # ML model implementation
├── data_fetcher.py       # Data acquisition system
├── requirements.txt      # Python dependencies
├── templates/           # HTML templates
│   ├── base.html
│   ├── index.html
│   └── dashboard.html
├── static/             # CSS/JS assets (auto-created)
├── data/              # Exchange rate data (auto-created)
├── logs/              # Prediction logs (auto-created)
└── models/            # Trained models (auto-created)
```

### Data Integration

- **Service**: Yahoo Finance
- **Cost**: Completely free
- **Features**: Real historical exchange rate data, 30+ currency pairs
- **Data Range**: Historical data going back years (2000+)
- **Benefits**: Reliable, authentic financial data perfect for ML learning

### Machine Learning Model

**Algorithm**: Simple Moving Average
```python
def predict(self, currency_pair, prediction_date, days_ahead):
    # Use the average of the last 10 exchange rates
    predicted_rate = np.mean(last_10_rates)
    return predictions
```

**Evaluation Metrics**:
- RMSE (Root Mean Square Error)
- MAE (Mean Absolute Error)

## 🧪 Educational Features

### Learning Objectives

1. **Data Pipeline**: Understand data fetching, cleaning, and storage
2. **Model Training**: Learn basic ML model structure and training
3. **Prediction**: Implement prediction logic and evaluation
4. **Web Development**: Build user interfaces for ML applications
5. **Evaluation**: Calculate and interpret model performance metrics

### Extension Ideas for Students

1. **Advanced Models**: Implement LSTM, ARIMA, or Prophet models
2. **Feature Engineering**: Add technical indicators, moving averages
3. **Real-time Updates**: Implement live data streaming
4. **Multiple Models**: Compare different prediction algorithms
5. **Risk Analysis**: Add volatility and confidence intervals

## 🔧 Development

### Running Tests

```bash
conda activate py310
pytest
```

### Development Mode

```bash
# Enable Flask debug mode
export FLASK_ENV=development
python app.py
```

### Adding New Features

1. **New Models**: Extend `ExchangeRatePredictor` class
2. **Additional Data**: Modify `ExchangeRateDataFetcher`
3. **UI Changes**: Update templates in `templates/`
4. **API Endpoints**: Add routes in `app.py`

## 📈 Model Performance

### Current Model (Simple Average)

- **Type**: Baseline model for educational purposes
- **Accuracy**: Limited (intended as starting point)
- **Training Time**: < 1 second
- **Prediction Time**: < 0.1 seconds

### Expected Results

- **RMSE**: Varies by currency pair (typically 0.01-0.1)
- **Trend**: May not capture market trends effectively
- **Use Case**: Demonstrates ML workflow concepts

## 🛠️ Troubleshooting

### Common Issues

1. **"No data available for USD_to_EUR" Error**:
   - Run `python test_api.py` to diagnose the issue
   - Click the "Fetch Latest Data" button in the web interface first
   - Check the internet connection to Yahoo Finance

2. **Yahoo Finance Connection Issues**:
   - Ensure a stable internet connection
   - Yahoo Finance may have temporary outages
   - Try running the test script to verify connectivity

3. **Missing Dependencies**: Run `pip install -r requirements.txt`

4. **Port Conflicts**: Change port in `app.py` if needed

5. **Data Fetching Fails**: 
   - Check internet connection to Yahoo Finance
   - Verify yfinance library is installed correctly

### Logs Location

- **Application Logs**: Console output
- **Prediction Logs**: `logs/predictions.log`
- **Data Files**: `data/exchange_rates.csv`
