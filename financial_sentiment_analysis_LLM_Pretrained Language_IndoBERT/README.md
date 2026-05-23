# 📈 Financial News Sentiment Classification using Traditional NLP and Transformer-Based Language Models

## 🚀 Overview

This project develops and compares multiple Natural Language Processing (NLP) approaches for sentiment classification of Indonesian-language financial news headlines.

The goal is to analyze how effectively traditional machine learning methods and modern Transformer-based language models can understand sentiment in non-English, finance-specific text.

The project compares:
- TF-IDF + Logistic Regression
- Embedding + Bidirectional LSTM (BiLSTM)
- Fine-tuned IndoBERT Transformer model

The results show that Transformer-based language models significantly outperform traditional NLP approaches in understanding contextual and semantic meaning in Indonesian financial news.

---

# 💼 Business Problem

Financial markets are highly influenced by news sentiment. Traders, analysts, and algorithmic trading systems increasingly use NLP and machine learning techniques to analyze investor sentiment and market reactions.

In Indonesia, financial sentiment analysis for Indonesian-language financial news remains relatively underdeveloped. This project explores how modern NLP and Transformer-based models can support sentiment analysis for Indonesian stock market news.

---

# 🎯 Target Audience

This project is relevant for:
- Indonesian stock market traders
- Financial analysts
- Quantitative researchers
- AI/ML teams building financial intelligence systems

The project demonstrates how NLP and LLM techniques can be applied to non-English, domain-specific financial text.

---

# 📦 Dataset

### Source
CNBC Indonesia Stock News Sentiment Dataset (Kaggle)

Dataset Link:  
https://www.kaggle.com/datasets/triagungj/cnbc-indonesia-stock-news-sentiment-dataset

---

## Dataset Description

The dataset contains:
- 9,819 Indonesian financial news headlines
- Published between January 2024 – March 2025
- Manually labeled into:
  - Positive
  - Neutral
  - Negative sentiment

Class distribution:
- Neutral: 4,356
- Negative: 2,887
- Positive: 2,576

---

# 🧹 Data Preparation

Preprocessing steps included:
- Lowercasing text
- Removing punctuation and symbols
- Cleaning extra spaces
- Removing empty rows
- Encoding sentiment labels:
  - 0 = negative
  - 1 = neutral
  - 2 = positive

Dataset split:
- 70% training
- 15% validation
- 15% test

---

# 🧠 Methodology

The project compares three NLP modeling approaches:

| Model | Type |
|---|---|
| TF-IDF + Logistic Regression | Classical NLP baseline |
| Embedding + BiLSTM | Neural sequence model |
| Fine-tuned IndoBERT | Transformer-based language model |

The workflow includes:
1. Data loading and preprocessing
2. Feature preparation
3. Baseline classical NLP model
4. Neural sequence model
5. Transformer-based model fine-tuning
6. Performance comparison using:
   - Accuracy
   - Macro F1 score
   - Confusion matrices

---

# ⚙️ Tools & Technologies

- Python
- pandas / numpy
- scikit-learn
- TensorFlow / Keras
- Hugging Face Transformers
- PyTorch
- IndoBERT
- Matplotlib / Seaborn

---

# 📊 Model Performance

## Accuracy Comparison

| Model | Accuracy |
|---|---|
| TF-IDF + Logistic Regression | ~80% |
| Embedding + BiLSTM | ~80% |
| Fine-tuned IndoBERT | **87.6%** |

The fine-tuned IndoBERT model achieved the highest accuracy, significantly outperforming both traditional and neural baseline approaches.

---

# 📈 Macro F1 Comparison

| Model | Macro F1 |
|---|---|
| TF-IDF + Logistic Regression | 0.803 |
| Embedding + BiLSTM | 0.789 |
| Fine-tuned IndoBERT | **0.876** |

Macro F1 was used to evaluate balanced performance across all sentiment classes.

The Transformer-based IndoBERT model achieved the strongest balanced classification performance, including minority sentiment classes.

---

# 🔍 Confusion Matrix Analysis

The confusion matrices show that IndoBERT achieved the highest number of correct predictions across all three sentiment categories:
- Negative classification improved from ~306 to 341 correct predictions
- Neutral classification improved from ~533 to 567
- Positive classification improved from ~349 to 383

IndoBERT also significantly reduced severe misclassification errors, especially:
- Positive headlines incorrectly predicted as negative

This demonstrates the Transformer model’s stronger ability to capture contextual meaning compared to bag-of-words or sequential neural approaches.

---

# 🧠 Key Insights

### 1. Transformer models outperform traditional NLP
IndoBERT significantly outperformed both TF-IDF and BiLSTM models across all evaluation metrics.

### 2. Financial headlines contain strong keyword signals
Interestingly, TF-IDF + Logistic Regression slightly outperformed the BiLSTM model, suggesting many financial headlines contain strong keyword patterns that simpler models can capture effectively.

### 3. Financial sentiment is context-sensitive
Many prediction errors occurred because financial headlines are often ambiguous without full article context.

Examples:
- Neutral headlines containing emotionally negative words such as:
  - “korupsi”
  - “utang”
  - “KPK”

were frequently predicted as negative despite being neutral.

---

# ⚠️ Limitations

- Only headlines were analyzed instead of full articles
- Dataset limited to CNBC Indonesia
- Market sentiment often requires broader context and interpretation
- Observational sentiment analysis should not be used as a standalone trading signal

The project emphasizes that sentiment analysis should support—not replace—human financial judgment.

---

# 🚀 Future Improvements

Potential future improvements include:
- Using full article text instead of headlines
- Increasing labeled financial data volume
- Developing finance-specific Indonesian language models
- Improving understanding of implicit financial sentiment and cultural context

These improvements could reduce confusion between neutral, positive, and negative sentiment classes.

---

# 💡 Business Impact

This project demonstrates how Transformer-based NLP systems can support:
- Financial sentiment monitoring
- Trading intelligence systems
- News-driven market analytics
- Risk monitoring
- Automated market research

The project also highlights the importance of domain-specific language understanding for non-English financial markets.

---

# 📂 Project Structure

```text
03_financial-news-sentiment/
├── README.md
├── financial_news_sentiment_model.ipynb
├── project_report.pdf
├── model_accuracy_comparison.png
├── macro_f1_comparison.png
├── confusion_matrix_comparison.png
