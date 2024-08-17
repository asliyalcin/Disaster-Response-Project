# Disaster Response Pipeline Project

## Overview

The Disaster Response Pipeline Project aims to build an efficient web application for classifying disaster response messages. By integrating a robust machine learning pipeline, this application ensures that incoming messages are accurately categorized and directed to the relevant disaster response agencies. This streamlined process improves the speed and effectiveness of emergency responses, helping to manage crises more effectively.

## Objective
The primary goal is to ensure that each message, whether it concerns an earthquake, fire, or any other disaster, is accurately categorized and routed to the appropriate disaster response agency. This routing helps streamline response efforts, enabling quicker and more effective action in crisis situations.


## Table of Contents
1. [Overview](#overview)
2. [Components](#components)
   - [ETL Pipeline](#etl-pipeline)
   - [ML Pipeline](#ml-pipeline)
   - [Flask Web Application](#flask-web-application)
3. [Setup Instructions](#setup-instructions)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
   - [Running the Pipelines](#running-the-pipelines)
   - [Running the Web Application](#running-the-web-application)
4. [File Descriptions](#file-descriptions)

## Components

### ETL Pipeline

The ETL (Extract, Transform, Load) pipeline processes data through the following steps:

- **Load Data:** Imports disaster messages and category datasets.
- **Merge Datasets:** Integrates both datasets into a unified format for consistency.
- **Data Cleaning:** Cleanses and preprocesses the data to prepare it for analysis.
- **Storage:** Saves the processed data into an SQLite database, ensuring it is ready for use in the machine learning model.

### ML Pipeline

The ML (Machine Learning) pipeline handles the development and evaluation of the classification model:

- **Data Retrieval:** Loads the cleaned data from the SQLite database.
- **Data Splitting:** Splits the dataset into training and test sets to evaluate model performance.
- **Model Building:** Constructs a pipeline for text processing and machine learning.
- **Training & Tuning:** Utilizes GridSearchCV to optimize the model's performance through hyperparameter tuning.
- **Evaluation:** Assesses the model on the test set to ensure accuracy and reliability.
- **Exporting:** Saves the trained model as a pickle file for future deployment and use.

### Flask Web Application

The Flask web application serves as the interface for user interaction:

- **Model Integration:** Loads the trained model and relevant data from the database.
- **User Interface:** Provides a user-friendly platform for inputting disaster messages.
- **Message Classification:** Classifies input messages and displays the categorized results.
- **Data Visualization:** Incorporates interactive visualizations using Plotly to enhance data insights and user experience.

## Setup Instructions

### Prerequisites

- **Python 3.6 or higher**
- **Required Libraries:** pandas, numpy, sqlalchemy, nltk, scikit-learn, Flask, Plotly, pickle
- Additional dependencies are listed in `requirements.txt`.

### Installation

1. **Clone the Repository:**
    ```bash
    git clone https://github.com/asliyalcin/Disaster-Response-Project
    cd your_repository
    ```

2. **Install Required Libraries:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Download NLTK Data:**
    ```bash
    python -m nltk.downloader punkt stopwords wordnet
    ```

### Running the Pipelines

- **ETL Pipeline:**
    ```bash
    python process_data.py disaster_messages.csv disaster_categories.csv DisasterResponse.db
    ```

- **ML Pipeline:**
    ```bash
    python train_classifier.py DisasterResponse.db classifier.pkl
    ```

### Running the Web Application

1. **Start the Flask App:**
    ```bash
    python run.py
    ```

2. **Open in Browser:**
    Navigate to [http://localhost:3001/](http://localhost:3001/) to access the web application.

## File Descriptions

- `process_data.py`: Script for processing and cleaning the data.
- `train_classifier.py`: Script for training and saving the machine learning model.
- `run.py`: Flask application script to run the web interface.
- `DisasterResponse.db`: SQLite database containing the cleaned data.
- `classifier.pkl`: Serialized machine learning model.
- `data/`: Directory containing the raw datasets.
- `app/`: Directory containing web application templates and static files.

