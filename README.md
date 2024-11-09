
# House Price Prediction Web Application

This project is a web application built using Flask, allowing users to predict house prices based on various input features. The underlying model used for predictions is a **Random Forest Regressor**, which has been trained on a housing dataset. The application provides two endpoints for predictions: one via a form on a web page and another via a JSON API.

## Project Structure
```
/house_price_prediction
|-- app.py                 # Flask app with endpoints for prediction
|-- regmodel.pkl           # Pickled Random Forest Regressor model
|-- scaling.pkl            # Scaler used to standardize inputs
|-- home.html              # HTML file for the front-end interface
|-- requirements.txt       # List of Python dependencies
|-- README.md              # Project documentation
```

## Table of Contents
1. [Project Setup](#project-setup)
2. [Running the Application](#running-the-application)
3. [Endpoints](#endpoints)
4. [Requirements](#requirements)
5. [License](#license)

## Project Setup

### 1. Clone the Repository
First, clone the repository or download the project files to your local machine:
```bash
git clone <repository-url>
cd house_price_prediction
```

### 2. Install Dependencies
To install the required libraries, create a virtual environment and install the dependencies from `requirements.txt`:
```bash
# Create a virtual environment (optional but recommended)
python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scriptsctivate`

# Install the dependencies
pip install -r requirements.txt
```

### 3. Files in the Project
- **`regmodel.pkl`**: This file contains the trained **Random Forest Regressor** model.
- **`scaling.pkl`**: This file contains the scaler used to standardize input features before passing them to the model.
- **`home.html`**: This is the HTML page where users will input the required features and receive predictions.
- **`app.py`**: The Python script that runs the Flask application and defines the prediction routes.

### 4. Set Up Pre-trained Model
Ensure that the pre-trained model (`regmodel.pkl`) and scaler (`scaling.pkl`) are available in the project directory. These files were created using the following steps:
- The **Random Forest model** was trained on housing data using `RandomizedSearchCV` to tune hyperparameters.
- The **scaler** was fitted to the training data and saved using `pickle`.

## Running the Application

### 1. Start the Flask Application
Once the environment is set up, start the Flask application by running:
```bash
python app.py
```

The application will start a local server. By default, the app will run on `http://127.0.0.1:5000/`.

### 2. Access the Web Interface
Open your browser and visit the following URL to access the prediction form:
```
http://127.0.0.1:5000/
```

The user interface (`home.html`) allows users to input various house features (e.g., number of bedrooms, area, etc.) and receive a predicted house price.

## Endpoints

The application provides two routes for predictions:

### 1. `/predict` (POST Method)
This route receives form data from the HTML interface. The data is processed, scaled using the pre-trained scaler, and passed through the Random Forest model to predict the house price.

**Request**:
- Input: Form data containing the house features.
- Example:
  - Feature 1: 2500 (Square Footage)
  - Feature 2: 3 (Number of Bedrooms)
  - Feature 3: 2 (Number of Bathrooms)
  
**Response**:
- Output: Predicted house price.

**Usage**: Submit the form on the homepage to get the prediction.

## Application Interface

Below is a screenshot of the application interface where users can input various features to predict house prices:

![Boston House Price Prediction Interface](image.png)


## Requirements

Make sure you have the following Python libraries installed:
- `Flask`: For building the web application and serving the endpoints.
- `scikit-learn`: For loading the model and preprocessing the data.
- `numpy`: For handling array operations.
- `pandas`: For data manipulation and handling input data.
- `pickle`: For saving and loading the model and scaler.
  
### Install Required Libraries
You can install all the dependencies from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```

Here's a sample `requirements.txt` file for this project:
```txt
Flask==2.0.2
scikit-learn==1.0.2
numpy==1.21.4
pandas==1.3.3
```

