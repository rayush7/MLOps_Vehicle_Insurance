````markdown
# 🚗 End-to-End MLOps Vehicle Project

> A production-ready **End-to-End MLOps pipeline** that demonstrates how to build, validate, train, evaluate, version, deploy, and serve a Machine Learning model using **MongoDB Atlas, FastAPI, Docker, AWS, and GitHub Actions**.

<p align="center">

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-API-009688?style=for-the-badge&logo=fastapi)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?style=for-the-badge&logo=mongodb)
![AWS](https://img.shields.io/badge/AWS-S3%20%7C%20EC2%20%7C%20ECR-orange?style=for-the-badge&logo=amazonaws)
![Docker](https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker)
![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-black?style=for-the-badge&logo=githubactions)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikitlearn)

</p>

---

# 📌 Overview

This repository demonstrates a complete **Machine Learning Operations (MLOps)** workflow following production-oriented software engineering practices.

Starting from storing data in **MongoDB Atlas**, the project builds a modular ML pipeline that performs:

- Data Ingestion
- Data Validation
- Data Transformation
- Model Training
- Model Evaluation
- Model Registry using AWS S3
- Model Deployment
- Prediction Serving through **FastAPI**
- Docker Containerization
- CI/CD Automation with GitHub Actions
- Deployment on AWS EC2

Each pipeline stage is implemented independently, making the project scalable, maintainable, and easy to extend.

---

# 🏗️ High-Level Architecture

```text
                   Dataset
                      │
                      ▼
               MongoDB Atlas
                      │
                      ▼
             Data Ingestion Pipeline
                      │
                      ▼
            Data Validation Pipeline
                      │
                      ▼
         Data Transformation Pipeline
                      │
                      ▼
             Model Training Pipeline
                      │
                      ▼
            Model Evaluation Pipeline
                      │
                      ▼
             AWS S3 Model Registry
                      │
                      ▼
              Model Pusher Pipeline
                      │
                      ▼
           FastAPI Prediction Service
                      │
                      ▼
                Docker Container
                      │
                      ▼
                 Amazon ECR
                      │
                      ▼
                 Amazon EC2
```

---

# ✨ Key Features

- End-to-End MLOps workflow
- Modular pipeline architecture
- MongoDB Atlas integration
- Schema-based data validation
- Automated data transformation
- Model training pipeline
- Threshold-based model evaluation
- AWS S3 model registry
- Prediction API built with FastAPI
- Docker containerization
- GitHub Actions CI/CD
- Self-hosted GitHub Runner
- AWS EC2 deployment
- Configuration-driven project structure

---

# 🛠 Tech Stack

| Category | Technologies |
|-----------|--------------|
| Programming Language | Python 3.12 |
| API Framework | FastAPI |
| Database | MongoDB Atlas |
| Machine Learning | Scikit-Learn |
| Cloud Services | AWS S3, EC2, ECR |
| CI/CD | GitHub Actions |
| Containerization | Docker |
| Version Control | Git & GitHub |

---

# 📂 Pipeline Workflow

## 🚀 Project Initialization

- Generate project template using `template.py`
- Configure `setup.py`
- Configure `pyproject.toml`
- Create Conda environment
- Install project dependencies

---

## 🍃 MongoDB Atlas

Project setup includes:

- MongoDB Atlas Cluster
- Database User
- Network Access Configuration
- Connection String
- Dataset upload through Jupyter Notebook

The dataset is stored inside MongoDB Atlas and serves as the source for the ingestion pipeline.

---

## 📥 Data Ingestion

The ingestion module includes:

- MongoDB connection configuration
- Data access layer
- Configuration entities
- Artifact entities
- Data ingestion component
- Pipeline integration

This stage fetches records from MongoDB Atlas and converts them into a Pandas DataFrame for downstream processing.

---

## ✅ Data Validation

Validation is driven using a schema configuration.

Implemented components include:

- Dataset schema
- Validation utilities
- Validation configuration
- Validation artifacts

---

## 🔄 Data Transformation

Responsible for preparing data before training.

Includes:

- Feature transformation
- Estimator configuration
- Transformation artifacts
- Transformation pipeline

---

## 🤖 Model Training

The training pipeline consists of:

