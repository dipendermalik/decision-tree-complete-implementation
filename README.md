# Decision Tree Implementation (Classification & Regression)

## Project Overview
This repository demonstrates the complete implementation of **Decision Tree Algorithms** for both:

- **Classification**
- **Regression**

The project covers:
- Theory (Entropy, Gini, Variance Reduction)
- Model Building
- Pre-Pruning & Post-Pruning
- Hyperparameter Tuning (Grid Search & Random Search)
- Model Evaluation
- Visualization of Decision Trees

The objective is to understand how Decision Trees work internally and how to optimize them for better generalization.

---

## Concepts Covered

### 1. Decision Tree for Classification
Decision Tree Classifier works by splitting the dataset based on feature values to maximize class separation.

#### Key Concepts:
- **Entropy**
- **Gini Impurity**
- **Information Gain**
- **Pure vs Impure Splits**

📌 Entropy/GINI impurity measure uncertainty and helps in selecting the best split. Information gain helps to determine which feature is use to start splitting.

#### Entropy Formula:
```python
H(S) = -p₁ log₂(p₁) - p₂ log₂(p₂)
```
#### Gini Impurity:
```python
Gini = 1 - Σ(pᵢ²)
```
#### Information Gain:
```python
Gain(S, F) = H(S) - Σ (|Sᵥ| / |S|) * H(Sᵥ)
```
---

### 2. Decision Tree for Regression
Decision Tree Regressor predicts continuous values using **variance reduction**.

#### Key Concepts:
- Mean Squared Error (MSE)
- Variance Reduction

📌 The model splits data to minimize variance within nodes.

#### Variance Formula:
```python
Variance = (1/n) Σ (yᵢ - ȳ)²
```
#### Variance Reduction:
```python
VR = Var(parent) - Σ (weight_child * Var(child))
```

---

### 3. Splitting for Numerical Features
For numerical variables:
- Values are sorted
- Multiple thresholds are tested
- Best split is selected based on Information Gain / Variance Reduction


---

## Implementation Details

### 1. Model Building

- DecisionTreeClassifier
- DecisionTreeRegressor

---

### 2. Pre-Pruning Techniques

- `max_depth`
- `min_samples_split`
- `min_samples_leaf`
- `max_features`

Helps prevent overfitting by restricting tree growth.

---

### 3. Post-Pruning (Cost Complexity Pruning)

- `ccp_alpha`

Used to prune fully grown trees:
- Removes weak splits
- Improves generalization

---

### 4. Hyperparameter Tuning

#### Grid Search
- Exhaustive search
- Finds optimal parameters

#### Random Search
- Faster than Grid Search
- Efficient for large parameter spaces

---

## Model Evaluation Metrics

### Regression Metrics
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score
- Adjusted R²

### Classification Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

## Results & Insights

### Overfitting in Decision Trees
- Default tree achieves:
  - **Train Score = 1.0**
  - Poor test performance
- Reason:
  - Tree memorizes data (high variance)

### Optimal Model Behavior
- After pruning:
  - Train and Test performance become balanced
  - Generalization improves

### Key Learning
- Decision Trees are:
  - High variance models
  - Sensitive to noise
- Pruning is essential

---

## Visualization

### Tree Plot
- Visual representation of splits
- Shows:
  - Feature selection
  - Threshold values
  - Predictions

### Alpha vs Error Plot
- Helps find optimal `ccp_alpha`
- Trade-off between:
  - Model complexity
  - Performance

---

## Feature Importance

Decision Trees provide:
- Feature importance scores
- Helps in:
  - Feature selection
  - Model interpretability

---

## Key Takeaways

- Decision Trees are easy to interpret but prone to overfitting
- Pre-pruning and post-pruning are critical
- Entropy and Gini help in classification
- Variance reduction is used in regression
- Ensemble methods (Random Forest, Gradient Boosting) improve performance significantly

---

## Future Improvements

- Implement Random Forest
- Implement Gradient Boosting (XGBoost, LightGBM)
- Cross-validation optimization
- Feature engineering
- Model deployment using Flask/FastAPI

---

