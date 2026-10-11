# News Article Classification: Classical ML vs. LLMs

Comparison of three approaches for classifying news articles into POLITICS, ENTERTAINMENT and WELLNESS, using the Kaggle News Category Dataset.

## Approach
- **Data:** 45,000 articles (15,000 per class, balanced), headline + short description, 80/20 train/test split
- **Classical ML:** TF-IDF (5,000 features) + XGBoost, trained on 36,000 articles
- **LLM zero-shot:** GPT-OSS 20B via Groq API and LangChain
- **LLM few-shot:** Qwen 27B with one example per class in the prompt

## Results
| Model | Test set | Accuracy | Macro F1 |
|---|---|---|---|
| XGBoost | 9,000 articles | 87% | 87% |
| XGBoost | 270 articles | 85% | 85% |
| Zero-shot GPT-OSS 20B | 270 articles | 92% | 92% |
| Few-shot Qwen 27B | 150 articles | 94% | 94% |

LLMs reached higher accuracy, while XGBoost runs locally, instantly and with no API cost. Due to free-tier rate limits, LLMs were evaluated on smaller balanced samples.

## How to run
Open the notebook in Google Colab and add your Groq API key in Colab Secrets under the name `Key`.

Built for the Advanced Data Analysis course, Faculty of Organizational Sciences, University of Belgrade.
