# Iris Flower Species Prediction

A machine learning web application that predicts the species of an Iris flower based on its sepal and petal measurements.

The application is built with **Python, Scikit-learn, Streamlit, NumPy, Pandas, and Joblib**. Users can provide four flower measurements through an interactive interface and receive an immediate species prediction.

---

## Overview

The **Iris Flower Species Prediction** project demonstrates how a trained machine learning classification model can be integrated into an interactive web application.

The application accepts the following flower measurements:

- Sepal Length
- Sepal Width
- Petal Length
- Petal Width

These measurements are passed to a previously trained machine learning model, which predicts the corresponding Iris species.

### Prediction Workflow

```text
User Input
    │
    ├── Sepal Length
    ├── Sepal Width
    ├── Petal Length
    └── Petal Width
          │
          ▼
    Feature Preparation
          │
          ▼
    Trained ML Model
          │
          ▼
    Species Prediction
          │
          ▼
    Streamlit Interface
```

---

## Features

- Interactive Streamlit web interface
- Four adjustable flower measurement inputs
- Pre-trained machine learning model
- Real-time species prediction
- Simple and intuitive user experience
- Iris dataset integration through Scikit-learn
- Serialized model loading using Joblib

The Streamlit application loads the trained model and uses the four user-provided measurements to generate the prediction. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

---

## Machine Learning

The project uses the **Iris dataset** provided by Scikit-learn.

The classification model is trained to identify the species of an Iris flower from its physical measurements.

### Input Features

| Feature | Unit |
|---|---|
| Sepal Length | cm |
| Sepal Width | cm |
| Petal Length | cm |
| Petal Width | cm |

The application exposes these four features as interactive sliders. :contentReference[oaicite:3]{index=3}

---

## Iris Species

The model predicts one of the three Iris species:

- **Iris Setosa**
- **Iris Versicolor**
- **Iris Virginica**

The predicted numerical class is mapped to its corresponding species name using Scikit-learn's Iris dataset. :contentReference[oaicite:4]{index=4}

---

## Application Interface

The application provides an interactive dashboard where users can adjust flower measurements before making a prediction.

### Input Ranges

| Measurement | Range |
|---|---:|
| Sepal Length | 4.0 – 8.0 cm |
| Sepal Width | 2.0 – 4.5 cm |
| Petal Length | 1.0 – 7.0 cm |
| Petal Width | 0.1 – 2.5 cm |

The application displays the prediction after the user clicks the **Predict** button. :contentReference[oaicite:5]{index=5}

---

## Example

### Input

```text
Sepal Length : 5.1 cm
Sepal Width  : 3.5 cm
Petal Length : 1.4 cm
Petal Width  : 0.2 cm
```

### Output

```text
Predicted Iris Species: setosa
```

---

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application and machine learning development |
| Streamlit | Interactive web application |
| Scikit-learn | Dataset and machine learning functionality |
| NumPy | Numerical data preparation |
| Pandas | Data handling |
| Joblib | Loading the trained model |
| Jupyter Notebook | Model development and experimentation |

---

## Project Structure

```text
Iris-Flower-Species-Prediction/
│
├── app.py
├── iris_model.pkl
├── iris_model.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

> The exact filenames in your repository should match the files used by the application.

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/DarshanS2004/Iris-Flower-Species-Prediction.git
```

### 2. Navigate to the Project

```bash
cd Iris-Flower-Species-Prediction
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

### 4. Activate the Virtual Environment

#### Windows

```powershell
.venv\Scripts\activate
```

#### macOS / Linux

```bash
source .venv/bin/activate
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Application

Start the Streamlit application with:

```bash
python -m streamlit run app.py
```

After starting the application, Streamlit will provide a local URL.

Usually:

```text
http://localhost:8501
```

Open the URL in your browser to access the application.

---

## How It Works

### 1. Load the Trained Model

The Streamlit application loads the serialized machine learning model using Joblib:

```python
model = joblib.load("iris_model.pkl")
```

This allows the application to use the previously trained model for predictions without retraining it every time the application starts. :contentReference[oaicite:6]{index=6}

### 2. Collect User Input

The application collects four measurements through Streamlit sliders:

```python
sepal_length
sepal_width
petal_length
petal_width
```

:contentReference[oaicite:7]{index=7}

### 3. Prepare the Features

The values are combined into a NumPy array:

```python
input_data = np.array([
    [sepal_length, sepal_width, petal_length, petal_width]
])
```

:contentReference[oaicite:8]{index=8}

### 4. Generate the Prediction

The trained model predicts the class:

```python
prediction = model.predict(input_data)
```

:contentReference[oaicite:9]{index=9}

### 5. Display the Species

The predicted class is converted into the corresponding Iris species name and displayed in the Streamlit interface. :contentReference[oaicite:10]{index=10}

---

## Machine Learning Pipeline

The overall machine learning workflow can be represented as:

```text
Iris Dataset
     │
     ▼
Feature Selection
     │
     ▼
Model Training
     │
     ▼
Model Evaluation
     │
     ▼
Model Serialization
     │
     ▼
iris_model.pkl
     │
     ▼
Streamlit Application
     │
     ▼
Real-Time Prediction
```

---

## Model Deployment Approach

Instead of training the model every time a user opens the application, the trained model is stored as a serialized file.

```text
Training Phase
      │
      ▼
Trained Model
      │
      ▼
Saved Model File
      │
      ▼
Streamlit Application
      │
      ▼
Prediction
```

This separates the **model development phase** from the **prediction application**.

---

## Use Cases

This project can be used as:

- A demonstration of machine learning classification
- A beginner-friendly ML deployment project
- A Streamlit application example
- A demonstration of model serialization
- A portfolio project for machine learning fundamentals
- An educational example of integrating ML with a web interface

---

## Skills Demonstrated

This project demonstrates practical understanding of:

- Machine learning classification
- Feature-based prediction
- Scikit-learn
- Model serialization
- Joblib
- NumPy
- Pandas
- Streamlit
- Interactive user interfaces
- Python application development

---

## Future Improvements

Potential improvements include:

- Display prediction probabilities
- Add model performance metrics
- Add confusion matrix visualization
- Compare multiple classification algorithms
- Display feature importance
- Add sample input presets
- Add batch prediction using CSV files
- Improve the visual design of the dashboard
- Deploy the application to a cloud platform

---

## Project Status

**Status:** Completed

The application provides an interactive interface for entering Iris flower measurements and generating a species prediction using the trained machine learning model.

---

## Author

**Darshan S**

GitHub:  
`https://github.com/DarshanS2004`

---

## License

This project is intended for educational and portfolio purposes.