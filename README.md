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

Last Name Classification Model
===============================

[Support](https://nowpayments.io/donation/Vishodi)

A Transformer-based classifier that checks if a provided last name is likely to be real (LABEL_1) or fake (LABEL_0). This can be helpful in validating contact form submissions, preventing bot entries, or for general name classification tasks.

Table of Contents
-----------------
1. Project Structure
2. Installation
3. Usage
4. Support Me
5. License

Project Structure
-----------------
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

Installation
------------
1. Clone the Repository:
   git clone https://github.com/Vishodi/Last-Name-Classification.git

2. Set Up the Environment:
   pip install -r requirements.txt

Usage
-----
Example Python code:

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
for name in test_names:
    result = classifier(name)
    label = result[0]['label']
    score = result[0]['score']
    print(f"Name: {name} => Prediction: {label}, Score: {score:.4f}")

Sample Output:
Name: musk   => Prediction: LABEL_1, Score: 0.9167
Name: zzzzzz => Prediction: LABEL_0, Score: 0.9991
Name: uhyhu  => Prediction: LABEL_0, Score: 0.9944
Name: trump  => Prediction: LABEL_1, Score: 0.9998

Support Me
----------
If you find this project helpful and would like to support my work, please consider donating using crypto.
Donation Link: https://nowpayments.io/donation/Vishodi

License
-------
This project is licensed under the MIT License. See the LICENSE file for details.

Contributions, issues, and feature requests are welcome! Feel free to fork the repository and open a pull request.
