---
license: mit
language:
- en
metrics:
- accuracy 97%
base_model:
- distilbert/distilbert-base-uncased
pipeline_tag: text-classification
---

# <h2>Last Name Classification Model</h2>
[![Support](https://img.shields.io/badge/Support-Us-brightgreen)](https://nowpayments.io/donation/Vishodi)

A  Transformer-based classifier that checks if a provided last name is likely to be **real** (LABEL_1) or **fake** (LABEL_0). This can be helpful in validating contact form submissions, preventing bot entries, or for general name classification tasks.

---
## Table of Contents

- [Project Structure](#project_structure)
- [Installation](#installation)
- [Usage](#usage)
- [Support Me](#support-me)
- [License](#license)

## Project Structure

Last_Name_Prediction/
├── .gitattributes
├── README.md
├── config.json
├── model.safetensors
├── requirements.txt
├── special_tokens_map.json
├── tokenizer.json
├── tokenizer_config.json
└── vocab.txt

---

## Installation

1. **Clone the Repository:**

   
bash
   git clone https://github.com/Vishodi/Last-Name-Classification.git


2. **Set Up the Environment:**

   Install the required packages using pip:

   
bash
   pip install -r requirements.txt

---

## Usage
Python
python
from transformers import pipeline

# Replace with your model repository
model_dir = "vishodi/Last-Name-Classification"

# Load the model pipeline with authentication
classifier = pipeline(
    "text-classification",
    model=model_dir,
    tokenizer=model_dir,
)

# Test the model
test_names = ["kiara", "zzzzzz", "uhyhu", "trump"]
for name
