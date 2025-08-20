
# Deploy SVC Model in Azure

In this project, I will build and deploy a Support Vector Classification learning model using the diabetes dataset to predict whether a patient has diabetic or not. The diabetes dataset is a classic dataset in machine learning, containing information about patient such as BMI, gender, age, and other features.

The primary objective of this project is to create a web application that allows users to input patient details and get predictions in real time. I will implement the application using Flask, a lightweight Python web framework, and deploy it on Microsoft Azure as a cloud-based service.

Once deployed, the web application will have a publicly accessible URL, providing an interactive interface where users can input data and see survival predictions instantly. This project demonstrates end-to-end machine learning workflow — from data preprocessing and model training to cloud deployment and web integration.


## About files

* diabetes_model_for_api.py: This file is used for data preprocessing and model training. A SVC is trained on the preprocessed diabetes dataset and then saved as a pickle file for later deployment in the API.

* Front-End Development: The HTML and CSS files for the web application’s interface were created and organized into templates and static folders, respectively. The templates folder contains the HTML files that define the structure of the web pages, while the static folder holds the CSS files to style the application, providing a clean and user-friendly interface

* The app.py file serves as the main Flask application for the Patient Diabetic prediction project. It loads the pre-trained SVC model from the diabetes_model.pkl pickle file and provides both a web interface and an API endpoint for making predictions. The root route (/) renders the home page (home.html) where users can input patient details. The /predict route processes these inputs, converts them into a format suitable for the model, predicts whether the pateint has diabetics or not, and displays the result on the web page. Additionally, the /predict_api route allows direct API calls using JSON data, returning predictions programmatically. This setup enables seamless interaction with the model, both through a user-friendly web interface and via API requests, making it ready for deployment on Azure with a public URL

#### Note:
if youre using a linux os, apply below line under the configuration tab as a startup command

gunicorn --bind=0.0.0.0:$PORT app:app
