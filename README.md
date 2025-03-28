📌 Project Overview
This project predicts water potability using a machine learning model. The pipeline integrates FastAPI for serving predictions, DVC for data versioning, Apache Airflow for workflow automation, and Apache Spark for scalable data processing.

⚡ Features
✅ FastAPI Backend - Real-time prediction API
✅ DVC Integration - Version control for data & models
✅ Apache Airflow - Automates data ingestion & ML pipeline
✅ Apache Spark - Scalable data processing & feature engineering

 🚀 Installation & Setup
1️⃣ Clone the Repository

git clone https://github.com/yourusername/water-potability-prediction.git
cd water-potability-prediction

2️⃣ Create a Virtual Environment & Install Dependencies

python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate     # On Windows
pip install -r requirements.txt

3️⃣ Set Up DVC & Retrieve Data
Ensure DVC is installed:

pip install dvc


Then, pull the dataset and model:

dvc pull


4️⃣ Start Apache Airflow (Optional, for Workflow Automation)
Initialize Airflow:

airflow db init
airflow scheduler &
airflow webserver -p 8082 &
Access Airflow UI at 👉 http://localhost:8082

5️⃣ Run the FastAPI Server

uvicorn src.main:app --reload


API available at 👉 http://127.0.0.1:8000

