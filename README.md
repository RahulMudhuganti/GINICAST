# GINICAST  
### A Machine Learning Approach to Modeling and Forecasting Income Inequality

---

## 📌 Project Overview
**GINICAST** is a Java-based machine learning application designed to preprocess economic data, train a multilayer neural network, and visualize prediction results through a JavaFX graphical user interface (GUI).

The system integrates:
- CSV data preprocessing (cleaning and normalization)
- Neural network training and testing
- A multi-scene JavaFX GUI for end-to-end interaction

This README is intended to guide the **professor/evaluator** on how to navigate, execute, and understand the project.

---

## 🗂️ Project Directory Structure

GINICAST/
│
├── gui/
│ └── pnw/ginicast/
│ ├── PrimaryController.java
│ ├── primary.fxml
│ ├── training.fxml
│ ├── normalizing.fxml
│ ├── trainingprocess.fxml
│ ├── trainingcompleted.fxml
│ ├── starttesting.fxml
│ ├── testingprocess.fxml
│ ├── testingresults.fxml
│ └── images/
│
├── normalizingCSV/
│ ├── CSVReader.java
│ ├── RemoveRows.java
│ ├── Cleaning.java
│ ├── Outliers.java
│ └── Normalizer.java
│
├── neuralNetwork/
│ ├── Main.java
│ ├── NeuralNetwork.java
│ ├── NormalizedDataCSVReader.java
│ └── TestingTrainingSet.java
│
├── models/
│ └── (saved trained model files)
│
├── data/
│ └── input CSV datasets
│
├── documentation/
│ ├── SRS.docx
│ ├── User_Manual.docx
│ └── Presentation.pptx
│
└── README.md

yaml
Copy code

---

## ⚙️ Software & Environment Requirements
- **Java JDK 17**
- **IntelliJ IDEA**
- **JavaFX SDK (compatible with JDK 17)**
- Operating System: Windows / macOS / Linux

---

## 🚀 How to Run the Application

### Step 1: Open Project
1. Launch **IntelliJ IDEA**
2. Click **Open**
3. Select the **GINICAST project root folder**
4. Ensure **JDK 17** is configured:
   - `File → Project Structure → SDK`

---

### Step 2: Run the GUI
The entire system is executed through the GUI.

**Main Controller File**
gui/pnw/ginicast/PrimaryController.java

markdown
Copy code

**FXML Entry Scene**
primary.fxml

yaml
Copy code

Run the project using a **JavaFX Application configuration**.

---

## 🧭 Application Workflow (For Professor)

### 1️⃣ Import Dataset
- On the home screen, click **Import CSV**
- Select an economic dataset (CSV file)

Example:
data/inflation_data.csv

yaml
Copy code

---

### 2️⃣ Configure Neural Network
- Enter:
  - Number of nodes
  - Learning rate
  - Training/Testing split
- Click **Start Training**

---

### 3️⃣ Data Normalization (Automatic)
The system automatically performs:
- Removal of invalid rows
- Handling missing values (KNN-based)
- Outlier detection and removal
- Min–Max normalization (0–1 range)

Progress is displayed in the GUI.

📂 Implemented in:
normalizingCSV/

yaml
Copy code

---

### 4️⃣ Model Training
- Neural network is trained using normalized data
- Epoch progress is displayed
- Training completes automatically

📂 Core logic:
neuralNetwork/NeuralNetwork.java

yaml
Copy code

⚠️ **Note:** Results may vary between runs due to random weight initialization (expected behavior).

---

### 5️⃣ Model Testing & Results
- Model is tested on unseen data
- Displays:
  - Accuracy
  - MSE
  - RMSE
- Results are visualized in the GUI

---

## 🧠 Core Modules Description

### 📁 `normalizingCSV/`
| File | Description |
|----|----|
| CSVReader.java | Reads raw CSV files |
| RemoveRows.java | Removes invalid or incomplete rows |
| Cleaning.java | Handles missing values using KNN |
| Outliers.java | Detects and removes statistical outliers |
| Normalizer.java | Normalizes values to range 0–1 |

---

### 📁 `neuralNetwork/`
| File | Description |
|----|----|
| Main.java | Standalone test runner (optional) |
| NeuralNetwork.java | Multilayer neural network implementation |
| TestingTrainingSet.java | 70/30 data split |
| NormalizedDataCSVReader.java | Reads normalized dataset |

---

## 💾 Saved Models
- Trained models are stored in:
models/

yaml
Copy code
- Models can be reused during testing.

---

## 📄 Documentation
Located in:
documentation/

yaml
Copy code

Includes:
- Software Requirements Specification (IEEE)
- User & Technical Manual
- Final Presentation (PPT)

---

## 🧪 Testing Summary
- Manual and functional testing performed
- Tested with real economic datasets
- Edge cases (missing values, outliers) handled

---

## 🔮 Future Enhancements
- Fixed random seed for reproducibility
- Advanced graphing (ChartFX)
- Export predictions to file
- Executable (.exe) packaging

---

## 🎓 Academic Context
This project was developed as part of a **Software Engineering course**, following:
- IEEE documentation standards
- Modular and layered architecture
- Client-driven requirements

---

## ✅ Recommended Evaluation Steps
1. Review README.md
2. Review SRS and Manual
3. Run GUI
4. Import CSV
5. Execute full pipeline
6. Review outputs and results

---

**End of README**
