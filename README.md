# ⚡ CortexRCA – Automated Industrial IoT Root Cause Analysis System

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-1.30+-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-Vector%20Store-DC2626?style=flat)
![Groq](https://img.shields.io/badge/Groq-LLaMA--3.3-000000?style=flat)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Isolation%20Forest-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-success)
![Status](https://img.shields.io/badge/Status-Active-success)

---

# 📖 Overview

Industrial machinery failures can result in costly downtime, production delays, and increased maintenance expenses. Traditional diagnostic workflows often depend on manual inspection and experienced technicians, making root cause identification slow, inconsistent, and difficult to scale.

**CortexRCA** is a **local-first Industrial IoT Root Cause Analysis platform** that combines **Machine Learning**, **Retrieval-Augmented Generation (RAG)**, and **Large Language Models (LLMs)** to automate equipment diagnostics.

The platform continuously monitors industrial telemetry, detects abnormal operating conditions using **Isolation Forest**, retrieves relevant maintenance documentation from a **Qdrant vector database**, and generates explainable AI-powered root cause analyses with actionable maintenance recommendations using **Groq's LLaMA-3.3**.

Designed with privacy and reliability in mind, CortexRCA performs all telemetry processing and semantic retrieval locally, ensuring low latency, enhanced security, and zero operational data leakage.

---

# 🚨 Problem Statement

Modern industrial facilities generate massive amounts of telemetry data from sensors monitoring machinery health. While this data contains valuable insights, identifying the exact cause of equipment failures remains a major operational challenge.

Current maintenance workflows often suffer from:

- Unexpected equipment failures
- High operational downtime
- Manual troubleshooting processes
- Slow root cause identification
- Difficulty searching lengthy maintenance manuals
- Limited explainability of AI-driven diagnostics
- Reactive instead of predictive maintenance

These challenges increase maintenance costs while reducing production efficiency and equipment availability.

---

# 💡 Solution

CortexRCA combines anomaly detection, semantic search, and generative AI into a unified diagnostic workflow.

The platform:

- Continuously monitors industrial sensor telemetry
- Detects anomalous equipment behavior using machine learning
- Retrieves relevant technical documentation through semantic search
- Performs explainable root cause reasoning using an LLM
- Generates confidence-based maintenance recommendations
- Assists engineers with faster troubleshooting and decision-making

---

# ✨ Key Features

## 📊 Real-Time Telemetry Analytics

- Interactive Streamlit dashboard
- Live multi-sensor monitoring
- Plotly-based visualizations
- Statistical anomaly highlighting
- Equipment health indicators

---

## 🤖 Intelligent Anomaly Detection

Uses the **Isolation Forest** algorithm to identify abnormal operating behavior across multiple telemetry dimensions without requiring labeled failure data.

Supported sensor metrics include:

- Temperature
- Pressure
- Vibration

---

## 🔍 Retrieval-Augmented Generation (RAG)

Instead of relying solely on an LLM, CortexRCA first retrieves relevant maintenance manuals and technical documentation from a local **Qdrant Vector Database**.

Benefits include:

- Context-aware reasoning
- Reduced hallucinations
- Equipment-specific diagnostics
- Explainable AI outputs
- Higher diagnostic reliability

---

## 🧠 AI-Powered Root Cause Analysis

Groq's **LLaMA-3.3** analyzes:

- Sensor telemetry
- Anomaly characteristics
- Retrieved documentation
- Historical maintenance context

to generate:

- Root cause explanation
- Failure mechanism
- Confidence score
- Risk assessment
- Corrective maintenance actions

---

## 🛠 Maintenance Recommendations

The platform provides technicians with actionable maintenance guidance including:

- Inspection procedures
- Component replacement suggestions
- Repair priorities
- Preventive maintenance recommendations
- Operational safety considerations

---

## 🌐 Local-First Architecture

CortexRCA is designed to operate locally, ensuring:

- Zero telemetry data leakage
- Faster inference
- Offline capability
- Low-latency diagnostics
- Improved data privacy

---

## ⚡ Optimized Resource Management

Efficient Streamlit resource caching prevents:

- SQLite lock errors
- Qdrant directory conflicts
- Multi-session failures
- Repeated vector database initialization

This enables smooth operation even during rapid dashboard refreshes.

---

# 🏗 System Architecture

```text
                  +-----------------------------+
                  |    Sensor Telemetry Data    |
                  | (Temp, Vibration, Pressure) |
                  +--------------+--------------+
                                 |
                                 v
                     +-----------------------+
                     |   Isolation Forest    |
                     |  (Anomaly Detector)   |
                     +-----------+-----------+
                                 |
                     +-----------+-----------+
                     |                       |
                     v                       v
          +--------------------+   +-------------------+
          |  Plotly Dashboard  |   | Anomaly Detected  |
          | Visual Analytics   |   |   Risk Scoring    |
          +--------------------+   +---------+---------+
                                             |
                                             v
                                   +-------------------+
                                   | Qdrant Vector DB  |
                                   | Technical Manuals |
                                   +---------+---------+
                                             |
                                             v
                                   +-------------------+
                                   | Groq LLaMA-3.3    |
                                   | Reasoning Engine  |
                                   +---------+---------+
                                             |
                                             v
                                  +----------------------+
                                  | Root Cause Analysis  |
                                  | Maintenance Actions  |
                                  +----------------------+
```

---

# 🔄 Workflow

### **Step 1 — Telemetry Ingestion**

Industrial sensors continuously stream equipment telemetry including:

- Temperature
- Pressure
- Vibration

---

### **Step 2 — Anomaly Detection**

Isolation Forest analyzes incoming telemetry and computes anomaly scores.

High-risk operating conditions are automatically flagged.

---

### **Step 3 — Interactive Visualization**

The Streamlit dashboard displays:

- Live telemetry trends
- Equipment health metrics
- Risk indicators
- Highlighted anomalies

---

### **Step 4 — Context Retrieval**

Detected anomalies trigger semantic retrieval from the local Qdrant database.

Relevant documents include:

- Service manuals
- Equipment documentation
- Maintenance procedures
- Failure case descriptions

---

### **Step 5 — AI Reasoning**

Telemetry data and retrieved documentation are passed to Groq's LLaMA-3.3 model.

The LLM synthesizes both sources of information to perform explainable root cause analysis.

---

### **Step 6 — Diagnostic Report Generation**

The platform generates:

- Root cause explanation
- Failure mechanism
- Confidence percentage
- Corrective maintenance actions
- Recommended next steps

---

# 🛠 Technology Stack

| Category | Technology |
|------------|------------|
| Programming Language | Python 3.10+ |
| Dashboard Framework | Streamlit |
| Data Visualization | Plotly Express |
| Machine Learning | Scikit-Learn |
| ML Algorithm | Isolation Forest |
| Data Processing | Pandas & NumPy |
| Vector Database | Qdrant |
| Embedding Model | Sentence Transformers |
| LLM Inference | Groq API |
| Language Model | LLaMA-3.3 |
| Environment Management | python-dotenv |

---

# 🎯 Diagnostic Capabilities

### 🌡 Thermal Overheating Detection

Identifies abnormal temperature increases associated with:

- Bearing friction
- Cooling system failure
- Excessive mechanical resistance

---

### 📳 Vibration Analysis

Detects vibration signatures caused by:

- Shaft misalignment
- Rotor imbalance
- Bearing wear
- Structural looseness

---

### 📉 Pressure Monitoring

Detects abnormal pressure behavior including:

- Pressure surges
- Pressure drops
- Valve malfunction
- Seal leakage
- Pipeline blockage

---

### ⚙ Equipment Health Assessment

Combines multiple sensor readings to estimate:

- Equipment health
- Operational risk
- Failure severity
- Maintenance urgency

---

# 📈 Project Outcomes

CortexRCA significantly improves industrial maintenance workflows by:

- Reducing diagnostic time from hours to seconds
- Automating root cause analysis
- Improving equipment uptime
- Delivering explainable AI-assisted diagnostics
- Reducing dependency on manual troubleshooting
- Accelerating maintenance decision-making
- Enhancing operational safety
- Providing consistent maintenance recommendations

---

# 📂 Project Structure

```text
CortexRCA/
│
├── app.py
├── requirements.txt
├── README.md
├── LICENSE
├── .gitignore
├── .env.example
│
├── assets/
│   ├── dashboard.png
│   ├── architecture.png
│   └── rca_output.png
│
├── data/
│   ├── telemetry.csv
│   └── manuals/
│
├── models/
│   └── isolation_forest.pkl
│
├── rag/
│   ├── ingest.py
│   ├── retrieve.py
│   └── embeddings.py
│
├── utils/
│   ├── preprocessing.py
│   ├── anomaly_detection.py
│   └── llm.py
│
└── qdrant_db/
```

---

# 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/Suhhas003/CortexRCA.git
```

Navigate to the project directory:

```bash
cd CortexRCA
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment:

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# ⚙ Configuration

Create a `.env` file in the project root.

```env
GROQ_API_KEY=your_groq_api_key
QDRANT_PATH=./qdrant_db
```

---

# ▶ Usage

Launch the Streamlit application:

```bash
streamlit run app.py
```

The application will:

- Load telemetry data
- Detect equipment anomalies
- Retrieve relevant maintenance documentation
- Generate AI-powered root cause analyses
- Display maintenance recommendations through an interactive dashboard

---

# 🔮 Future Enhancements

- 📡 Live MQTT sensor integration
- ⚡ Apache Kafka streaming support
- 📈 Predictive maintenance using LSTM and Transformer models
- 📊 Remaining Useful Life (RUL) prediction
- 🔔 Slack and Microsoft Teams alert integration
- 📱 Mobile-responsive technician dashboard
- ☁ Docker and Kubernetes deployment
- 🤖 Multi-Agent AI maintenance workflows
- 📄 Automated PDF maintenance reports
- 📊 Historical trend analytics
- 🌍 Multi-equipment fleet monitoring
- 📈 Digital Twin integration for industrial assets

---

# 👨‍💻 Author

**Suhas Dongre**

B.Tech Computer Engineering  
Ramrao Adik Institute of Technology (RAIT)

**GitHub:** https://github.com/Suhhas003

---

# 🤝 Acknowledgements

This project leverages several outstanding open-source technologies:

- Streamlit
- Plotly
- Scikit-Learn
- Qdrant
- Groq
- Sentence Transformers
- Pandas
- NumPy

Their contributions have made the development of CortexRCA possible.

---

# 📄 License

This project is distributed under the **MIT License**.

See the `LICENSE` file for more information.

---

## ⭐ Project Summary

**CortexRCA** demonstrates how **Machine Learning**, **Retrieval-Augmented Generation (RAG)**, and **Large Language Models (LLMs)** can be combined to build an intelligent Industrial IoT diagnostic system capable of delivering **real-time anomaly detection**, **explainable root cause analysis**, and **actionable maintenance recommendations** while preserving data privacy through a **local-first architecture**.

If you found this project interesting, consider giving it a ⭐ on GitHub.
