Financial News in Indonesian Language Sentiment Classification Using Traditional NLP Approaches and Modern Transformer-Based Language Models

Abstract

Financial markets are highly influenced by news sentiment, and traders, analysts, and automated trading systems increasingly rely on Natural Language Processing (NLP) techniques to understand market reactions and investor sentiment. In Indonesia, financial news sentiment analysis remains relatively underdeveloped, particularly for Indonesian-language financial text. This project develops and evaluates an Indonesian financial news sentiment classification system using both traditional NLP approaches and modern Transformer-based language models. This project demonstrates and compares the performance between traditional NLP models and modern transformer-based LLM on non-english language specific-industry language, specifically Indonesian-language financial text.

The project uses the CNBC Indonesia Stock News Sentiment Dataset, which contains 9,819 Indonesian financial news headlines manually labeled into three sentiment categories: positive, neutral, and negative. The dataset includes a broad range of market-related news and provides a realistic benchmark for financial sentiment classification in Indonesian language.

To study the effectiveness of different NLP approaches, three models were implemented and compared. First, a TF-IDF + Logistic Regression model was used as a classical machine learning baseline. Second, an Embedding + Bidirectional LSTM (BiLSTM) neural network model was implemented to capture sequential text patterns. Finally, a Transformer-based Large Language Model approach was developed by fine-tuning IndoBERT using the Hugging Face Transformers framework in Python. Afterwards, the project compares the performance across the three models.

