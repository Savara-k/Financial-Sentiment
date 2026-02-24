# Financial-Sentiment

An end-to-end NLP pipeline designed to analyze financial news headlines in real-time. By leveraging three distinct transformer architectures, the system provides a 360-degree view of market signals, moving from raw text to structured sentiment, entity recognition, and generative forecasting.

---
## Overview

In the fast-paced world of finance, raw data is a liability—processed intelligence is the asset. this project is a sophisticated NLP ecosystem designed to transform unstructured financial headlines into structured, actionable market signals.

This project demonstrates my ability to architect a multi-model pipeline that balances specialized domain accuracy with generative flexibility. By integrating FinBERT, BERT-NER, and GPT-2, the system moves beyond simple classification to provide a comprehensive "Analyst's View" of any market event.

echnical Architecture & Decision Making My analytical approach focused on three critical pillars: Domain Precision, Contextual Awareness, and Generative Synthesis.

Supervised Sentiment Fine-Tuning (The Foundation) Generic sentiment models often fail in financial contexts (e.g., the word "crashing" is negative for a stock but potentially positive for a short-seller).

## Model Selection: 
   - Utilized ProsusAI/finbert as the backbone, leveraging its pre-training on the Financial PhraseBank.


## Addressing Data Imbalance: 
   - Recognizing the "Neutral" class bias in financial news, I implemented Weighted Cross-Entropy Loss. I computed class weights (Neg: 2.67, Neu: 0.56, Pos: 1.18) to ensure the model didn't ignore critical negative signals.


## Results: 
    - Achieved a Final Test Accuracy of 85.5% with a particularly strong recall for Negative (0.93) and Positive (0.88) classes.

Specialized NER Extraction (The Context) Data is meaningless without entities. I integrated a Large-Cased BERT-NER model to extract Organizations (ORG) and Locations (LOC). This allows businesses to not just know what is being said, but exactly who it affects and where the impact is centered.

Generative Market Outlook (The Insight) To bridge the gap between data and strategy, I utilized GPT-2 to generate synthetic "Analyst Commentaries". This provides a narrative layer that interprets the sentiment and entities into a cohesive market outlook.

---

## Business Impact & Use Cases

Risk Mitigation: Real-time detection of negative sentiment regarding specific organizations, allowing for rapid hedging or exit strategies.

Alpha Generation: Identifying positive signals in niche locations or emerging sectors before they hit mainstream reporting.

Automated Summarization: Reducing the cognitive load on analysts by distilling complex headlines into three structured data points: Sentiment, Entities, and Forecast.

---

## Technical Stack

* Engineering: Python, PyTorch, Hugging Face Transformers.

* Data Science: Scikit-learn (Weighted Loss, Metrics), Pandas, NumPy.

* Deployment: Gradio (Interactive Dashboard for Stakeholder Review).

* Hardware: Optimized for CUDA-enabled GPU environments (T4).
