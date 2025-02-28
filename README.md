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

# Name Validation AI

[![Support](https://img.shields.io/badge/Support-Me-brightgreen)](https://www.example.com/donate?crypto=YOUR_CRYPTO_ID)

Name Validation AI is an intelligent system that classifies first names as **real** or **fake**. This project demonstrates two primary approaches:

- **Reinforcement Learning Approach:** A custom Gym environment coupled with a PPO agent.
- **Transformer-based Approach:** Fine-tuning a transformer model (using Hugging Face Transformers) for binary classification with the final model saved in the `.safetensors` format.

Both models are equipped with detailed testing (including confusion matrix visualization) and API deployment capabilities.

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

   > **Note:** If you're using Google Colab, you can run each provided code block directly.

3. **Dependencies:**

   - `transformers`
   - `datasets`
   - `safetensors`
   - `stable-baselines3`
   - `gym`
   - `flask`
   - `scikit-learn`
   - `seaborn`
   - `huggingface_hub`

---

## Usage

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