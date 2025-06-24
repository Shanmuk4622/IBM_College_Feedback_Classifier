# 📝 Legal Sentiment Analysis using IBM Watsonx.ai

## 📌 Project Overview

The **Legal Sentiment Analysis** project is an AI-powered system designed to classify legal or general text data into sentiment categories such as **Positive**, **Negative**, and **Neutral**. Leveraging IBM Watsonx foundation models and prompt engineering, this project enables organizations to extract actionable sentiment insights from unstructured text, supporting better decision-making in legal, business, or customer feedback contexts.

---

## 🎯 Objectives

- Automatically analyze and classify text sentiment using large language models.
- Organize feedback or legal statements into Positive, Negative, or Neutral categories.
- Generate sentiment-based insights for reports and analytics.
- Leverage IBM Watsonx Foundation Models with few-shot prompting for robust results.

---

## 🛠️ Tools & Technologies

| Component            | Technology                          |
|----------------------|--------------------------------------|
| Programming Language | Python                              |
| AI Model             | IBM Watsonx Foundation Model (FLAN-T5 / Mistral) |
| Cloud Platform       | IBM Cloud                           |
| Data Format          | CSV                                 |
| Prompting            | Few-shot Prompt Engineering         |
| Libraries            | `pandas`, `sklearn`, `ibm_watson_machine_learning` |
| IDEs                 | Jupyter Notebook / Google Colab     |

---

## 📂 Dataset Format

**CSV File Name:** `legal_sentiment_dataset.csv` (or similar)

| Phrase                                                    | Sentiment |
|-----------------------------------------------------------|-----------|
| The contract was fulfilled on time and without issues.     | 1         |
| The service was unsatisfactory and delayed.                | -1        |
| The agreement was signed.                                 | 0         |
| ...                                                       | ...       |

- Sentiment labels: `1` (Positive), `0` (Neutral), `-1` (Negative)

---

## 🧠 IBM Foundation Models Used

- **Model Options:**
  - `FLAN_T5_XXL`
  - `MISTRAL_7B_INSTRUCT`
- **Approach:**
  - Few-shot prompting with labeled examples for each sentiment
  - Zero-shot fallback for short or ambiguous text

---

## 🧪 Prompt Template (Few-Shot)

```
Determine the sentiment of the following sentence (as 'positive', 'negative', or 'neutral'). Use the examples below as reference:

Example 1: sentence: The contract was fulfilled on time and without issues.
sentiment: positive
Example 2: sentence: The service was unsatisfactory and delayed.
sentiment: negative
Example 3: sentence: The agreement was signed.
sentiment: neutral

sentence: {Phrase}
sentiment:
```

---

## 🧱 Implementation Pipeline

### 1. **Data Preparation**

* Load the sentiment dataset (e.g., `legal_sentiment_dataset.csv`)
* Preprocess and remove empty or invalid rows

### 2. **IBM Watsonx.ai Setup**

* Authenticate using API key and project ID
* Select and initialize the foundation model

### 3. **Prompt-Based Sentiment Classification**

* For each text entry:
  * Insert it into the prompt template
  * Send prompt to model
  * Extract predicted sentiment

### 4. **Result Structuring**

* Save outputs to a new CSV: `legal_sentiment_results.csv`
* Optionally evaluate with labeled data (if available)

### 5. **Analytics & Reporting**

* Generate:
  * Sentiment distribution chart
  * Frequent words/phrases for each sentiment
  * Summary statement of overall sentiment

---

## 🚀 How to Run

### ✅ Prerequisites

* IBM Cloud account with Watsonx access
* IBM Cloud Object Storage (optional for remote data)
* Python 3.8+ and `pip` installed

### 🔧 Installation

```bash
pip install pandas scikit-learn ibm-watson-machine-learning
```

### ▶️ Execution

Run the Jupyter Notebook (or Python script):

```bash
jupyter notebook Legal_Sentiment_Analysis.ipynb
```

Or on Google Colab:

1. Upload your sentiment dataset CSV
2. Run notebook cells (authentication → model → classification)
3. Download output CSV

---

## 📊 Output

**Output File:** `legal_sentiment_results.csv`

| Phrase                                               | Predicted Sentiment |
|------------------------------------------------------|---------------------|
| The contract was fulfilled on time and without issues.| positive            |
| The service was unsatisfactory and delayed.           | negative            |
| The agreement was signed.                             | neutral             |

---

## 📈 Future Improvements

* Add support for more granular sentiment (e.g., very positive, very negative)
* Use multilingual models for non-English text
* Build a dashboard for real-time sentiment analytics
* Integrate with legal or business workflow tools

---

## 🤝 Contributors

* **Project Lead:** Bonala Shanmukesh
* **Co-Creators:** IBM Watsonx Foundation Model Team
* **Data Design & Prompt Engineering:** You & GPT Collaboration

---

## 🧠 Learn More

* [IBM Watsonx.ai Documentation](https://www.ibm.com/cloud/watsonx)
* [Few-Shot Prompting Techniques](https://arxiv.org/abs/2005.14165)
* [FLAN-T5: Scaling Instruction-Finetuned Language Models](https://arxiv.org/abs/2210.11416)

---

## 📄 License

This project is open-source under the **MIT License**. You may use, modify, and share freely with attribution.
