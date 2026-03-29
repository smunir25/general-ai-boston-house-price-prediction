# Boston House Price Prediction

A machine learning web application that predicts housing prices using the **Boston Housing Dataset**. Built with a **CatBoost Regressor** model and served via a **Flask** web interface, it helps buyers and sellers estimate property prices based on key housing features.

## Features

- Predicts house prices from 13 input features (crime rate, room count, tax rate, etc.)
- Preprocessing with Standard Scaler for improved model accuracy
- REST API endpoint for programmatic predictions (`/predict_api`)
- Simple web UI for manual input and instant results
- Deployable to Netlify / any cloud platform

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| CatBoost | Gradient boosting regression model |
| Scikit-learn | Data preprocessing (StandardScaler) |
| Flask | Web framework & REST API |
| Pandas / NumPy | Data manipulation |
| Gunicorn | Production WSGI server |

## Project Structure

```
boston-house-price-prediction/
├── app.py                              # Flask application
├── housepred.pkl                       # Trained CatBoost model
├── scaler.pkl                          # Fitted StandardScaler
├── requirements.txt                    # Python dependencies
├── Procfile                            # Deployment process file
├── netlify.toml                        # Netlify deployment config
├── templates/
│   └── home.html                       # Frontend UI
├── Output/                             # Sample output screenshots
└── Boston House Price Prediction.ipynb # Model training notebook
```

## Getting Started

### Prerequisites

- Python 3.7+

### Installation

```bash
git clone https://github.com/smunir25/general-ai-boston-house-price-prediction.git
cd general-ai-boston-house-price-prediction
pip install -r requirements.txt
```

### Run Locally

```bash
python app.py
```

Visit `http://localhost:5000` in your browser.

## API Usage

**POST** `/predict_api`

```json
{
  "data": {
    "CRIM": 0.00632,
    "ZN": 18.0,
    "INDUS": 2.31,
    "CHAS": 0,
    "NOX": 0.538,
    "RM": 6.575,
    "AGE": 65.2,
    "DIS": 4.09,
    "RAD": 1,
    "TAX": 296,
    "PTRATIO": 15.3,
    "B": 396.9,
    "LSTAT": 4.98
  }
}
```

**Response:**

```json
24.0
```

## Model

The CatBoost Regressor was trained on the Boston Housing Dataset with standard scaling applied to all input features. The trained model and scaler are serialized as `.pkl` files for inference.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
