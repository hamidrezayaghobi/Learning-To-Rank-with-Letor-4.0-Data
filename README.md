# Learning To Rank LTR models for [Letor 4.0](https://www.microsoft.com/en-us/research/project/letor-learning-rank-information-retrieval/letor-4-0/) Dataset (MQ2007).

## Summary
In this project, we try to use the LTR application for the MQ2007 dataset of letor 4.0 with **Point-Wise** and **Pair-Wise** approaches. In the first step, we prepare the MQ2007 dataset and then implement these two approaches.

## Data-Preparation:
1. Normalization: Using sklearn.preprocessing.StandardScaler
2. Dimensionality Reduction: Using sklearn.decomposition.PCA algorithem
3. Deal With Class-Imbalance: Using imblearn.over_sampling.SMOTE 

## 1-Point-Wise:

### 1-1 Models
1. **Closed Form**: calculate the optimum weights vector of linear regression.
2. **Dummy Model**: constantly predicts the labels regarding the most frequent train label.
3. **Simple Model**: trained on original data using Stochastic Gradient Descent
4. **Best Model**: used data normalizing, feature reduction, and oversampling for training using Stochastic Gradient Descent to achieve better generalization

### 1-2 Results:
| Model | Accuracy |
|  :--------:  | :------: |
|  CLOSED_FROM | 0.7562   |
|  DUMMY_MODEL | 0.7536   |
| SIMPLE_MODEL | 0.7566   |
|  BEST_MODEL  | 0.5406   |

### 1-3 Conclusion:
At the evaluation step, for the Dummy and the Simple models, we got the same accuracy as Closed-form. It's because of having a high percentage of 0s in train labels. Besides that, having less accuracy in our Best model compared to the other models doesn't necessarily mean that they are more powerful models to use. On the other hand, our Best model has better generalization due to oversampling and handles less probable data.


## 2-Pair-Wise:

### 2-1 Model
1. **Logistic Regression**

### 2-2 Results:
| Model | Accuracy |
|  :--------:  | :------: |
|  LOGISTIC_REGRESSION | 0.7077   |

## 3 Conclusion:
Pairwise approaches work better in practice than pointwise approaches because predicting relative order is closer to the nature of ranking than predicting class label or relevance score.
