# indicLLMs 🇮🇳 Culturally-Grounded QA for Meitei (Manipuri)
**Fine-Tuning IndicBERT on Hybrid Datasets for Low-Resource QA**

---

### 🧠 Overview

This repository contains all artifacts from the **CS224U Final Project** titled:  
**"Culturally-Aligned QA for Meitei: Fine-Tuning IndicBERT with Hybrid Datasets"**  
by **Rahul Basu**, Founder – humaNLP Mindful AI Solutions LLP.

The project addresses the scarcity of NLP resources for **Meitei (Manipuri)**, a low-resource language spoken in Northeast India, by creating a culturally-grounded extractive Question Answering (QA) system using a fine-tuned **IndicBERT** model.  

---

### 🎯 Objectives

- Build a lightweight, semantically aligned QA system for Meitei
- Fine-tune IndicBERT using a hybrid dataset of:
  - 500 culturally specific QA pairs (generated synthetically)
  - 200 translated SQuAD QA pairs
- Evaluate performance using **BERTScore**, **ROUGE-L**, and **BLEU**
- Release a reproducible pipeline and open dataset under an open license

---

### 📂 Repository Structure

├── data/
│ ├── meitei_cqa.jsonl # 500 synthetic cultural QA pairs
│ ├── translated_squad_meitei.jsonl # 200 translated QA pairs
│ └── preprocessed/ # Tokenized and split datasets
│
├── models/
│ └── fine_tuned_indicbert/ # Fine-tuned HuggingFace model
│
├── scripts/
│ ├── preprocess.py # Data cleaning, Romanization, tokenization
│ ├── train.py # HuggingFace Trainer API
│ ├── evaluate.py # Metrics: BERTScore, BLEU, ROUGE-L
│
├── notebooks/
│ └── QA_pipeline_walkthrough.ipynb
│
├── results/
│ └── evaluation_metrics.json
│
└── README.md

---

### 🧪 Experimental Setup

- **Model**: `ai4bharat/IndicBERT` with QA head (`AutoModelForQuestionAnswering`)
- **Training Data**: 700 QA pairs split into train (80%), val (10%), test (10%)
- **Script Used**: Romanized Meitei (due to tokenizer limitations in IndicBERT)
- **Training Platform**: Single NVIDIA T4 (16 GB)
- **Framework**: Hugging Face Transformers + Datasets

---

### 🧮 Metrics & Performance

| Model Variant               | BERTScore (F1) | ROUGE-L | BLEU |
|----------------------------|----------------|----------|------|
| IndicBERT (Fine-Tuned)     | **0.82**       | 0.17     | 0.00 |
| IndicBERT (Zero-Shot)      | 0.62           | 0.11     | 0.00 |
| English QA + Backtrans     | 0.76           | 0.15     | 0.00 |
| Random Span Baseline       | 0.40           | 0.06     | 0.00 |

*Note: Semantic metrics like BERTScore are more reliable in morphologically rich languages like Meitei.*

---

### 🧩 Key Features

- ✅ **Cultural Alignment**: QA pairs based on festivals, governance, oral traditions, and rituals
- ✅ **Tokenizer Adaptation**: Custom Romanization pipeline
- ✅ **Open Dataset**: JSONL format, released under open license
- ✅ **Reproducible Codebase**: Easily extensible to other Indic languages

---

### 🔬 Research Contributions

- First reproducible QA pipeline for Meitei using LLMs
- Evaluation of fine-tuned IndicBERT vs zero-shot and translation baselines
- Released dataset + training scripts for the research community
- Analysis of overfitting, tokenization errors, and metric gaps

---

### 🏷 License

This repository is released under the **MIT License** for code and **CC BY 4.0** for datasets.

---

### 👤 Author

**Rahul Basu**  
Founder, humaNLP Mindful AI Solutions LLP  
Adjunct Faculty – NLP & RL @ BITS Pilani  
📧 rahulbasuai@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/basu-rahul)

---

### 🙌 Acknowledgements

- Stanford CS224U Teaching Team
- AI4Bharat for `indictrans2` and `IndicBERT`
- Community contributors working on Indic NLP, cultural alignment, and low-resource language access

---

### 🔭 Future Work

- Add more culturally validated QA pairs in Meitei Mayek
- Extend to other low-resource languages like Bhojpuri and Konkani
- Add adapter-based fine-tuning and multilingual alignment

