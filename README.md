Disaster Response Pipeline Project
Overview
This project develops a web application to classify disaster response messages efficiently. By leveraging a machine learning pipeline, the application categorizes messages, ensuring they reach the appropriate disaster response agency in a timely manner.

Components
ETL Pipeline
The ETL (Extract, Transform, Load) pipeline performs the following tasks:

Load Data: Imports disaster messages and categories datasets.
Merge Datasets: Integrates the two datasets into a unified format.
Data Cleaning: Cleans and preprocesses the data for analysis.
Storage: Saves the cleaned data into an SQLite database.
ML Pipeline
The ML (Machine Learning) pipeline handles:

Data Retrieval: Loads data from the SQLite database.
Data Splitting: Divides the dataset into training and test sets.
Model Building: Constructs a text processing and machine learning pipeline.
Training & Tuning: Uses GridSearchCV to optimize model performance.
Evaluation: Assesses the model on the test set.
Exporting: Saves the trained model as a pickle file for future use.
Flask Web Application
The web application:

Model Integration: Loads the trained model and data from the database.
User Interface: Provides a platform for users to input disaster messages.
Message Classification: Categorizes messages and displays results.
Data Visualization: Features interactive plots created with Plotly.
Setup Instructions
Prerequisites
Python 3.6 or higher
Required Libraries: pandas, numpy, sqlalchemy, nltk, scikit-learn, Flask, Plotly, pickle
Additional dependencies listed in requirements.txt
