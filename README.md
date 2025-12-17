# EC523 Project — RoBERTa-based Sentiment Extraction  

---

## 📘 Project Overview
This project implements a **Transformer-based (RoBERTa)** text sentiment extraction system.  
Given a tweet and its overall sentiment label (positive / neutral / negative), the model extracts the specific substring that best represents that sentiment.

The task is equivalent to **Kaggle’s Tweet Sentiment Extraction** challenge, with the main objective of minimizing the **Jaccard similarity gap** between the predicted and ground truth substrings.

---

## 🧠 Model Architecture
- **Base Model:** [`cardiffnlp/twitter-roberta-base-sentiment`](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment)  
- **Encoder:** RoBERTa Transformer  
- **Decoder:** Two linear layers predicting the start and end indices of the target span  
- **Loss Function:** `CrossEntropyLoss(start_logits, start_labels) + CrossEntropyLoss(end_logits, end_labels)`  
- **Evaluation Metric:** Jaccard similarity  

**Input:**  
> Sentiment + Text  

**Output:**  
> Start index, End index → Extracted Substring

---

update:
ec523largejacloss includes all the code related to roberta and loss funtions. 
523lstm includes code related to lstm.
