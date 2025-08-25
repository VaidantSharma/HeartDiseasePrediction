# 🫀 Cardio-Monitor: Heart Disease Prediction System

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/flask-2.0+-green.svg)](https://flask.palletsprojects.com/)
[![Scikit-learn](https://img.shields.io/badge/sklearn-0.24+-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An intelligent web application that predicts the risk of heart disease using machine learning algorithms. The system achieves **92% accuracy** in predicting heart disease based on various medical parameters.

![Application Workflow](https://raw.githubusercontent.com/VaidantSharma/Cardio-Monitor/main/Input%20Data.png)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Machine Learning Model](#machine-learning-model)
- [API Endpoints](#api-endpoints)
- [Data Visualization](#data-visualization)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

Heart disease is one of the leading causes of death globally. Early detection and continuous monitoring can significantly reduce mortality rates. This project leverages machine learning and big data analytics to create a real-time heart disease prediction system that can help healthcare professionals and individuals assess cardiovascular risk.

### Key Objectives

- Early detection of heart disease using medical parameters
- Real-time prediction with high accuracy (92%)
- User-friendly web interface for easy interaction
- Data visualization for better understanding of health metrics
- Scalable architecture for handling large datasets

## ✨ Features

- **Real-time Prediction**: Instant heart disease risk assessment based on user input
- **High Accuracy**: Machine learning model with 92% accuracy
- **Interactive Web Interface**: User-friendly Flask-based web application
- **Data Visualization**: Comprehensive charts and graphs for health metrics analysis
- **Database Integration**: MongoDB for storing user data and predictions
- **Responsive Design**: Works seamlessly across different devices
- **Health Metrics Comparison**: Compare user values with normal ranges

## 🛠 Technology Stack

### Core Technologies

- **Backend**: Python 3.8+, Flask
- **Machine Learning**: Scikit-learn, XGBoost, NumPy, Pandas
- **Database**: MongoDB, PyMongo
- **Data Visualization**: Matplotlib, Seaborn
- **Frontend**: HTML5, CSS3, JavaScript
- **Deployment**: Gunicorn, Heroku

### Machine Learning Libraries

- **Scikit-learn**: Model building and evaluation
- **XGBoost**: Gradient boosting algorithms
- **NumPy**: Numerical computations
- **Pandas**: Data manipulation and analysis
- **Matplotlib/Seaborn**: Data visualization

## 📁 Project Structure

```
Cardio-Monitor/
├── app.py                          # Main Flask application
├── prediction.py                   # ML prediction logic
├── modelbuild.py                   # Model training and building
├── database.py                     # Database operations
├── visualization.py                # Data visualization functions
├── Heart_model1.pkl               # Trained ML model
├── heartmodel.pkl                 # Alternative model
├── heart.csv                      # Training dataset
├── requirements.txt               # Python dependencies
├── Procfile                       # Heroku deployment
├── README.md                      # Project documentation
├── static/                        # Static assets (CSS, JS, images)
│   ├── heartlogo.png
│   ├── heart.gif
│   └── corousal/
├── templates/                     # HTML templates
│   ├── home.html
│   ├── disease.html
│   ├── result.html
│   └── error.html
└── heart disease prediction/      # Research notebooks
    ├── Notebooks/
    └── EDA/
```

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- MongoDB (local or cloud instance)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/VaidantSharma/HeartDiseasePrediction.git
cd Cardio-Monitor
```

### Step 2: Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Set Up Environment Variables

1. Copy the `.env.example` file to `.env`:
   ```bash
   cp .env .env.local  # or create your own .env file
   ```

2. Edit the `.env` file and add your MongoDB credentials:
   ```
   DATABASE_LINK=mongodb+srv://your_username:your_password@heart.9ynzc.mongodb.net/Heartpatientdatabase?retryWrites=true&w=majority
   ```

### Step 5: Set Up Database

1. Install MongoDB locally or use MongoDB Atlas
2. Ensure your DATABASE_LINK environment variable is properly set

### Step 6: Run the Application

```bash
python app.py
```

The application will be available at `http://localhost:5000`

## 💻 Usage

### Input Parameters

The system requires the following medical parameters for prediction:

1. **Age**: Patient's age in years
2. **Sex**: Male/Female
3. **Chest Pain Type**:
   - Typical Angina
   - Atypical Angina
   - Non-anginal Pain
   - Asymptomatic
4. **Resting Blood Pressure**: mm Hg
5. **Cholesterol**: mg/dl
6. **Fasting Blood Sugar**: >120 mg/dl (Yes/No)
7. **Rest ECG**:
   - Normal
   - ST-T Wave abnormality
   - Left ventricular hypertrophy
8. **Max Heart Rate**: Achieved during exercise
9. **Exercise Induced Angina**: Yes/No
10. **ST Depression**: Induced by exercise
11. **Peak Exercise ST Segment**:
    - Upsloping
    - Flat
    - Downsloping
12. **Number of Major Vessels**: (0-3)
13. **Thalassemia**: Normal/Fixed defect/Reversible defect

### How to Use

1. Navigate to the home page
2. Fill in all required medical parameters
3. Click "Predict" to get the risk assessment
4. View the results with probability scores
5. Analyze the comparison charts with normal values

## 🤖 Machine Learning Model

### Algorithm

The system uses **K-Nearest Neighbors (KNN)** classifier with the following specifications:

- **Algorithm**: KNN with optimized parameters
- **Accuracy**: 92%
- **Features**: 13 medical parameters
- **Preprocessing**: StandardScaler for feature normalization
- **Cross-validation**: Used for model validation

### Model Performance

- **Accuracy**: 92%
- **Precision**: High precision in positive predictions
- **Recall**: Effective in identifying true positive cases
- **F1-Score**: Balanced performance metric

### Model Training Process

1. Data preprocessing and cleaning
2. Feature scaling using StandardScaler
3. Train-test split (80-20)
4. Hyperparameter tuning
5. Cross-validation
6. Model serialization using joblib

## 🌐 API Endpoints

### Main Routes

- `GET /` - Home page with input form
- `POST /disease` - Process prediction request
- `GET /result` - Display prediction results
- `GET /plot1.png` - Generate comparison visualization
- `GET /error` - Error handling page

### Database Operations

- Store user input data
- Save prediction results
- Retrieve historical data for analysis

## 📊 Data Visualization

The application provides comprehensive visualizations:

### 1. Health Metrics Comparison

- Bar charts comparing user values with normal ranges
- Color-coded indicators for risk levels

### 2. Feature Importance

- Visualization of which parameters contribute most to the prediction

### 3. Historical Trends

- Track changes in health metrics over time

## 🔒 Security

### Environment Variables
This application uses environment variables to store sensitive information like database credentials. 

**Important Security Notes:**
- Never commit `.env` files to version control
- Rotate MongoDB credentials immediately if they were exposed
- Use strong, unique passwords for database access
- Consider using MongoDB Atlas IP whitelisting for additional security

### Setting Up Secure Credentials
1. Create a `.env` file in the project root
2. Add your MongoDB connection string:
   ```
   DATABASE_LINK=mongodb+srv://username:password@cluster.mongodb.net/database
   ```
3. Ensure `.env` is listed in `.gitignore`

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 style guidelines
- Add docstrings to functions
- Include unit tests for new features
- Update documentation as needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Vaidant Sharma**

- GitHub: [@VaidantSharma](https://github.com/VaidantSharma/)
- LinkedIn: [Vaidant Sharma](https://www.linkedin.com/in/vaidant-sharma-7435592a4)

## 🙏 Acknowledgments

- Dataset sourced from UCI Machine Learning Repository
- Flask documentation and community
- Scikit-learn contributors
- MongoDB community

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/VaidantSharma/HeartDiseasePrediction/issues) page
2. Create a new issue with detailed description
3. Contact the maintainer

---

⭐ **Star this repository if you find it helpful!**
