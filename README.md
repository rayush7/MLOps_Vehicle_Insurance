# 🚗 Vehicle Insurance Prediction — End-to-End MLOps Pipeline

An industrial-grade **MLOps project** demonstrating a complete machine learning lifecycle—from data ingestion to model deployment—using **FastAPI**, MongoDB Atlas, AWS, Docker, and GitHub Actions.

## 🔥 Key Highlights

- ⚙️ Modular project template generator
- 🧩 Structured Python package architecture
- 🗄️ MongoDB Atlas as cloud database
- ☁️ AWS (S3, EC2, ECR, IAM) integration
- 🐳 Docker containerization
- 🔁 GitHub Actions CI/CD
- ⚡ FastAPI REST API
- 🚀 End-to-end ML pipeline

## 🏗️ Architecture

```text
MongoDB Atlas
      │
      ▼
Data Ingestion
      ▼
Data Validation
      ▼
Data Transformation
      ▼
Model Training
      ▼
Model Evaluation
      ▼
AWS S3 Model Registry
      ▼
Model Pusher
      ▼
FastAPI Prediction API
```

## 📦 Project Setup

```bash
python template.py

conda create -n vehicle python=3.12 -y
conda activate vehicle
pip install -r requirements.txt
pip list
```

Configure `setup.py` and `pyproject.toml` for local package imports.

## 🗄️ MongoDB Atlas

- Create Atlas project and M0 cluster
- Create DB user
- Allow network access (`0.0.0.0/0`)
- Obtain Python connection string
- Store in environment variable:

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster..."
```

Push the dataset from the notebook and verify it in Atlas.

## 🔄 ML Pipeline

### Data Ingestion
- Read data from MongoDB
- Convert to DataFrame
- Save ingestion artifacts

### Data Validation
- Schema validation
- Data quality checks

### Data Transformation
- Feature engineering
- Encoding & scaling
- Train/test split

### Model Trainer
- Model training
- Artifact generation

### Model Evaluation
- Compare current and previous models
- Register better model

### Model Pusher
- Upload best model to AWS S3

## ☁️ AWS Services

- Amazon S3 — Model Registry
- Amazon EC2 — Deployment
- Amazon ECR — Docker Registry
- IAM — Access Management

Environment variables:

```bash
export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
export AWS_DEFAULT_REGION="us-east-1"
```

## 🐳 Docker

```bash
docker build -t vehicle-app .
docker run -p 5000:5000 vehicle-app
```

## 🔁 CI/CD

- Docker image build
- Push to Amazon ECR
- Self-hosted GitHub Actions runner on EC2
- Automatic deployment

## ⚡ FastAPI API

### Endpoints

| Endpoint | Description |
|-----------|-------------|
| `/` | Home / Health |
| `/training` | Trigger training pipeline |
| `/predict` | Prediction endpoint |

## 📁 Project Structure

```text
src/
 ├── components/
 ├── configuration/
 ├── cloud_storage/
 ├── data_access/
 ├── entity/
 └── pipeline/
notebook/
templates/
static/
Dockerfile
requirements.txt
setup.py
pyproject.toml
```

## 💡 Skills Demonstrated

- MLOps
- FastAPI
- Docker
- AWS
- MongoDB
- GitHub Actions
- CI/CD
- Data Validation
- Feature Engineering
- Model Registry
- Production Deployment

## 🚀 Future Enhancements

- Kubernetes
- MLflow
- Monitoring
- Feature Store

## ⭐ Summary

This project demonstrates a complete production-style MLOps workflow, covering data ingestion, validation, transformation, model training, evaluation, cloud model registry, containerization, CI/CD, and deployment through a high-performance FastAPI service. 