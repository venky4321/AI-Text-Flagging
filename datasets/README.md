# Datasets

This folder lists the public datasets used in the paper
**"A Risk-Calibrated Decision Framework for AI-Text Flagging: Fair and Robust Flag/Abstain/Clear Decisions under Paraphrase Attack"**.

The raw data is **not** redistributed in this repository. Each dataset has its own licence, so please download it from the official source below.

| Study | Role in the paper | Dataset | Access link |
|---|---|---|---|
| Study 1 | AI texts + "native" human texts | HC3 | https://huggingface.co/datasets/Hello-SimpleAI/HC3 |
| Study 1 | Learner essays (analytic proficiency scores) | ELLIPSE | https://github.com/scrosseye/ELLIPSE-Corpus |
| Study 2 | Learner + native student essays (7 source-based prompts) | ASAP 2.0 | https://github.com/scrosseye/ASAP_2.0 |
| Study 2 | Essays underlying ASAP 2.0 (ELL status, holistic score) | PERSUADE 2.0 | https://github.com/scrosseye/persuade_corpus_2.0 |
| Study 2 | AI essays (6,194, seven generator families) | DAIGT-v2 | https://www.kaggle.com/datasets/thedrcat/daigt-v2-train-dataset |

---

## 1. HC3 (Human ChatGPT Comparison Corpus)

- Page: https://huggingface.co/datasets/Hello-SimpleAI/HC3
- Direct file: https://huggingface.co/datasets/Hello-SimpleAI/HC3/resolve/main/all.jsonl
- Licence: CC BY-SA 4.0

```bash
wget https://huggingface.co/datasets/Hello-SimpleAI/HC3/resolve/main/all.jsonl -O data/hc3_all.jsonl
```

Or in Python:

```python
from datasets import load_dataset
hc3 = load_dataset("Hello-SimpleAI/HC3", "all")
```

Citation: Guo et al. (2023). *How Close is ChatGPT to Human Experts? Comparison Corpus, Evaluation, and Detection.* arXiv:2301.07597.

## 2. ELLIPSE (English Language Learner Insight, Proficiency and Skills Evaluation)

- Repository: https://github.com/scrosseye/ELLIPSE-Corpus
- Files used: `ELLIPSE_Final_github_train.csv`, `ELLIPSE_Final_github_test.zip`

```bash
git clone https://github.com/scrosseye/ELLIPSE-Corpus.git data/ELLIPSE-Corpus
```

Citation: Crossley et al. (2023). *The English Language Learner Insight, Proficiency and Skills Evaluation (ELLIPSE) Corpus.* International Journal of Learner Corpus Research, 9(2), 248–269.

## 3. ASAP 2.0

- Repository: https://github.com/scrosseye/ASAP_2.0
- Licence: CC BY 4.0

```bash
git clone https://github.com/scrosseye/ASAP_2.0.git data/ASAP_2.0
```

Citation: Crossley et al. (2025). *A large-scale corpus for assessing source-based writing quality: ASAP 2.0.* Assessing Writing, 65.

## 4. PERSUADE 2.0

- Repository: https://github.com/scrosseye/persuade_corpus_2.0
- The CSV files are too large for GitHub; follow the training-set and test-set links in that repository's README.
- Key file: `persuade_2.0_human_scores_demo_id_github.csv` (full text, holistic score, prompt, English-learner status)
- Licence: CC BY-NC-SA 4.0

Citation: Crossley et al. (2024). *A large-scale corpus for assessing written argumentation: PERSUADE 2.0.* Assessing Writing, 61, 100865.

## 5. DAIGT-v2 Train Dataset

- Kaggle: https://www.kaggle.com/datasets/thedrcat/daigt-v2-train-dataset
- Requires a free Kaggle account and API token (`~/.kaggle/kaggle.json`).
- File: `train_v2_drcat_02.csv` (the `source` column gives the generator model)

```bash
pip install kaggle
kaggle datasets download -d thedrcat/daigt-v2-train-dataset -p data/
unzip data/daigt-v2-train-dataset.zip -d data/daigt-v2
```

Citation: Kłeczek, D. (2023). *DAIGT v2 train dataset.* Kaggle, LLM – Detect AI Generated Text competition.

---

## Suggested folder layout after download

```
data/
├── hc3_all.jsonl
├── ELLIPSE-Corpus/
├── ASAP_2.0/
├── persuade_corpus_2.0/
└── daigt-v2/
```

Add `data/` to `.gitignore` so raw files are never committed.
