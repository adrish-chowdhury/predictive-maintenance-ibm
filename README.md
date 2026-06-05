# 🔧 Predictive Maintenance AI Assistant

## Project Overview
AI-powered predictive maintenance system for industrial machinery built using IBM Cloud, Langflow, and Machine Learning. The system predicts machine failures before they occur using real-time sensor data.

## Problem Statement No. 39
Develop a predictive maintenance model for a fleet of industrial machines to anticipate failures before they occur by analyzing sensor data to identify patterns that precede a failure.

## Tech Stack
- **IBM Watson Studio** - Model training and development
- **IBM watsonx.ai** - LLM (meta-llama/llama-3-3-70b-instruct)
- **Langflow** - AI workflow builder
- **Python** - scikit-learn, pandas, joblib, numpy
- **Random Forest Classifier** - ML model

## Dataset
[Kaggle - Machine Predictive Maintenance Classification](https://www.kaggle.com/datasets/shivamb/machine-predictive-maintenance-classification)

## Failure Types Predicted
| Code | Failure Type |
|------|-------------|
| 0 | Heat Dissipation Failure |
| 1 | No Failure |
| 2 | Overstrain Failure |
| 3 | Power Failure |
| 4 | Random Failure |
| 5 | Tool Wear Failure |

## Architecture
```
User Input (Sensor Values)
        ↓
Langflow Chat Interface
        ↓
IBM watsonx.ai LLM (Extracts JSON from natural language)
        ↓
Predict Failure (Random Forest Model)
        ↓
Map Failure (Integer → Failure Name)
        ↓
Recommend (Generate Maintenance Report)
        ↓
Chat Output
```

## Project Structure
```
predictive-maintenance/
├── notebook/
│   └── predictive_maintenance.ipynb
├── model/
│   └── predictive_maintenance_model.pkl
├── langflow/
│   └── predictive_maintenance_flow.json
├── requirements.txt
└── README.md
```

## How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/YourUsername/predictive-maintenance-ibm.git
cd predictive-maintenance-ibm
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Install and Run Langflow
```bash
pip install langflow
langflow run
```

### 4. Import Flow
- Open http://localhost:7860
- Import `langflow/predictive_maintenance_flow.json`

### 5. Configure IBM watsonx
- Add your IBM watsonx API Key
- Add your Project ID
- Select model: `meta-llama/llama-3-3-70b-instruct`

### 6. Place Model File
```bash
cp model/predictive_maintenance_model.pkl .
```

### 7. Test in Playground
Open Playground and type:
```
Machine Type: M, Air Temperature: 298 K, Process Temperature: 308 K, RPM: 1500, Torque: 45 Nm, Tool Wear: 200 min
```

## Sample Output
```
========================================
        MACHINE HEALTH REPORT
========================================

  Failure Type : No Failure
  Risk Level   : LOW
  Status       : MACHINE HEALTHY

  Action       : Machine healthy. Continue monitoring.

  Powered by IBM Cloud + Langflow
========================================
```

## Features
- Natural language input for sensor values
- Real-time failure prediction using trained ML model
- Maintenance recommendations based on failure type
- Risk level assessment (LOW / MEDIUM / HIGH)
- IBM Cloud integration

## Model Performance
- Algorithm: Random Forest Classifier
- Features: Type, Air Temperature, Process Temperature, RPM, Torque, Tool Wear, Temperature Difference, Power, Wear Rate

## Author
**Adrish Chowdhury**
IBM AICTE Internship Project - Mechanical Engineering (Machine Learning)

## License
MIT License
