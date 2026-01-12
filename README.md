# MediaSense: Fake News Detection System

## Overview
**MediaSense** is a machine learning framework designed to detect fake news based on the textual content of news articles. By utilizing Natural Language Processing (NLP) and various classification algorithms, MediaSense moves beyond simple blacklisting of websites to analyze the semantic patterns within articles to determine their reliability.

The project aims to build a classifier that can identify when a news source may be producing fake news, allowing social networks to weigh the visibility of stories based on their predicted reliability.

## Key Features
* **Text Pre-processing:** Utilizes `Doc2Vec` (via Gensim) for embedding generation and NLTK for text cleaning and stopword removal.
* **Multi-Model Architecture:** Implementations of five distinct classifiers:
    * **Naive Bayes:** A baseline probabilistic classifier.
    * **Support Vector Machine (SVM):** A robust classifier for high-dimensional text data.
    * **Neural Networks (TensorFlow):** A custom deep neural network implementation.
    * **Neural Networks (Keras):** A high-level deep learning implementation.
    * **LSTM (Long Short-Term Memory):** A recurrent neural network optimized for sequence data.

## Dataset Description
The project utilizes a labeled dataset containing:
* **train.csv:** The primary training set with attributes:
    * `id`: Unique article identifier.
    * `title`: The headline of the article.
    * `author`: The original author.
    * `text`: The main body content.
    * `label`: Classification tag (**1** = Unreliable/Fake, **0** = Reliable/Real).
* **test.csv:** Testing dataset with identical attributes (excluding labels).

## Model Performance
The following table compares the accuracy of the implemented models on the testing dataset:

| Model | Accuracy |
| :--- | :---: |
| Naive Bayes | 72.94% |
| SVM | 88.42% |
| Neural Network (TensorFlow) | 81.42% |
| Neural Network (Keras) | 92.62% |
| **LSTM** | **94.53%** |

## File Structure
```text
MediaSense/
├── datasets/
│   ├── train.csv
│   └── test.csv
├── images/             # Confusion matrix visualizations
├── getEmbeddings.py    # Pre-processing and Doc2Vec generation
├── svm.py              # SVM Classifier implementation
├── naive-bayes.py      # Naive Bayes implementation
├── neural-net-tf.py    # TensorFlow Neural Net implementation
├── neural-net-keras.py # Keras Neural Net implementation
├── LSTM.py             # LSTM implementation
└── README.md
