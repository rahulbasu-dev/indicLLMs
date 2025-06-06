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
<pre> repo-root/ ├── <b>data/</b> │ ├── meitei_cqa.jsonl # 500 culturally grounded QA pairs │ ├── translated_squad_meitei.jsonl # 200 Meitei-translated SQuAD QA pairs │ └── preprocessed/ # Preprocessed and tokenized versions │ ├── <b>models/</b> │ └── fine_tuned_indicbert/ # Hugging Face model checkpoint directory │ ├── <b>scripts/</b> │ ├── preprocess.py # Data cleaning, Romanization │ ├── train.py # Hugging Face Trainer API │ ├── evaluate.py # BERTScore, BLEU, ROUGE-L │ ├── <b>notebooks/</b> │ └── QA_pipeline_walkthrough.ipynb # Step-by-step training and inference │ ├── <b>results/</b> │ └── evaluation_metrics.json # Final model evaluation scores │ └── README.md # Project overview and documentation </pre>

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

