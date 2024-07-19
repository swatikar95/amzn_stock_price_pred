Certainly! Here is the fixed version of your GitHub README page:

---

### Project Overview
This script contains a real-world stock price dataset (Amazon) collected from Yahoo Finance. I have applied three machine learning algorithms on this dataset: Logistic Regression, Decision Tree, and Random Forest.

### Method Overview

#### Logistic Regression
Suppose our dataset has two features $X_1$ and $X_2$ with target variable $`Y`$.
![Logistic Regression](image-3.png)

- **Parameters** (for simplicity, I am taking random values): 
    - Weights: $w_1 = 0.5$, $w_2 = 0.3$
    - Bias: $b = -2.5$

- **Linear Combination**: For each data point, compute the linear combination of the input features using the formula:
    $$z = w_1 \cdot X_1 + w_2 \cdot X_2 + b$$

    1. **Data point 1**: ($X_1 = 2$, $X_2 = 3$)
        $$z = 0.5 \cdot 2 + 0.3 \cdot 3 - 2.5 = -0.6$$
    2. **Data point 2**: ($X_1 = 6$, $X_2 = 8$)
        $$z = 0.5 \cdot 6 + 0.3 \cdot 8 - 2.5 = 2.9$$
    3. **Data point 3**: ($X_1 = 1$, $X_2 = 5$)
        $$z = 0.5 \cdot 1 + 0.3 \cdot 5 - 2.5 = -0.5$$
    4. **Data point 4**: ($X_1 = 7$, $X_2 = 2$)
        $$z = 0.5 \cdot 7 + 0.3 \cdot 2 - 2.5 = 1.6$$

- **Apply Sigmoid Function**:
    $$\sigma(z) = \frac{1}{1 + e^{-z}}$$

    1. **Data Point 1**: $z = -0.6$
        $$\sigma(-0.6) = \frac{1}{1 + e^{0.6}} = 0.3543$$ 
    2. **Data Point 2**: $z = 2.9$
        $$\sigma(2.9) = \frac{1}{1 + e^{-2.9}} = 0.9478$$ 
    3. **Data Point 3**: $z = -0.5$
        $$\sigma(-0.5) = \frac{1}{1 + e^{0.5}} = 0.3775$$ 
    4. **Data Point 4**: $z = 1.6$
        $$\sigma(1.6) = \frac{1}{1 + e^{-1.6}} = 0.8320$$ 

- **Predictions**: If the probability is greater than 0.5, predict $Y = 1$; otherwise, predict $Y = 0$.

#### Decision Tree
Constructs a model in the form of a tree structure to make decisions based on the input features.

![Decision Tree](image.png)

- **Root node selection**: Decide on the best feature to split the data at the root node. For simplicity, let's assume we choose $X_1$ as our first splitting feature.
- **Splitting data**: Choose a threshold value $X_1 = 5$ based on which we will split:
    - Left node: $X_1 \leq 5$, data points: (2,3,0), (1,5,0)
    - Right node: $X_1 > 5$, data points: (6,8,1), (7,2,1)
- **Leaf nodes**: Since the data points in each node are perfectly classified, we can create leaf nodes directly.

![Decision Tree Leaf Nodes](image-1.png)

- **Prediction**: If a new node comes with value (5,5), the model will predict $Y = 0$.

#### Random Forest
Based on Decision Tree but uses multiple trees. I will consider the same dataset for this one as well.
![Random Forest](image-2.png)

- **Bootstrap Samples**: Creates multiple subsets of the original dataset by sampling with replacement:
    - Sample 1: (2,3,0), (6,8,1), (2,3,0), (7,2,1)
    - Sample 2: (6,8,1), (1,5,0), (7,2,1), (6,8,1)
    - Sample 3: (1,5,0), (2,3,0), (7,2,1), (1,5,0)
- **Decision Tree Construction**: For each bootstrap sample, we build a decision tree:
    - **Tree 1 (from Sample 1)**:
        - Root Node: Split on $X_1 \leq 5$
        - Left Node: (2,3,0), (2,3,0) → $Y = 0$
        - Right Node: (6,8,1), (7,2,1) → $Y = 1$
    - **Tree 2 (from Sample 2)**:
        - Root Node: Split on $X_1 \leq 5$
        - Left Node: (1,5,0) → $Y = 0$
        - Right Node: (6,8,1), (7,2,1), (6,8,1) → $Y = 1$
    - **Tree 3 (from Sample 3)**:
        - Root Node: Split on $X_1 \leq 5$
        - Left Node: (1,5,0), (2,3,0), (1,5,0) → $Y = 0$
        - Right Node: (7,2,1) → $Y = 1$
- **Prediction**: For a new data point, (5,5):
    - Tree 1: $X_1 = 5 \leq 5$ → Left Node → Predicts $Y = 0$
    - Tree 2: $X_1 = 5 \leq 5$ → Left Node → Predicts $Y = 0$
    - Tree 3: $X_1 = 5 \leq 5$ → Left Node → Predicts $Y = 0$

Since all trees predict $Y = 0$, the final prediction for the data point (5,5) is $Y = 0$.

### Results
#### Logistic Regression

![Logistic Regression Results](output1.png)

#### Decision Tree Classifier

![Decision Tree Results](output2.png)

#### Random Forest Classifier

![Random Forest Results](output3.png)

Random Forest performed better as it can capture more complex situations than the other two algorithms.

---

This should render correctly on GitHub. Let me know if you need any further adjustments!