### 📊 Student Math Score Prediction – ML Project

This project aims to predict students' **math scores** based on various features such as gender, parental level of education, lunch type, and test preparation course. It's a complete **end-to-end machine learning pipeline**, from data ingestion to model deployment.

---

## 📁 Project Structure

mlproject/
├── app.py
├── application.py
├── requirements.txt
├── setup.py
├── Dockerfile
├── README.md
├── templates/
│ ├── home.html
│ └── index.html
├── src/
│ └── mlproject/
│ ├── components/
│ │ ├── data_ingestion.py
│ │ ├── data_transformation.py
│ │ ├── model_trainer.py
│ ├── utils.py
│ ├── logger.py
│ ├── exception.py
├── artifacts/
│ ├── model.pkl
│ ├── preprocessor.pkl
│ ├── train.csv
│ ├── test.csv
├── notebook/
│ ├── data/
│ │ ├── raw.csv
│ ├── 1. EDA STUDENT PERFORMANCE.ipynb
│ ├── 2. MODEL TRAINING.ipynb


---

## 📊 Dataset Overview

- **Source**: [Student Performance Data](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Target Variable**: `math score`

### 🧾 Features Used:
- `gender`
- `race/ethnicity`
- `parental level of education`
- `lunch`
- `test preparation course`
- `reading_score`
- `writing_score`

---

## 🧠 Problem Statement

Can we predict a student’s math score accurately using other exam scores and demographic background?

---

## 🛠️ Tech Stack

- **Languages**: Python  
- **Libraries**: Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn  
- **Framework**: Flask (for web deployment)  
- **Tools**: Jupyter Notebook, Pickle (model serialization)

---

## 🔁 ML Pipeline

### 1. Data Ingestion
- Loads the `raw.csv` file
- Splits data into `train.csv` and `test.csv` under `artifacts/`

### 2. Data Transformation
- Encodes categorical features
- Scales numerical features using `StandardScaler`
- Saves transformer as `preprocessor.pkl`

### 3. Model Training
- Trained with **Linear Regression**
- Evaluated with R² score
- Best model saved as `model.pkl`

### 4. Prediction Pipeline
- Loads saved model and preprocessor
- Makes predictions on new inputs

---

## 📈 Model Performance

| Model             | R² Score |
|------------------|----------|
| Linear Regression | ✅ 0.82 (Best) |

---

## 📉 EDA Highlights

📓 Found in: `notebook/1. EDA STUDENT PERFORMANCE.ipynb`

- Gender and parental education have impact on scores
- Students who completed test preparation scored higher
- **Derived features created**:
  - `total_score` = math + reading + writing
  - `average` = total_score / 3
- Visualizations include histograms, boxplots, and correlation heatmaps

---

## 💻 Web App - Flask Interface

A simple web interface is built using Flask where users can input values and get a predicted math score.

### 📁 Files:
- `app.py`: Main Flask application
- `templates/home.html`: Input form
- `templates/index.html`: Prediction result display

---

## ▶️ How to Run Locally

Follow these steps to set up and run the project on your local machine:

### 1️⃣ Prerequisites
Make sure you have installed:
- [Python 3.10+](https://www.python.org/downloads/)  
- [Git](https://git-scm.com/downloads)  
- (Optional but recommended) [VS Code](https://code.visualstudio.com/)  

Check installation:
```bash
python --version
git --version
```

---

### 2️⃣ Clone the Repository
```bash
git clone https://github.com/byte-Shubham/mlproject.git
cd mlproject
```

---

### 3️⃣ Create and Activate Virtual Environment

#### On **Windows**:
```bash
python -m venv venv
venv\Scripts\activate
```

#### On **Mac/Linux**:
```bash
python3 -m venv venv
source venv/bin/activate
```

(You should see `(venv)` in your terminal once it’s activated.)

---

### 4️⃣ Install Dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

### 5️⃣ Run the Flask Application
```bash
python app.py
```

If successful, you’ll see something like:
```
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

Now open your browser and go to 👉 [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

### 6️⃣ Using the App
- Homepage → `index.html`  
- Prediction Form → `home.html`  
- Enter details (gender, education, lunch type, test prep, scores) → Get **predicted math score**  

---

### 7️⃣ Folder Structure Overview
```
mlproject/
├── app.py                # Flask entry point
├── requirements.txt      # Dependencies
├── templates/            # HTML templates (index & home)
├── src/mlproject/        # ML pipeline code
├── artifacts/            # Saved model & preprocessor
├── notebook/             # Jupyter notebooks for EDA & training
```

---


MLFLOW_TRACKING_URI=https://dagshub.com/byte-Shubham/mlproject.mlflow \
MLFLOW_TRACKING_USERNAME=byte-Shubham \
MLFLOW_TRACKING_PASSWORD=0b6224ec2652b639bef3e6f078456c41bd7eb3a1 \
python script.py