# Attention Visualizer

BERT-based NLP project that predicts masked words and visualizes self-attention across transformer layers and heads.

## Overview

This project uses a pre-trained BERT masked language model to perform two main tasks:

1. Predict the most likely replacements for a masked word in a sentence
2. Generate visual diagrams showing self-attention patterns across transformer layers and attention heads

It combines natural language processing with model interpretability, providing a practical introduction to how transformer-based language models process textual context.

## Features

- Predicts top masked-token completions using `bert-base-uncased`
- Uses a pre-trained transformer model from Hugging Face
- Extracts attention weights from all layers and heads
- Generates grayscale attention diagrams as PNG images
- Demonstrates both practical NLP usage and attention visualization

## Technologies Used

- Python
- TensorFlow
- Hugging Face Transformers
- Pillow

## Repository Structure

```text
attention-visualizer/
├── README.md
├── requirements.txt
├── mask.py
├── .gitignore
└── examples/
    ├── layer1-head11.png
    └── layer6-head10.png
```

## How It Works

The user provides a sentence containing BERT’s mask token.

Example:

```text
The cat [MASK] on the sofa.
```

The script then:

- tokenizes the input text
- finds the position of the `[MASK]` token
- runs the sentence through a pre-trained BERT model
- prints the top predicted replacements
- extracts self-attention weights from all layers and heads
- generates one attention diagram per layer and per head

## Example Output

Example input:

```text
The cat [MASK] on the sofa.
```

Example predictions:

```text
The cat sat on the sofa.
The cat was on the sofa.
The cat lay on the sofa.
```

## Example Attention Visualizations

Two sample outputs are included in the `examples/` folder:

- `layer1-head11.png`
- `layer6-head10.png`

Each attention diagram shows how strongly each token attends to every other token in the sentence. Brighter cells indicate higher attention weights.

In these visualizations:

- rows represent the token that is attending
- columns represent the token receiving attention
- lighter cells indicate stronger attention
- special tokens such as `[CLS]` and `[SEP]` may receive strong attention in some heads due to their structural role in the model

## Installation

This project is best run with **Python 3.11**.

Install dependencies with:

```bash
python -m pip install -r requirements.txt
```

## Usage

Run the script with:

```bash
python mask.py
```

Then enter a sentence containing the `[MASK]` token when prompted.

## Notes on Compatibility

This project was tested using a Python/TensorFlow/Transformers combination compatible with the original CS50 AI implementation.

If you run into environment issues, use:

- Python 3.11
- TensorFlow 2.15.x
- Transformers 4.30.x

## Notes

- The project uses the pre-trained model `bert-base-uncased`
- Generated attention images are not all included in the repository, since they can be reproduced by running the script
- Only selected example outputs are kept in the `examples/` folder

## Purpose

This project was developed as part of **CS50 AI** and serves as a practical introduction to:

- masked language modeling
- transformer architectures
- self-attention
- model interpretability

## Author

**André Montenegro**
