# Disaster Response Pipeline Project

This project is part of the Data Science Nanodegree Program by Udacity. The initial dataset contains pre-labelled tweet and messages from real-life disaster situations. The aim of the project is to build a Natural Language Processing tool that categorize messages.

The Project is divided in the following Sections:

1. Data Processing, ETL Pipeline to extract data from source, clean data and save them in a proper database structure.
2. Machine Learning Pipeline to train a model able to classify text message in categories.
3. Web App to show model results in real time.

## Project Components

1. **ETL Pipeline**: A Python script, `process_data.py`, writes a data cleaning pipeline that:
    - Loads the `messages` and `categories` datasets
    - Merges the two datasets
    - Cleans the data
    - Stores it in a SQLite database

2. **ML Pipeline**: A Python script, `train_classifier.py`, writes a machine learning pipeline that:
    - Loads data from the SQLite database
    - Splits the dataset into training and test sets
    - Builds a text processing and machine learning pipeline
    - Trains and tunes a model using GridSearchCV
    - Outputs results on the test set
    - Saves the final model as a pickle file

3. **Flask Web App**: A Python script, `run.py`, provides a web app where an emergency worker can input a new message and get classification results in several categories. The web app also displays visualizations of the data.

## Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/


## Folder Structure
The project workspace has the following structure:

- app
    - template
        - master.html  (main page of the web app)
        - go.html  (classification result page of web app)
    - run.py  (Flask file that runs the app)

- data
    - disaster_categories.csv  (data to process)
    - disaster_messages.csv  (data to process)
    - process_data.py  (data processing script)
    - DisasterResponse.db   (database to save clean data to)

- models
    - train_classifier.py  (training script)
    - classifier.pkl  (saved model)

