# Sentiment Analysis on Amazon Reviews

This project performs sentiment analysis on Amazon product reviews using two sentiment analysis models: **VADER** and **RoBERTa**. The goal is to classify reviews as positive, negative, or neutral and evaluate the performance of these models using metrics such as accuracy, precision, recall, F1-score, and confusion matrices.

---

## Table of Contents
1. Project Overview
2. Dataset
3. Models Used
4. Evaluation Metrics
5. Results
6. How to Run the Project
7. Dependencies
8. Future Improvements

---

## Project Overview

Sentiment analysis is a natural language processing (NLP) task that determines the sentiment of a given text. In this project, we analyze Amazon product reviews to classify them into three categories:
- **Positive**
- **Negative**
- **Neutral**

We use two models for sentiment analysis:
1. **VADER (Valence Aware Dictionary and sEntiment Reasoner)**: A rule-based model for general sentiment analysis.
2. **RoBERTa (Robustly Optimized BERT Pretraining Approach)**: A transformer-based model fine-tuned for sentiment classification.

The project evaluates the performance of these models and compares their effectiveness.

---

## Dataset

The dataset consists of Amazon product reviews with the following columns:
- **Text**: The review text.
- **Score**: The star rating of the review (1 to 5).
- **VADER Scores**: Sentiment scores (`vader_neg`, `vader_neu`, `vader_pos`, `vader_compound`) generated by the VADER model.
- **RoBERTa Scores**: Sentiment probabilities (`roberta_neg`, `roberta_neu`, `roberta_pos`) generated by the RoBERTa model.

### Ground Truth Labels
The `Score` column is used to derive the ground truth sentiment:
- **Positive**: Scores 4 and 5.
- **Negative**: Scores 1 and 2.
- **Neutral**: Score 3.

---

## Models Used

### 1. VADER
- A lexicon and rule-based sentiment analysis tool.
- Outputs sentiment scores (`compound`, `pos`, `neu`, `neg`).
- Classification thresholds:
  - `compound >= 0.05`: Positive
  - `compound <= -0.05`: Negative
  - Otherwise: Neutral

### 2. RoBERTa
- A transformer-based model fine-tuned for sentiment classification.
- Outputs probabilities for each sentiment class (`positive`, `neutral`, `negative`).
- Classification is based on the highest probability.

---

## Evaluation Metrics

The following metrics are used to evaluate the performance of the models:
1. **Accuracy**: The percentage of correct predictions.
2. **Precision**: The proportion of true positive predictions out of all positive predictions.
3. **Recall**: The proportion of true positive predictions out of all actual positives.
4. **F1-Score**: The harmonic mean of precision and recall.
5. **Confusion Matrix**: A matrix showing the breakdown of true and predicted labels.

---

## Results

### VADER Metrics:
- **Accuracy**: 81.09%
- **Precision**: 77.15%
- **Recall**: 81.09%
- **F1-Score**: 78.54%

### RoBERTa Metrics:
- **Accuracy**: 85.51%
- **Precision**: 84.93%
- **Recall**: 85.51%
- **F1-Score**: 85.17%

### Confusion Matrices:
#### VADER:
- True Positives: 734
- False Positives: 11
- False Negatives: 30

#### RoBERTa:
- True Positives: 721
- False Positives: 33
- False Negatives: 21

**Observation**: RoBERTa outperforms VADER in all metrics, demonstrating its superior ability to classify sentiments in this dataset.

---

## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/SidhanthSanil/MTL_Reviews_Amazon
   cd <repo-folder>
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter Notebook:
   ```bash
   jupyter notebook MTL_project.ipynb
   ```

4. Follow the steps in the notebook to preprocess the data, run the models, and evaluate their performance.

---

## Dependencies

The project requires the following Python libraries:
- `pandas`
- `numpy`
- `sklearn`
- `matplotlib`
- `seaborn`
- `tqdm`
- `ipywidgets` (for progress bars in Jupyter Notebook)

Install all dependencies using:
```bash
pip install -r requirements.txt
```

---

## Future Improvements

1. **Dataset Expansion**:
   - Use a larger and more diverse dataset to improve model generalization.

2. **Fine-Tuning RoBERTa**:
   - Fine-tune the RoBERTa model on the specific dataset for better performance.

3. **Neutral Sentiment Analysis**:
   - Investigate why neutral reviews are underrepresented or misclassified.

4. **Additional Models**:
   - Experiment with other transformer-based models like BERT or DistilBERT.

5. **Error Analysis**:
   - Perform a detailed analysis of misclassified reviews to identify patterns and improve the models.

---

## Conclusion

This project demonstrates the effectiveness of sentiment analysis using VADER and RoBERTa. While both models perform well, RoBERTa consistently outperforms VADER in accuracy, precision, recall, and F1-score. The results highlight the potential of transformer-based models for sentiment classification tasks.

Feel free to contribute or suggest improvements to this project!

--- 
