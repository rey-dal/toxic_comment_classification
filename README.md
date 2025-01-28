# Toxic Comment Classification

## Introduction

This project addresses the challenge of toxic comment classification by implementing and comparing three deep learning models: LSTM, GRU, and BERT. The goal is to identify and categorize toxic comments based on six categories: toxic, severe_toxic, obscene, threat, insult, and identity_hate.

## Dataset

The project utilizes the "Toxic Comment Classification Challenge" dataset by Kaggle (Jigsaw toxic data), which consists of a large collection of Wikipedia comments labeled with binary values for each toxicity category. The dataset is provided in two separate files: `train.csv` and `test.csv`. The `train.csv` file contains both the comments and their corresponding labels, and is used for training and validating the models. The `test.csv` file contains the comments without labels, and is used to evaluate the final performance of the trained models on unseen data. 

## Models

Three distinct models are employed for the classification task:

**LSTM:** The LSTM model leverages its ability to capture long-range dependencies in text. Its architecture comprises a bidirectional LSTM with multiple layers, designed for handling sequential data with complex relationships. The training process uses AdamW optimization with learning rate scheduling and monitors both loss and Macro-F1 score for evaluation. Early stopping is implemented to prevent overfitting, while model checkpoints and learning curves aid in performance analysis.

**GRU:** The GRU model tackles toxic comment classification by leveraging its efficient Gated Recurrent Unit architecture. It captures contextual information effectively through bidirectional processing and employs techniques like layer normalization and attention mechanisms. AdamW optimization with learning rate scheduling guides the training, with a focus on minimizing loss and maximizing Macro-F1 score. Early stopping helps to avoid overfitting, and model checkpoints and learning curves provide insights into performance.

**BERT:** The process involves freezing initial model layers, adapting the final classification head, and utilizing AdamW optimization with learning rate scheduling. Performance is tracked with training/validation loss and Macro-F1 score, employing early stopping to prevent overfitting. Detailed error analysis is conducted by saving false positive/negative cases for review. Model checkpoints, learning curves, and error analysis summaries are generated for comprehensive evaluation.

## Training and Evaluation (/learning_curves, /checkpoints)

Each model is trained on the training data and evaluated on a validation set using metrics such as loss and Macro-F1 score. Early stopping is implemented to prevent overfitting. Model checkpoints are saved to preserve the best-performing models. Learning curves are generated to visualize the training progress and saved. Models are tested on test data and predictions are saved.

## Error Analysis (/error_analysis)

Detailed error analysis is performed, by saving false positive and false-negative cases for review. This analysis helps to understand the model's weaknesses and potential biases.

## Annotations

Manually annotated 10 comments are tested. These annotations are not meant to provide a comprehensive evaluation.

## Results and Comparison

The performance of the three models is compared, the macro-averaged F1 is prioritized as dataset is not balanced and it does not take class imbalance into account, which ensures that every class is given equal weight independently of its proportion. A comparison plot is generated to visualize the results. The evaluation process is thorough, implementing cross-validation with detailed metrics tracking. The system compares the performance of all three models, generating comparative visualizations and statistical analyses of their performance differences.