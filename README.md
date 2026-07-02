# Academic Dropout Prediction Platform (MLOps-Oriented)

## Overview

This project is an end-to-end machine learning system designed to predict academic dropout risk in higher education environments. It focuses not only on model performance but also on the full lifecycle of machine learning systems, incorporating MLOps principles such as reproducibility, automation, versioning, and continuous training.

The system is structured as a collection of independent but integrated repositories, each responsible for a specific layer of the pipeline. This modular design allows scalability, maintainability, and clear separation of concerns.

The goal is to move beyond experimental models and provide a production-ready solution capable of continuous operation in real-world institutional settings.

---

## Architecture Summary

The project follows a typical MLOps workflow:

1. Data preprocessing and feature engineering
2. Model training and evaluation
3. Experiment tracking and model versioning
4. Pipeline orchestration
5. Infrastructure provisioning

Each of these stages is implemented in a dedicated repository.

---

## Repositories

### 1. [airflow](https://github.com/Pipeout/airflow)

This repository contains the orchestration layer of the system.

It defines Directed Acyclic Graphs (DAGs) responsible for:

* Coordinating preprocessing and training pipelines
* Scheduling workflows
* Managing dependencies between tasks
* Triggering retraining when new data is available

This is the central control point of the pipeline execution.

---

### 2. [preprocessing](https://github.com/Pipeout/preprocessing)

This repository is responsible for preprocessing the raw datasets and guaranteeing their consistency 

It provides:

* Data wrangling routines
* Checks of columns presence
* Checks of dataset consistency 

---

### 3. [feature engineering](https://github.com/Pipeout/featureEngineering)

This repository is responsible for generating the features and auditing for their correctness.

It provides:

* Feature generation script
* Audit of generated features

---

### 4. [model](https://github.com/Pipeout/model)

This repository contains the core machine learning logic.

It includes:

* Model training scripts
* Evaluation metrics and validation procedures

Experiments are typically conducted here before being integrated into the production pipeline.

---

### 5. [mlflow](https://github.com/Pipeout/mlflow)

This repository is responsible for experiment tracking and model lifecycle management.

It provides:

* Logging of parameters, metrics, and artifacts
* Model versioning
* Storage of trained models
* Reproducibility of experiments

It acts as the system of record for all model-related operations.

---

### 6. [IaC (Infrastructure as Code)](https://github.com/Pipeout/IaC)

This repository defines the infrastructure required to run the system.

It includes:

* Provisioning scripts (e.g., Terraform or similar tools)
* Definition of compute resources
* Environment configuration
* Deployment setup

This ensures that the entire environment can be recreated consistently across different machines or cloud providers.

---

## Key Characteristics

* Modular architecture with clear separation of concerns
* Reproducible machine learning workflows
* Automated pipelines for training and evaluation
* Version control for data, code, and models
* Scalable infrastructure defined programmatically

---

## Motivation

Most academic work on dropout prediction focuses on model performance, often neglecting how these models are deployed, maintained, and updated over time.

This project addresses that gap by integrating machine learning with software engineering practices, enabling continuous operation in dynamic environments where data distributions and student behavior evolve over time.

---

## Future Work

* Real-time inference API
* Monitoring and alerting for model drift
* Automated data validation pipelines
* Integration with institutional systems

---

## Final Notes

This project is not just a machine learning model. It is a complete system designed to handle the operational challenges of deploying predictive models in real-world academic environments.
