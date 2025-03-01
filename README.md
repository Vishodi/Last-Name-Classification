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

# Last Name Classification Model

[![Support](https://img.shields.io/badge/Support-Me-brightgreen)](https://www.example.com/donate?crypto=YOUR_CRYPTO_ID)

A simple Transformer-based classifier that checks if a provided last name is likely to be **real** (LABEL_1) or **fake** (LABEL_0). This can be helpful in validating contact form submissions, preventing bot entries, or for general name classification tasks.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Training](#training)
  - [Testing](#testing)
  - [API Deployment](#api-deployment)
  - [Push to Hugging Face](#push-to-hugging-face)
- [Project Structure](#project-structure)
- [Support Me](#support-me)
- [License](#license)

---

## Overview

The goal of this project is to determine if a given first name is "real" (from a curated dataset) or "fake" (randomly generated). The project includes:

- **Custom Reinforcement Learning Setup:** Using OpenAI Gym and PPO for training.
- **Transformer Fine-tuning:** Leveraging a pre-trained DistilBERT model with Hugging Face’s Trainer API.
- **Deployment:** Code for a Flask API for real-time inference.
- **Model Hosting:** Support for pushing the model (in `.safetensors` format) to a private Hugging Face repository, ensuring seamless CPU/GPU usage.

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/your_username/name-validation-ai.git
   cd name-validation-ai
   ```

2. **Set Up the Environment:**

   Install the required packages using pip:

   ```bash
   pip install -r requirements.txt
   ```
---

## Usage

```python
from transformers import pipeline

# Replace with your model directory or Hugging Face model hub link
model_dir = "/kaggle/input/name-dataset/transformers_name_classifier_safetensors"

# Load the model pipeline
classifier = pipeline(
    "text-classification",
    model=model_dir,
    tokenizer=model_dir,
    framework="pt"
)

# Test the model
test_names = ["musk", "zzzzzz", "uhyhu", "trump"]
for name in test_names:
    result = classifier(name)
    label = result[0]['label']
    score = result[0]['score']
    print(f"Name: {name} => Prediction: {label}, Score: {score:.4f}")
```
```bash
Name: musk   => Prediction: LABEL_1, Score: 0.9167
Name: zzzzzz => Prediction: LABEL_0, Score: 0.9991
Name: uhyhu  => Prediction: LABEL_0, Score: 0.9944
Name: trump  => Prediction: LABEL_1, Score: 0.9998
```
### Training

- **Reinforcement Learning Model:**  
  Use the provided training notebook/code block to set up the custom Gym environment and train a PPO agent for name validation.

- **Transformer-based Model:**  
  Fine-tune a transformer model (e.g., DistilBERT) on a balanced dataset of real and fake names. The final model is saved in `.safetensors` format for robust, secure, and efficient storage.

### Testing

- **Confusion Matrix:**  
  Run the testing code block to evaluate the transformer-based model. The block collects predictions on a test set, computes a confusion matrix, and visualizes the results using Seaborn.

- **Flask API:**  
  Deploy a Flask API to accept a first name as input and return a prediction (real or fake) in real time.

---

## Project Structure

```
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

```

---

## Support Me

If you find this project helpful and would like to support my work, please consider donating using crypto.
<a href="https://www.example.com/donate?crypto=YOUR_CRYPTO_ID" target="_blank">
  <img src="https://img.shields.io/badge/Support-Me-brightgreen" alt="Support Me">
</a>

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*Contributions, issues, and feature requests are welcome! Feel free to fork the repository and open a pull request.*
```