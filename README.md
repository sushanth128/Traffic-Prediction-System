# Traffic Prediction Model Using METR-LA Dataset

![metr-la](https://github.com/user-attachments/assets/46b0ccac-3700-430b-aa6b-8ec5cb5f8a8b)

## Overview

This project is designed to develop, deploy, and monitor a traffic prediction model using the **METR-LA dataset**. The goal of this project is to predict traffic conditions in real-time, enabling better decision-making for traffic management systems. The entire workflow is divided into three distinct phases:

1. **Model Experimentation**: Developing and training machine learning models.
2. **Model Deployment**: Deploying the trained model using **Docker** and **Kubernetes**.
3. **Model Monitoring**: Monitoring the deployed model using **Evidently** for data drift and model performance.

By leveraging state-of-the-art techniques in machine learning and MLOps, this project aims to provide a scalable and efficient traffic prediction system.

## Key Technologies Used

- **Python**: Programming language for model development and experimentation.
- **LSTM**: Long Short-Term Memory models for sequence prediction.
- **GRU**: Gated Recurrent Units for time-series prediction.
- **Kubeflow Pipelines**: For orchestrating model training and experimentation.
- **Docker**: For containerizing the model API.
- **Kubernetes**: For deploying the containerized model in a scalable environment.
- **Flask**: For serving the machine learning model as a web API.
- **Evidently**: For model monitoring, checking data drift, and tracking model performance.

## Phases of the Project

### Phase 1: Model Experimentation

#### Goal:
The goal of this phase is to experiment with various machine learning models for traffic prediction using the **METR-LA** dataset. We use **LSTM** and **GRU** models, which are well-suited for time-series prediction.

#### Steps:
1. **Data Preprocessing**: The METR-LA dataset, which includes traffic data from different locations in Los Angeles, is preprocessed to ensure it is ready for training. This step includes normalization and feature selection.
2. **Model Training**: We implement an LSTM and GRU model to train on the processed dataset. 
3. **Experiment Tracking**: Using **Kubeflow Pipelines**, we track different experiments and their results. This helps to compare the effectiveness of different models and hyperparameters.

You can start the model training by running the `starter_notebook_phase_1.py` script.

### Phase 2: Model Deployment

#### Goal:
Once the model is trained and validated, the goal of this phase is to deploy it as a web API so it can be used for real-time predictions.

#### Steps:
1. **Flask API Setup**: A simple **Flask API** is created to serve the trained model. The API is responsible for taking traffic data as input and providing predictions based on the trained model.
2. **Dockerization**: We create a `Dockerfile` to containerize the Flask API. This allows the model to be deployed in any environment that supports Docker.
3. **Kubernetes Deployment**: The Docker container is then deployed on **Kubernetes** for scalability. Kubernetes ensures that the model can handle high traffic and scale based on demand.

You can refer to `starter_notebook_phase_2.py` for the Flask API and deployment steps.

### Phase 3: Model Monitoring

#### Goal:
The final phase of the project focuses on monitoring the model’s performance once it has been deployed. We use **Evidently**, an open-source tool, to monitor the model's predictions and track metrics like data drift and accuracy.

#### Steps:
1. **Monitoring Dashboard**: The `starter_notebook_phase_3.py` script generates an **Evidently** monitoring dashboard that helps you understand how the model is performing over time.
2. **Data Drift**: The dashboard provides insights into whether the incoming data distribution is changing, which can affect the model's accuracy.
3. **Model Performance**: You can view various metrics that help evaluate the performance of the model after deployment.

Check the `evidently_report.html` file for detailed insights on data drift and model performance.

## How to Run the Project

### Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/sushanth128/traffic-prediction-project.git
