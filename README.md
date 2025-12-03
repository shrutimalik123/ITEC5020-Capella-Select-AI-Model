# 🏥 Hypotify Clinical Insights Bot
### AI Model Selection & Architecture Research (ITEC 5020/5025)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange?style=for-the-badge&logo=mysql&logoColor=white)
![Machine Learning](https://img.shields.io/badge/AI%2FML-XGBoost%20%7C%20Transformers-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Research%20Complete-success?style=for-the-badge)

---

## 📖 Overview

**Hypotify Clinical Insights Bot** is an advanced AI-driven system designed to bridge the gap between structured Electronic Medical Records (EMR) and actionable clinical intelligence. This repository contains the definitive research and architectural decisions for the system's AI core, bridging the foundational database design (ITEC 5020) with the upcoming application development (ITEC 5025).

The system employs a **Dual-Model Architecture** specifically engineered to run reliably on a 3NF normalized MySQL database, ensuring data integrity while delivering high-accuracy predictive insights.

## 📂 Key Deliverables

| Resource | Description | Access |
| :--- | :--- | :---: |
| **Research Paper** | Full 4–5 page analysis of model selection, rationale, and implementation strategy. | [📄 View PDF](./WEEK9.pdf) |
| **Presentation** | Executive summary slides covering the problem, solution, and technical architecture. | [📊 View Slides](https://docs.google.com/presentation/d/1ic1YDwGli7wBW9j_UWFrOegbxu89KGYOt8L9FycFzMg/edit?usp=sharing) |

---

## 🏗️ System Architecture

The solution integrates two distinct AI components to handle natural language querying and clinical risk assessment independently but cohesively.

```mermaid
graph TD
    User[👤 Clinician] -->|Natural Language Query| NLP[🗣️ NLP Interface]
    NLP -->|Generates SQL| DB[(🗄️ MySQL EMR Database)]
    
    subgraph "AI Core"
        NLP[Text-to-SQL Model<br/>(Fine-Tuned LLM/BERT)]
        Pred[Predictive Model<br/>(Gradient Boosting)]
    end
    
    DB -->|Retrieved Patient Data| Pred
    Pred -->|Risk Score / Classification| Insight[💡 Clinical Insight]
    Insight --> User
```

### 🧠 Dual-Model Strategy

#### 1. Natural Language Interface (Querying)
*   **Model:** Text-to-SQL (Fine-Tuned LLM / BERT-based)
*   **Role:** Translates complex clinical questions (e.g., *"Show me all patients with hypertension under 40"*) into precise, executable SQL queries.
*   **Rationale:** Eliminates the need for clinicians to learn SQL while leveraging the strict schema of the EMR for 100% accurate data retrieval.
*   **Tech:** Hugging Face Transformers, SQLAlchemy.

#### 2. Clinical Predictive Analysis
*   **Model:** Gradient Boosting Machine (GBM) / XGBoost
*   **Role:** Performs high-performance classification and risk prediction on the tabular data retrieved from the EMR.
*   **Rationale:** GBMs are state-of-the-art for structured/tabular data, offering superior performance and interpretability compared to deep learning for this specific data type.
*   **Tech:** Scikit-learn, XGBoost.

---

## 🛠️ Technical Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Language** | ![Python](https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white) | Core application logic and ML pipelines. |
| **Database** | ![MySQL](https://img.shields.io/badge/-MySQL-4479A1?logo=mysql&logoColor=white) | Structured storage of EMR data (3NF Normalized). |
| **ML Framework** | ![Scikit-learn](https://img.shields.io/badge/-Scikit--learn-F7931E?logo=scikit-learn&logoColor=white) | Data preprocessing and model evaluation. |
| **Boosting** | ![XGBoost](https://img.shields.io/badge/-XGBoost-EB4C42) | High-performance gradient boosting for risk prediction. |
| **NLP** | ![Hugging Face](https://img.shields.io/badge/-Hugging%20Face-FFD21E?logo=huggingface&logoColor=black) | Pre-trained models for Text-to-SQL tasks. |

---

## 🛡️ Data Engineering & Ethics

### Database Integrity
The AI models rely entirely on the **Third Normal Form (3NF)** schema of the MySQL database. This clean, predictable structure is critical for:
*   Minimizing data redundancy.
*   Ensuring consistent query generation by the NLP model.
*   Providing high-quality structured features for the predictive model.

### Ethical Compliance
*   **Synthetic Data:** All models are trained and validated against a synthetic EMR dataset.
*   **Privacy:** No PII (Personally Identifiable Information) or real PHI (Protected Health Information) is used, ensuring full HIPAA compliance during development and testing.

---

## 🚀 Development Roadmap (ITEC 5025)

The research in this repository sets the stage for the implementation phase.

- [ ] **Database Interface:** Implement `SQLAlchemy` ORM for secure DB communication.
- [ ] **Data Pipeline:** Build preprocessing pipelines using `pandas` and `scikit-learn`.
- [ ] **Model Implementation:**
    - [ ] Integrate Text-to-SQL model for query generation.
    - [ ] Train and deploy XGBoost model for risk analysis.
- [ ] **Application Integration:** Combine modules into the final **Hypotify** chatbot interface.
