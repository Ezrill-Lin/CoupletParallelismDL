# Couplet Parallelism Measurement using Deep Learning

## 📖 Overview
This project models human evaluation of the **parallelism** in 7-character classical Chinese couplets using **deep learning techniques**. Parallelism is a key literary feature of Chinese couplets, encompassing syntactic, semantic, and thematic alignment between two poetic lines. Our goal is to develop a model that imitates human judgment of parallelism, providing insights into how this complex literary art is perceived.

## 🛠 Methodology
We implemented a framework that combines multiple computational models to evaluate couplet parallelism:
1. **Word Segmentation**:
   - Splits text into meaningful words for precise alignment.
   - Uses a feed-forward neural network with **SikuBERT** embeddings for segmentation.
   
2. **Part-of-Speech (POS) Tagging**:
   - Identifies grammatical structures to compare syntactic alignment.
   - Utilizes a fine-tuned **RoBERTa** model for POS tagging.

3. **Character-Wise Semantic Matching**:
   - Measures semantic similarity between corresponding characters in the two couplet halves.
   - Employs SikuBERT embeddings for comparison.

4. **Theme & Emotion Semantic Matching**:
   - Evaluates thematic and emotional alignment between couplet lines.
   - Leverages fine-tuned SikuBERT embeddings trained on a labeled classical poetry dataset.

### Weighted Average Scoring
The parallelism score is computed as a **weighted average** of the outputs from the above models. We optimized the weights using **Root Mean Square Error (RMSE)** to align model predictions with human-assigned scores.

## 📊 Dataset
- **Couplets Dataset**:
  - Cleaned dataset of ~350,000 7-character couplets.
  - Filtered from the original dataset on [GitHub](https://github.com/v-zich/couplet-clean-dataset).

- **Classical Poetry Dataset**:
  - Sourced from Kaggle, containing 17,103 poems with theme and emotion labels.
  - Useful for training the Theme & Emotion Semantic Matching model.

- **Human Survey**:
  - Conducted a survey with 151 participants of diverse demographics.
  - Collected human ratings for parallelism across eight carefully curated couplets.

## 🧠 Results
- The final model achieved a high degree of alignment with human scores, especially for **featureless couplets**.
- Key findings:
  - **Theme and emotion** play a significant role in human evaluation of parallelism.
  - The model struggles with classical allusions and cultural references, areas where human cognition excels.

## ⚡ Strengths
- Comprehensive evaluation incorporating syntax, semantics, theme, and emotion.
- Diversity in survey demographics ensured robust human evaluation data.

## 🧩 Limitations & Future Work
1. **Training Epochs**: Limited by computational resources; longer training could enhance performance.
2. **Phonetic Features**: Incorporating phonetic data could improve alignment with human judgments.
3. **Cultural Nuances**: The model could be extended to handle allusions and cultural references better.