The results show that the fine-tuned IndoBERT model significantly outperformed the traditional and BiLSTM models across all evaluation metrics. IndoBERT achieved approximately 87.6% accuracy and 0.876 macro F1 score, compared to approximately 80% performance from the TF-IDF and BiLSTM approaches. The findings suggest that Transformer-based language models are more effective for Indonesian financial sentiment analysis because they better capture contextual and semantic meaning compared to bag-of-words or sequential neural approaches. However, there are still works needed on emotionally charged words, such as corruption and loan. IndoBERT still has difficulties understanding the context and sentiment in the presence of emotionally charged words.
Problem Statement
Financial markets react strongly to news sentiment. Traders, analysts, and automated trading systems increasingly use NLP and LLM methods to quantify news sentiment and integrate it into trading or risk-monitoring workflows. In Indonesia, financial market news sentiment analysis is not yet widely available due to the lag of market and technology sophistication in the market. 
Target Audience
The target audience are traders and analysts, specifically, for the Indonesian stock market. This project is to help explore the usage of LLM for financial news sentiment analysis. This project will explore the usage of classical NLP methods to more modern Transformer-based Language Models and compare the efficacy for non-English texts and industry-specific terms, namely financial texts in Indonesian language.
Dataset Description
This dataset contains 9,819 Indonesian stock market news headlines published on CNBC Indonesia under the "Market" category from January 1, 2024 to March 31, 2025. Each headline has been manually labeled with one of three sentiment classes: positive, neutral, or negative. The dataset is obtained from Kaggle (https://www.kaggle.com/datasets/triagungj/cnbc-indonesia-stock-news-sentiment-dataset). 



The datasets contained 4,356 neutral, 2,887 negative and 2,576 positive stock news in Indonesian language.

For preprocessing, this project cleaned up the texts and labeled sentiment. Text was converted to lowercase so abbreviations are treated equally, then symbols and punctuations were removed. Extra spaces were reduced to a single space. Empty texts were removed. Sentiments are labeled as 0: negative, 1: neutral, 2: positive.



For data split, this project used 70% training, 15% validation, and 15% test.
Methodology
For this project, I used the classical model TF–IDF + logistic regression for the baseline model, sequence model Embedding + Bidirectional LSTM (BiLSTM) for the neural model and lastly LLM Transformer-based language models, IndoBERT. After that, I compared their performances by analyzing the accuracy and confusion matrices.


Installation & Configuration
I started by setting the necessary library below.

I continued with loading and preparing the datasets, continued by training and testing the classical model as baseline, neural model and LLM model. Then, I compared the accuracies, macro F1 and confusion matrices.
Results



The results show that the fine-tuned IndoBERT model achieved the highest accuracy at 87.6%, outperforming both TF-IDF + Logistic Regression and Embedding + BiLSTM, which achieved around 80% accuracy. This suggests that Transformer-based language models are more effective at understanding Indonesian financial news because they can better capture context and semantic meaning.
Interestingly, the TF-IDF + Logistic Regression baseline slightly outperformed the BiLSTM model. This indicates that many financial headlines contain strong keyword patterns, allowing simpler models to remain competitive despite their lower complexity.



To address the class imbalance, this project looked into macro F1 scores. The Macro F1 results show that fine-tuned IndoBERT achieved the best balanced performance across all sentiment classes with a Macro F1 score of 0.876. In comparison, TF-IDF + Logistic Regression achieved 0.803 while Embedding + BiLSTM achieved 0.789. A higher Macro F1 score means the model performs more consistently across all sentiment categories, not just the majority class. This indicates that the Transformer-based model was better at handling all three sentiment categories more consistently, including minority classes, rather than mainly optimizing for the largest class. 



The confusion matrices show that fine-tuned IndoBERT makes the most correct predictions across all three classes. It improves negative classification from 306/307 correct to 341 correct, neutral from 533/545 to 567 correct, and positive from 349/322 to 383 correct.

IndoBERT also reduces the most serious errors. For example, positive headlines wrongly predicted as negative drop from 28 in TF-IDF and 60 in BiLSTM to only 14 in IndoBERT. Overall, the Transformer model is better at separating positive, neutral, and negative sentiment, while TF-IDF and BiLSTM make more confusion between neutral and the two sentiment classes.
Conclusion
The results show that the fine-tuned IndoBERT model significantly outperformed the traditional and BiLSTM models across all evaluation metrics. IndoBERT achieved approximately 87.6% accuracy and 0.876 macro F1 score, compared to approximately 80% performance from the TF-IDF and BiLSTM approaches. The findings suggest that Transformer-based language models are more effective for Indonesian financial text sentiment analysis because they better capture contextual and semantic meaning compared to bag-of-words or sequential neural approaches.
Future Improvement

IndoBERT made mistakes mainly because many financial headlines are ambiguous without reading the full article. Neutral news containing words like korupsi, utang, or KPK were often predicted as negative because those words sound emotionally negative. On the other hand, some neutral company news was predicted as positive because the headlines sounded beneficial for business or investors.

The model also struggled with positive sentiment that was implied indirectly. Headlines about Fed rate cuts, BUMN contributions, or BRImo services may look neutral on the surface but are considered positive in financial markets. Overall, IndoBERT understands Indonesian language well, but financial sentiment is harder because many headlines require market context and interpretation.

Future improvements could focus on reducing misclassification caused by ambiguous financial headlines. Many errors occurred because short headlines often lack enough context and may contain emotionally strong words that do not always reflect the actual sentiment. Using the full article text instead of only headlines, increasing the amount of labeled financial data, and applying domain-specific financial language models could help the model better understand cultural context, subtle market sentiment and reduce confusion between neutral, positive, and negative classes.

Reflection
One limitation of this project is that the models only analyze short financial news headlines rather than full news articles, which can reduce contextual understanding and lead to sentiment misclassification. In addition, the dataset is limited to CNBC Indonesia financial news, so the models may not generalize well to other Indonesian news sources, social media content, or future market conditions.

As a financial trader or analyst, sentiment analysis should not be used as a sole-source of decision-making. Therefore, the model should be used as a supporting analytical tool rather than a standalone decision-making system, and human judgment should remain part of the investment process.


References
Tri Agung J. (2025). CNBC Indonesia Stock News Sentiment Dataset. 
Kaggle.https://www.kaggle.com/datasets/triagungj/cnbc-indonesia-stock-news-sentiment-dataset