- Training configuration
- Model training
- Training artifacts
- Estimator implementation

---

## ☁️ AWS Integration

AWS services are used to maintain a centralized model registry.

Configured services include:

- IAM
- Amazon S3
- AWS Credentials
- AWS Connection Configuration
- Cloud Storage Utilities

The project maintains:

- Model Registry Bucket
- Registry Key
- Evaluation Threshold

---

## 📊 Model Evaluation

The evaluation component compares the newly trained model against the currently deployed production model stored in AWS S3.

Only models meeting the configured threshold are promoted for deployment.

---

## 📦 Model Pusher

Responsible for:

- Uploading trained models
- Registering production models
- Managing model artifacts inside AWS S3

---

## ⚡ Prediction Service

The serving layer includes:

- FastAPI application
- Prediction pipeline
- HTML templates
- Static assets

The API serves predictions using the latest approved model from the registry.

---

## 🐳 Dockerization

Containerization includes:

- Dockerfile
- .dockerignore
- Portable deployment image

---

## 🔄 Continuous Integration & Deployment

GitHub Actions automates:

- Docker image build
- Image push to Amazon ECR
- Deployment to AWS EC2 through a Self-hosted Runner

---

# ☁️ AWS Services

- IAM
- Amazon S3
- Amazon EC2
- Amazon ECR

---

# 🔐 Environment Variables

```bash
MONGODB_URL=<MongoDB Connection String>

AWS_ACCESS_KEY_ID=<AWS Access Key>

AWS_SECRET_ACCESS_KEY=<AWS Secret Key>

AWS_DEFAULT_REGION=us-east-1
```

---

# 🚀 Getting Started

## Clone Repository

```bash
git clone <repository-url>

cd <repository-name>
```

---

## Create Virtual Environment

```bash
conda create -n vehicle python=3.12 -y

conda activate vehicle
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Verify Installation

```bash
pip list
```

---

## Run Training Pipeline

```bash
python demo.py
```

---

## Start FastAPI Server

```bash
python app.py
```

> Depending on your implementation, the application can then be accessed on the configured host and port.

---

# 🐳 Docker

Build Docker image

```bash
docker build -t vehicleproj .
```

Run Docker container

```bash
docker run -p 5000:5000 vehicleproj
```

---

# 🌐 Deployment Flow

```text
GitHub Repository
        │
        ▼
 GitHub Actions Workflow
        │
        ▼
 Docker Image Build
        │
        ▼
 Amazon Elastic Container Registry (ECR)
        │
        ▼
 Amazon EC2
        │
        ▼
 FastAPI Prediction Service
```

---

# 📁 Project Structure

```text
Project
│
├── components
├── configuration
├── cloud_storage
├── constants
├── data_access
├── entity
├── notebook
├── static
├── templates
├── app.py
├── demo.py
├── template.py
├── setup.py
├── pyproject.toml
├── requirements.txt
├── Dockerfile
└── .github/
    └── workflows/
```

---

# 🔄 Complete MLOps Pipeline

```text
Dataset
    │
    ▼
MongoDB Atlas
    │
    ▼
Data Ingestion
    │
    ▼
Data Validation
    │
    ▼
Data Transformation
    │
    ▼
Model Training
    │
    ▼
Model Evaluation
    │
    ▼
AWS S3 Model Registry
    │
    ▼
Model Pusher
    │
    ▼
FastAPI Prediction API
    │
    ▼
Docker
    │
    ▼
Amazon ECR
    │
    ▼
Amazon EC2
```

---

# 💡 MLOps Concepts Demonstrated

- Modular Pipeline Architecture
- Configuration Management
- Artifact Management
- Data Validation
- Feature Engineering
- Model Registry
- Cloud Storage
- Model Versioning
- Continuous Integration
- Continuous Deployment
- Containerized Inference
- Production-ready API Serving

---

# ⭐ Project Highlights

- ✅ End-to-End MLOps Pipeline
- ✅ MongoDB Atlas Integration
- ✅ AWS S3 Model Registry
- ✅ FastAPI Prediction Service
- ✅ Dockerized Deployment
- ✅ GitHub Actions CI/CD
- ✅ Self-hosted GitHub Runner
- ✅ Amazon EC2 Deployment
- ✅ Modular and Scalable Architecture

---