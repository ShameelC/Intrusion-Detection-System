# Intrusion Detection System (IDS) Using Machine Learning

## Overview
This project implements an Intrusion Detection System (IDS) using a machine learning approach. It uses a RandomForestClassifier to classify network traffic data and detect intrusions. The system preprocesses the data, trains the model, evaluates its performance, and deploys it as a RESTful web service using Flask.

## Project Structure
ids-project/
│
├── data/
│   ├── KDDTrain+.txt                 # Training data
│   └── KDDTest+.txt                  # Test data
│
├── model/
│   └── random_forest_id_model.pkl    # Trained RandomForestClassifier model
│
├── visualization/
│   ├── visualization_random_forest_metrics.png  # Visualization of model metrics
│   ├── confusion_matrix_random_forest.png       # Confusion matrix plot
│   └── roc_curve_random_forest.png              # ROC curve plot
│
├── app.py                               # Flask application for model deployment
├── requirements.txt                     # List of Python package dependencies
├── preprocess.py                        # Data preprocessing script
├── train_model.py                       # Model training script
├── evaluate_model.py                    # Model evaluation script
└── README.md                            # Project documentation


## Features
- **Data Preprocessing**: Cleans and encodes categorical variables, handles missing values.
- **Model Training**: Trains a RandomForestClassifier model on network traffic data.
- **Evaluation**: Generates accuracy, precision, recall, and F1-score metrics. Visualizes confusion matrix and ROC curve.
- **Deployment**: Deploys the trained model using Flask, providing an endpoint for making predictions.

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/ids-project.git
    cd ids-project
    ```

2. Create and activate a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # For Windows use `venv\Scripts\activate`
    ```

3. Install required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
1. Run the Flask web application:
    ```bash
    python app.py
    ```

2. Make POST requests to the `/predict` endpoint with JSON data. Example request using `curl`:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"duration": 10, "protocol_type": 1, "service": 2, "flag": 0, "src_bytes": 100, "dst_bytes": 200, "land": 0, "wrong_fragment": 0, "urgent": 0, "hot": 0, "num_failed_logins": 0, "logged_in": 1, "num_compromised": 0, "root_shell": 0, "su_attempted": 0, "num_root": 0, "num_file_creations": 0, "num_shells": 0, "num_access_files": 0, "num_outbound_cmds": 0, "is_host_login": 0, "is_guest_login": 0, "count": 10, "srv_count": 10, "serror_rate": 0, "srv_serror_rate": 0, "rerror_rate": 0, "srv_rerror_rate": 0, "same_srv_rate": 1, "diff_srv_rate": 0, "srv_diff_host_rate": 0, "dst_host_count": 1, "dst_host_srv_count": 1, "dst_host_same_srv_rate": 1, "dst_host_diff_srv_rate": 0, "dst_host_same_src_port_rate": 1, "dst_host_srv_diff_host_rate": 0, "dst_host_serror_rate": 0, "dst_host_srv_serror_rate": 0, "dst_host_rerror_rate": 0, "dst_host_srv_rerror_rate": 0}' http://127.0.0.1:5000/predict
    ```

3. The response will be a JSON object containing the prediction.

## Dependencies
- Flask
- pandas
- numpy
- matplotlib
- scikit-learn
- imbalanced-learn
- shap
- joblib

## Evaluation Metrics
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

## Visualizations
- Metrics bar chart
- Confusion matrix plot
- ROC curve

## License
This project is licensed under the MIT License. You are free to use, modify, and distribute this project as per the license terms.

## Acknowledgements
- The dataset used in this project is the KDD Cup 1999 dataset, which is widely used for network intrusion detection research.
- The project relies on several Python libraries, including `scikit-learn`, `pandas`, and `Flask`.

## Author
Shameel (Cybersecurity Enthusiast)

