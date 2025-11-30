# Machine Learning Project – Mobile Price Classification

Machine learning is a method where computers learn patterns from data without being explicitly programmed.  
This project aims to build and compare different ML models to classify mobile phones into **four price categories (0–3)** using their features.

---

## 🛠 Steps Performed

I have performed it into four steps:

1. Training Without Splitting the Dataset
2. Train/Validation Split
3. Decision Tree with max_leaf_nodes Tuning
4. Random Forest Model

---

### 1. Training Without Splitting the Dataset

First, the model is trained using the entire dataset without separating it into training and validation sets.  
This helps to understand the model behaviour. But it is not reliable because when we try to predict the values, we do not have new data to cross check the results.

### 2. Train/Validation Split

As we need the data to check the results of the computer, we split the data into two categories:  

- **Training data** – for learning the patterns  
- **Validation data** – for testing the model on unseen data  

### 3. Decision Tree with max_leaf_nodes Tuning

Now, we can check the model’s accuracy. So, we are moving to tune the model (Decision Tree Regressor). To tune the model, we need to know about the **underfitting** and **overfitting** concepts.
In a Decision Tree Regressor, the data is repeatedly split into two groups at each step. As the tree grows, these splits create many “leaf nodes,” which are the final decision points of the tree. The number of leaf nodes can grow like \(2^n\) as the tree becomes deeper.

By adjusting **max_leaf_nodes**, we control how big or small the tree can grow.  
A very large number of leaf nodes can make the model overfit, and a very small number can make it underfit. When testing different leaf counts, the accuracy sometimes increases or decreases in an irregular pattern. So, we need to find a good balance where both training accuracy and validation accuracy are reasonable.

To do this, I used a loop to test different values of **max_leaf_nodes**, found the value that gave the best performance, and used it to train the final model.

### 4. Random Forest Model

A Random Forest is a machine learning method that uses **many decision trees** instead of just one. Each tree learns slightly different patterns, and when they all make a prediction, the forest combines their results to give a final answer.  

Random Forest is usually **more accurate**, **more stable**, and **less likely to overfit** than a single decision tree because many trees “vote” together.

### To compare the performance of these models, I used MAE (Mean Absolute Error) as the evaluation metric. It tells how far the model’s predictions are from the actual values on average.
