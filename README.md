# 🌊🚰 Water Potability Prediction API with DVC pipeline

## 📌 Project Overview
This project provides a **machine learning-powered API** for predicting water potability based on chemical properties. It integrates multiple technologies to ensure efficient data processing, model versioning, and automated workflow execution:

- **FastAPI** → Serves real-time predictions
- **DVC (Data Version Control)** → Manages datasets and ML models
- **Apache Airflow** → Automates data ingestion, transformation, and ML pipeline execution

## ⚡ Features
- ✅ **FastAPI Backend** - Provides a high-performance REST API for predictions
- ✅ **DVC Integration** - Ensures reproducibility and version control for data & models
- ✅ **Apache Airflow** - Automates workflow execution, including model retraining and data updates
- ✅ **Docker-Ready** - Easily containerized for cloud deployments

## 🚀 Installation & Setup
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/water-potability-prediction.git
cd water-potability-prediction
```

### 2️⃣ Create a Virtual Environment & Install Dependencies
```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate    # On Windows
pip install -r requirements.txt
```

### 3️⃣ Set Up DVC & Retrieve Data
Ensure DVC is installed:
```bash
pip install dvc
```
Then, pull the dataset and pre-trained model:
```bash
dvc pull
```

### 4️⃣ Start Apache Airflow (Optional, for Workflow Automation)
Initialize Airflow:
```bash
airflow db init
airflow scheduler & airflow webserver -p 8082 &
```
Access the Airflow UI at 👉 [http://localhost:8082](http://localhost:8082)

### 5️⃣ Run the FastAPI Server
```bash
uvicorn src.main:app --host 0.0.0.0 --port 8000 --reload
```
API available at 👉 [http://127.0.0.1:8000](http://127.0.0.1:8000)

## 🏗️ API Usage
### 1️⃣ Home Route  
**GET /**  
Returns a welcome message.

### 2️⃣ Prediction Route  
**POST /predict**  

#### Request Body (JSON):
```json
{
  "ph": 7.1,
  "Hardness": 120.5,
  "Solids": 21000.0,
  "Chloramines": 7.5,
  "Sulfate": 350.2,
  "Conductivity": 400.0,
  "Organic_carbon": 10.2,
  "Trihalomethanes": 70.5,
  "Turbidity": 4.5
}
```

#### Response:
- **"Water is Consumable"** → If the water is safe for drinking
- **"Water is not Consumable"** → If the water is unsafe

## 📡 Deployment
### 🛠️ Deploy on Render
1. Push your project to GitHub
2. Connect the repository to [Render](https://render.com/)
3. Set up a FastAPI service and define the start command:
   ```bash
   uvicorn src.main:app --host 0.0.0.0 --port 8000
   ```
4. Deploy and access your API via the Render-generated URL

### 🐳 Docker Deployment
1. Build the Docker image:
   ```bash
   docker build -t water-potability-api .
   ```
2. Run the container:
   ```bash
   docker run -p 8000:8000 water-potability-api
   ```
3. Access the API at [http://localhost:8000](http://localhost:8000)

## 🐟 License
MIT License

