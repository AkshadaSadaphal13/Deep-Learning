
# Assignment 5 – RNN, LSTM and GRU Sequence Classification

## Aim

To implement and compare RNN, LSTM, and GRU models for sequence
classification and analyze their performance using appropriate
evaluation metrics.

## Dataset

The IMDB Movie Review Dataset is used.

The dataset contains 50,000 movie reviews:

- 25,000 training reviews
- 25,000 testing reviews

Each review is classified as:

- 0 – Negative
- 1 – Positive

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- TensorFlow
- Keras

## Models Implemented

### 1. Simple RNN

A basic recurrent neural network used for sequence classification.

### 2. LSTM

Long Short-Term Memory network designed to learn long-term dependencies
in sequential data.

### 3. GRU

Gated Recurrent Unit that provides a simpler gated recurrent
architecture.

## Methodology

1. Load the IMDB dataset.
2. Analyze the dataset.
3. Analyze sequence lengths.
4. Pad sequences to a fixed length of 200.
5. Build the Simple RNN model.
6. Train the RNN model.
7. Build the LSTM model.
8. Train the LSTM model.
9. Build the GRU model.
10. Train the GRU model.
11. Generate test predictions.
12. Calculate Accuracy.
13. Calculate Precision.
14. Calculate Recall.
15. Calculate F1-score.
16. Generate confusion matrices.
17. Compare the three models.
18. Identify the best-performing model.

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

## Conclusion

RNN, LSTM, and GRU can all be used for sequence classification.
LSTM and GRU are designed to handle long-term dependencies better
than a basic RNN.

The final model is selected based on the evaluation results obtained
from the IMDB dataset.