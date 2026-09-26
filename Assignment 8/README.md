# Assignment 8 – Pre-trained BERT for Sentiment Analysis

## 📌 Title

**Implementation of Pre-trained BERT Model for Sentiment Analysis**

## 🎯 Aim

To implement a pre-trained BERT model for sentiment analysis and classify movie reviews into positive and negative sentiment categories.

## 📖 Description

BERT (Bidirectional Encoder Representations from Transformers) is a transformer-based language model developed for understanding the contextual meaning of text.

In this assignment, the pre-trained `bert-base-uncased` model is fine-tuned on the IMDB movie review dataset for binary sentiment classification.

The model receives a movie review as input and predicts whether the sentiment of the review is:

* **0 – Negative**
* **1 – Positive**

## 🧠 Concepts Covered

* Natural Language Processing
* Transformer Architecture
* BERT
* Tokenization
* Self-Attention
* Transfer Learning
* Fine-Tuning
* Text Classification
* Sentiment Analysis
* Model Evaluation

## 🗂️ Dataset

The **IMDB Movie Reviews Dataset** is used for this project.

The dataset contains movie reviews labelled as positive or negative.

### Classes

| Label | Sentiment |
| ----- | --------- |
| 0     | Negative  |
| 1     | Positive  |

The dataset is loaded using the Hugging Face `datasets` library.

## 🛠️ Technologies Used

* Python
* PyTorch
* Hugging Face Transformers
* Hugging Face Datasets
* Scikit-learn
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook / VS Code

## 📁 Project Structure

```text
Assignment 8/
│
├── Assignment_8_BERT_Sentiment_Analysis.ipynb
├── README.md
├── requirements.txt
├── .gitignore
│
├── results/
│   ├── class_distribution.png
│   ├── confusion_matrix.png
│   └── sample_predictions.png
│
└── screenshots/
```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/AkshadaSadaphal13/Deep-Learning.git
```

Navigate to the Assignment 8 folder:

```bash
cd "Deep-Learning/Assignment 8"
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

## 🚀 Implementation Steps

### 1. Import Libraries

The required Python libraries for deep learning, NLP, visualization and evaluation are imported.

### 2. Load Dataset

The IMDB dataset is loaded using:

```python
load_dataset("imdb")
```

### 3. Explore Dataset

The dataset size, labels and sample reviews are examined.

### 4. Tokenization

The pre-trained BERT tokenizer is loaded:

```python
AutoTokenizer.from_pretrained("bert-base-uncased")
```

The text is converted into BERT-compatible token IDs.

### 5. Load Pre-trained BERT

The pre-trained BERT model is loaded using:

```python
AutoModelForSequenceClassification
```

The model is configured for two classes.

### 6. Fine-Tuning

The BERT model is fine-tuned on the IMDB dataset using the Hugging Face Trainer API.

### 7. Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

### 8. Prediction

The trained model is tested on new movie reviews to determine their sentiment.

## 🏗️ Model Architecture

```text
                    Input Review
                         │
                         ▼
                BERT Tokenizer
                         │
                         ▼
                Input Token IDs
                         │
                         ▼
              Pre-trained BERT
                         │
                         ▼
              Transformer Encoder
                         │
                         ▼
             Contextual Representation
                         │
                         ▼
             Classification Layer
                         │
                         ▼
              ┌──────────┴──────────┐
              ▼                     ▼
          Negative               Positive
```

## 📊 Evaluation Metrics

### Accuracy

Measures the percentage of correctly classified reviews.

```text
Accuracy = Correct Predictions / Total Predictions
```

### Precision

Measures how many reviews predicted as a particular class actually belong to that class.

### Recall

Measures how many actual samples of a class are correctly identified.

### F1-Score

The F1-score is the harmonic mean of precision and recall.

```text
F1 = 2 × (Precision × Recall) / (Precision + Recall)
```

## 📈 Results

The actual results obtained after training are recorded in the notebook.

The project includes:

* Class distribution graph
* Confusion matrix
* Classification report
* Sample predictions

### Model Performance

| Metric    |                   Value |
| --------- | ----------------------: |
| Accuracy  | Obtained from execution |
| Precision | Obtained from execution |
| Recall    | Obtained from execution |
| F1-Score  | Obtained from execution |

> The metric values should be updated with the actual values produced by the notebook after execution.

## 🔍 Sample Prediction

Example input:

```text
"The movie was absolutely amazing and enjoyable."
```

Expected sentiment:

```text
Positive
```

Example input:

```text
"The movie was boring and disappointing."
```

Expected sentiment:

```text
Negative
```

## ✅ Advantages of BERT

1. Understands contextual meaning of words.
2. Uses bidirectional attention.
3. Uses knowledge learned during pre-training.
4. Requires less task-specific training compared with training a language model from scratch.
5. Performs effectively on many NLP classification tasks.
6. Can be fine-tuned for different downstream NLP applications.

## ⚠️ Limitations

1. BERT requires significant computational resources.
2. Training can be slow on systems without a GPU.
3. The model contains a large number of parameters.
4. Inference can be slower than simpler NLP models.
5. Maximum sequence length limits the amount of text processed at once.

## 🔮 Applications

BERT-based sentiment analysis can be used for:

* Product review analysis
* Customer feedback analysis
* Social media sentiment analysis
* Movie review classification
* Brand monitoring
* Customer support analysis
* Opinion mining

## 🏁 Conclusion

The pre-trained BERT model was successfully implemented for sentiment analysis using the IMDB movie review dataset.

The text data was tokenized using the BERT tokenizer, and the pre-trained `bert-base-uncased` model was fine-tuned for binary sentiment classification.

The performance of the model was evaluated using accuracy, precision, recall, F1-score and a confusion matrix.

This experiment demonstrates how transfer learning and transformer-based models can be effectively applied to NLP text classification problems.

## 👩‍💻 Author

**Akshada Sadaphal**

B.Tech Computer Science

Vishwakarma Institute of Technology, Pune

## 📚 References

* Devlin et al., *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding*
* Hugging Face Transformers Documentation
* Hugging Face Datasets Documentation
* IMDB Movie Reviews Dataset
