# 🚀 End-to-End MLOps Project: Vehicle Price Prediction

Welcome to the **Vehicle Price Prediction** MLOps project! This repository demonstrates a complete machine learning lifecycle from data ingestion to CI/CD deployment on AWS.

---

## 📁 Project Structure

```
├── src/
│   ├── components/             # Data ingestion, transformation, validation, model trainer
│   ├── configuration/          # MongoDB & AWS connection setup
│   ├── data_access/            # Scripts to interact with MongoDB
│   ├── entity/                 # Config & artifact data classes
│   ├── aws_storage/            # AWS S3 integration
│   └── utils/                  # Utility functions (logger, exception, etc.)
├── notebook/                   # EDA and MongoDB upload notebooks
├── templates/                  # Flask app templates
├── static/                     # Static files (CSS/JS)
├── .github/workflows/          # GitHub Actions CI/CD pipeline
├── Dockerfile                  # Docker container setup
├── requirements.txt            # Required Python packages
├── setup.py / pyproject.toml   # Local package setup
└── app.py                      # Flask app entry point
```

---

## 🛠️ Getting Started

### ✅ Project Setup

1. Generate project template:

   ```bash
   python template.py
   ```

2. Install packages:

   ```bash
   conda create -n vehicle python=3.10 -y
   conda activate vehicle
   pip install -r requirements.txt
   pip list  # Confirm local packages are installed
   ```

3. Setup module import support via `setup.py` and `pyproject.toml`

4. Refer to `crashcourse.txt` for setup guidance

---

## 🗄️ MongoDB Setup (MongoDB Atlas)

1. Create a free cluster
2. Configure DB user credentials and network access (`0.0.0.0/0`)
3. Copy the Python connection string from MongoDB Atlas
4. Load your dataset via `mongoDB_demo.ipynb`
5. Verify data via MongoDB Atlas > Database > Browse Collections

---

## 📋 Logging, Exception Handling & Notebooks

* Custom logging via `logger.py`
* Exception tracking via `exception.py`
* EDA and feature engineering notebooks added

---

## 🔄 Data Ingestion Module

1. Define constants in `constants/__init__.py`
2. Set up MongoDB connection in `configuration/mongo_db_connection.py`
3. Fetch and convert MongoDB data to DataFrame in `data_access/proj1_data.py`
4. Define config and artifact classes in `entity/config_entity.py` and `entity/artifact_entity.py`
5. Implement core logic in `components/data_ingestion.py`
6. Configure MongoDB URI in terminal (bash or PowerShell)
7. Run `demo.py` to test ingestion

---

## ✅ Data Validation, Transformation, and Model Training

* Define schema in `config/schema.yaml`
* Utility methods in `utils/main_utils.py`
* Develop components for:

  * Data Validation
  * Data Transformation (with `estimator.py`)
  * Model Trainer (also updates `estimator.py`)

---

## ☁️ AWS Setup (for Model Evaluation & Deployment)

* Create IAM user with `AdministratorAccess`
* Store Access & Secret keys securely
* Set environment variables via terminal or system settings
* Define S3 config in `constants/__init__.py`
* Connect to S3 via `configuration/aws_connection.py`
* Create S3 bucket (e.g., `my-model-mlopsproj`)
* Add logic to `aws_storage/` and `entity/s3_estimator.py` for push/pull

---

## 📈 Model Evaluation & Model Pusher

* Evaluate model improvements using defined threshold
* Push new models to S3 bucket registry

---

## 🔮 Prediction Pipeline

* Create `PredictionPipeline` class
* Build a Flask web app (`app.py`) with `templates/` and `static/`
* Launch locally or via Docker/EC2

---

## 🔁 CI/CD with GitHub Actions + Docker + AWS

* Configure `Dockerfile` and `.dockerignore`
* Create GitHub Action workflows in `.github/workflows/aws.yaml`
* Create and connect a self-hosted runner on AWS EC2
* Set secrets in GitHub:

  * `AWS_ACCESS_KEY_ID`
  * `AWS_SECRET_ACCESS_KEY`
  * `AWS_DEFAULT_REGION`
  * `ECR_REPO`
* Setup AWS ECR & EC2
* Deploy app on port `5080` via public IP

---

## 🧪 Accessing the App

* Launch the web app: `http://<EC2-PUBLIC-IP>:5080`
* Trigger training via `http://<EC2-PUBLIC-IP>:5080/training`

---

## ✅ Key Features

* End-to-end ML pipeline with modular components
* MongoDB for flexible data storage
* AWS S3 for model versioning
* GitHub Actions CI/CD with Docker + EC2
* Web-based prediction interface

---

## 👨‍💻 Tech Stack

* **Python**, **Flask**, **MongoDB**, **Docker**, **AWS (S3, EC2, IAM, ECR)**
* **GitHub Actions**, **Pandas**, **Scikit-learn**, **PyYAML**, **Logging**

---

## 🙌 Contributors

* **Manish Chauhan**
  [Email](mailto:manish.chauhan.we@gmail.com) | [LinkedIn](https://linkedin.com/in/yourprofile)

---


