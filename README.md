# CodeCommenter

**CodeCommenter** is a machine learning project for automatic code documentation. It uses pre-trained transformer models (e.g., CodeT5, CodeTrans) and fine-tuning techniques to generate high-quality natural language comments for Python functions. It supports training, evaluation, and inference workflows.

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Training](#training)
- [Evaluation](#evaluation)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- Fine-tuning support for code-commenting models (CodeT5, CodeTrans)
- Preprocessing of `code_search_net` dataset with filtering and cleaning
- Evaluation metrics: BLEU, ROUGE, exact match
- Visual and statistical analysis of model performance
- Scriptable training and inference pipelines

---

## Installation

Clone the repository and install the required dependencies.

```bash
git clone https://github.com/yourusername/CodeCommenter.git
cd CodeCommenter/homemade-model
pip install -r requirements.txt
````

For conda users, you may use the provided environment file:

```bash
conda env create -f env.yml
conda activate codecommenter
```

---

## Usage

### Generate Comment from Code

Use the `main.py` script to load a trained model and generate comments:

```bash
python main.py
```

Modify the `generate_comment(code_snippet)` function for custom inputs.

---

## Training

To fine-tune a model on the Python subset of `code_search_net`, run:

```bash
python homemade-model/main.py
```

This will:

* Filter and preprocess the dataset
* Tokenize code and documentation
* Fine-tune a Seq2Seq model (default: CodeTrans)
* Save the trained model in `homemade-model/final_model/`

---

## Evaluation

Use `eveluate.py` for benchmark evaluation:

```bash
python homemade-model/eveluate.py
```

This computes:

* BLEU score
* ROUGE metrics
* Exact match accuracy

Or use `model_evaluate_and_analysis.py` to compare pretrained and fine-tuned models and generate boxplots for visual analysis.

