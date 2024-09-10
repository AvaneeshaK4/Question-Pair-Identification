# Quora Duplicate Question Pair Identification

This project aims to identify duplicate question pairs from the Quora dataset using various approaches. The dataset used is sourced from Kaggle.

## Dataset

The dataset is available on [Kaggle](https://www.kaggle.com/datasets/quora/question-pairs-dataset)

## Project Overview

The project involves three main approaches to tackle the problem of identifying duplicate question pairs:

### 1. Simple Approach
- **Feature Engineering**:
  - Applied Bag of Words to the columns `question1` and `question2`.
  - Added basic features:
    - `q1len`: Length of question1
    - `q2len`: Length of question2
    - `q1words`: Number of words in question1
    - `q2words`: Number of words in question2
    - `words_common`: Number of common words between question1 and question2
    - `words_total`: Total number of words in both questions
    - `words_share`: Ratio of common words to total words
- **Model**: Random Forest Algorithm

### 2. Advanced Approach
- **TOKEN Features**:
  - `cwc_min`: Ratio of the number of common words to the length of the smaller question
  - `cwc_max`: Ratio of the number of common words to the length of the larger question
  - `csc_min`: Ratio of the number of common stop words to the smaller stop word count among questions
  - `csc_max`: Ratio of the number of common stop words to the larger stop word count among questions
  - `ctc_min`: Ratio of the number of common tokens to the smaller token count among the two questions
  - `ctc_max`: Ratio of the number of common tokens to the larger token count among the two questions
  - `last_word_eq`: 1 if the last word of the two questions are the same
  - `first_word_eq`: 1 if the first word of the two questions are the same

- **Length Based Features**:
  - `mean_len`: Mean length of the two questions
  - `abs_len_diff`: Absolute difference between the lengths of the two questions
  - `longest_substring_ratio`: Ratio of the length of the longest common substring to the length of the smaller question

### 3. Model Training and Evaluation
- Trained a Random Forest model using the advanced features.
- Compared the accuracy of the Simple Approach, Basic Feature Engineering, and Advanced Approach.

## Results

The project concludes with a comparison of the accuracy of all three approaches, demonstrating the effectiveness of the advanced feature engineering techniques.
