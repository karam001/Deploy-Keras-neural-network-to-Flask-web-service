# Dog vs Cat classification with Keras and deployment with Flask
This project consists of a front-end application for image classification and a backend application using Python and Flask to host a VGG16 model.

## Prerequisites
Before running the code, ensure that you have installed all dependencies:
- Python	3.6.10
- TensorFlow	2.5.0
- Flask	1.1.2
- numpy	1.17.0

## Getting Started
1. Clone the repository :

`git clone https://github.com/karam001/Deploy-Keras-neural-network-to-Flask-web-service.git`


2. In the workspace, export the application source code

`set FLASK_APP = predict_app.py`

If you are working on Linux, use the following command

`export FLASK_APP = predict_app.py`

3. Then run the web service

`flask run`

4. Visit http://localhost:5000/static/predict.html

you find the front-end web page. Upload your image file.

Ensure that the image is a **.png** image. Then make predictions.

## Project Guide

The purpose of this project is not to create and train our model.

I use a VGG16 pre-trained model to classify images of cats and dogs.

The pre-trained weights file is downloaded from Kaggle with _val_accuracy: 0.9822_

The objective is to host this model in a Flask web service and use it on front-end application to predict images

## Project structure

predict_app.py:

This Flask web service loads the VGG model and preprocesses the images to correspond to the Keras model. 

  - **/predict** endpoint is defined to handle POST requests.
  
  - Decodes the base64-encoded image received in the request.
  
  - Preprocesses the image using the defined function.
  
  - Makes predictions using the loaded VGG model.
  
  - Returns the prediction results in JSON format.

The directory static contains the static files (HTML files so Flask can serve the web service.

predict.html: 

This file serves as the frontend for the image classifier web service. It allows users to upload an image, display it on the page, and make predictions using the hosted VGG model.

  - JavaScript code using jQuery to handle image selection, display, and send predictions to the Flask backend.
  
  - Reads the selected image, displays it on the page, and sends a POST request to the /predict endpoint with the base64-encoded image.

  - Displays the predictions for the "Dog" and "Cat" classes.

## Results :

![Capture d'écran 2024-01-21 213854](https://github.com/karam001/Deploy-Keras-neural-network-to-Flask-web-service/assets/107030749/065e6aec-7fd3-4f55-96d9-f8263d4d68ee)

