Diabetes Prediction System 🩺
This project uses Machine Learning to predict whether a person is diabetic or non-diabetic based on specific health metrics (Pregnancies, Glucose, Blood Pressure, BMI, etc.). It utilizes a Support Vector Machine (SVM) model to achieve high prediction accuracy.

🚀 Features
Data Analysis: Exploration of the PIMA Diabetes Dataset.

SVM Classifier: Implementation of a Linear SVC for binary classification.

Model Serialization: Uses pickle to save the trained model for later use without retraining.

Predictive System: A reusable function/block to test individual user data.

📊 Dataset Info
The dataset used is the PIMA Diabetes Dataset. It contains health-related records for 768 individuals:

Features: Pregnancies, Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, Age.

Target: Outcome (1 = Diabetic, 0 = Non-Diabetic).

🛠️ Installation & Setup
To run this project locally, ensure you have Python installed, then follow these steps:

Clone the repository:

Bash
git clone https://github.com/your-username/diabetes-checker.git
cd diabetes-checker
Install required libraries:

Bash
pip install numpy pandas scikit-learn
Prepare the dataset:
Make sure diabetes.csv is in the project directory.

📈 Model Performance
Based on the current training:

Training Data Accuracy: ~78.3%

Test Data Accuracy: ~77.2%

🖥️ How to Use
You can use the saved model (trained_model.sav) to make predictions directly:

Python
import pickle
import numpy as np

# Load the saved model
loaded_model = pickle.load(open('trained_model.sav', 'rb'))

# Example input: 1 pregnancy, 85 glucose, 66 BP, 29 Skin, 0 Insulin, 26.6 BMI, 0.351 DPF, 31 Age
input_data = (1, 85, 66, 29, 0, 26.6, 0.351, 31)
input_as_numpy = np.asarray(input_data).reshape(1, -1)

prediction = loaded_model.predict(input_as_numpy)

if prediction[0] == 0:
    print('The person is not diabetic')
else:
    print('The person is diabetic')
📂 Project Structure
diabetes_analysis.ipynb: The main notebook containing data cleaning, visualization, and model training.

diabetes.csv: The dataset file.

trained_model.sav: The serialized SVM model.

README.md: Project documentation.

📝 License
This project is open-source and available under the MIT License.
