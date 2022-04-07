# TrinhNKL-Project_2_Disaster-Response-Pipeline_Data-Science-Project

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Instructions](#instructions)



## Installation <a name="installation"></a>

There are some neccessary library nees to install such as: numpy, pandas, matplolib, seaborn, wordcloud.  The code should run with no issues using Python versions 3.*.

## Project Motivation<a name="motivation"></a>

In this project, I will process with thousands of real messages provided by Appen, then build an ETL pipeline that processes messages and load them into a SQLite database. After that I will build the machine learning pipeline that can read from the database to create a supervised learning model with some of algorithm was applied.
Finally, your web app will extract data from this database and use your model to classify new messages.

## File Descriptions <a name="files"></a>
There are three main foleders:

1. data
- disaster_categories.csv: dataset including all the categories
- disaster_messages.csv: dataset including all the messages
- process_data.py: ETL pipeline scripts to read, clean, and save data into a database
- disaster_response_data.db: output of the ETL pipeline, i.e. that can be load in sqlite to check the content
2. model
- train_classifier.py: machine learning pipeline scripts to train and export a classifier
- model.pkl: this is an output of the machine learning pipeline
3. app
- run.py: Flask file to run the web application
- templates contains html file for the web applicatin


## Results<a name="results"></a>
The main result will include:
- An ETL pipleline was built to read data from two csv files, clean data, and save data into a SQLite database.
- A machine learning pipepline was developed to train a classifier to performs multi-output classification on the 36 categories in the dataset.
- A Flask app was created to show data visualization and classify the message that user enters on the web page.
-
## Instructions:<a name="instructions"></a>
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/disaster_response_data.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/disaster_response_data.db models/model.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
