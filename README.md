# ITEC5020-Capella-Select-AI-Model

Research and Selection of AI Models for Hypotify Clinical Insights Bot

ITEC 5020/5025: AI Model Selection Research (Week 9)

Overview

This repository includes the final research paper detailing the Artificial Intelligence (AI) architecture selected for the Hypotify Clinical Insights Bot. This selection phase bridges the foundational database work (ITEC 5020) with the application development (ITEC 5025).

The paper justifies the choice of a dual-model system specifically engineered to run effectively and reliably on the structured MySQL EMR database committed to this repository.

📄 Key Deliverable

File: WEEK9.pdf (The full 4–5 page research paper on model selection)

Core AI Architecture

The research paper proposes and justifies two distinct AI models, each addressing a critical function of the chatbot interface:

AI Task

Model Selected

Rationale

Libraries (Implementation in ITEC 5025)

1. User Interface / Querying

Text-to-SQL Model (Fine-Tuned LLM/BERT)

Purpose: Translates complex natural language questions into precise, executable SQL queries against the structured EMR database.

Hugging Face Transformers, SQLAlchemy

2. Predictive Analysis

Gradient Boosting Machine (GBM) (e.g., XGBoost)

Purpose: Runs high-accuracy classification (risk prediction) on the retrieved patient cohort data. Optimized for high-performance on tabular data.

Scikit-learn, XGBoost

Alignment with Database (ITEC 5020)

The model selection confirms the necessity and success of the database design:

Integrity: The AI models rely entirely on the 3NF normalization of the MySQL schema. The clean, predictable structure is essential for the ML model's accuracy.

Ethical Basis: All models are designed to be trained and run against the synthetic EMR dataset, ensuring compliance with ethical standards by eliminating PII/HIPAA risks.

📚 Next Steps (ITEC 5025)

The research detailed in this document dictates the work pipeline for the next course, focusing on developing the Python modules to:

Interface with the MySQL database using libraries like SQLAlchemy.

Build the data processing pipeline using Scikit-learn.

Implement and integrate the selected Text-to-SQL and GBM models into the final chatbot application.
