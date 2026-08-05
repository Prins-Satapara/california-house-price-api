# 🏠 California House Price Prediction API

A FastAPI-based Machine Learning application for predicting California house prices using a trained Random Forest model. The API provides both single predictions and bulk predictions through CSV file uploads.

---

## 🚀 Features

* Predict house prices using a trained Machine Learning model
* Upload a CSV file for batch predictions
* Automatic validation using Pydantic
* Health check endpoint
* Interactive Swagger UI documentation
* CSV download with predicted prices
* Clean REST API architecture

---

# 🛠 Tech Stack

### Backend

* FastAPI
* Uvicorn

### Machine Learning

* Scikit-learn
* Random Forest Regressor
* Joblib

### Data Processing

* Pandas
* NumPy

---

# 📁 Project Structure

```
California-House-Price-API/
│
├── main.py
├── train.py
├── explore.py
├── test_housing.csv
├── requirements.txt
├── README.md
├── .gitignore
├── screenshots/
│   ├── swagger-home.png
│   ├── health-endpoint.png
│   ├── predict-endpoint.png
│   ├── predict-response.png
│   ├── upload-endpoint.png
│   └── csv-download.png
│
├── house_model.joblib        (generated after training)
└── house_features.joblib     (generated after training)
```

---

# 📊 Dataset

California Housing Dataset from Scikit-learn.

Features used:

* MedInc
* HouseAge
* AveRooms
* AveBedrms
* Population
* AveOccup
* Latitude
* Longitude

Target:

* Median House Price

---

# ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/california-house-price-api.git
cd california-house-price-api
```

Create virtual environment

```bash
python -m venv venv
```

Activate environment

Windows

```bash
venv\Scripts\activate
```

Linux / Mac

```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 🧠 Train the Model

```bash
python train.py
```

This generates:

* house_model.joblib
* house_features.joblib

---

# ▶️ Run the API

```bash
uvicorn main:app --reload
```

Open

```
http://127.0.0.1:8000/docs
```

---

# 📡 API Endpoints

## Home

```
GET /
```

Returns API information.

---

## Health Check

```
GET /health
```

Returns model status and metadata.

---

## Predict Single House

```
POST /predict
```

Input JSON

```json
{
  "MedInc": 8.32,
  "HouseAge": 41,
  "AveRooms": 6.98,
  "AveBedrms": 1.02,
  "Population": 322,
  "AveOccup": 2.55,
  "Latitude": 37.88,
  "Longitude": -122.23
}
```

Sample Response

```json
{
  "predicted_price": "$452,000",
  "predicted_price_short": "$4.52 hundred thousands",
  "confidence_range": "$413,000 to $491,000"
}
```

---

## Batch Prediction

```
POST /predict-file
```

Upload a CSV file containing housing features.

Returns a CSV file with predicted house prices.

---

# 📷 Screenshots

See the `screenshots/` folder for API examples.

---

# 🔮 Future Improvements

* Docker support
* Model versioning
* Authentication
* Cloud deployment (Render / Railway / Azure)
* CI/CD using GitHub Actions
* Unit testing
* Logging
* API monitoring