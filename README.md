# Digit Recognizer (MNIST)

---

---

# Overview

Correctly recognize handwritten images of digits. Use different models from regression to neural networks.

---

# Data

- train.csv
- test.csv

## Data Dictionary

Each image is 28x28 pixels, total of 784 pixels in total

- pixel-value (0~255) : Indicate the lightness or darkness of that pixel

## Training data

- The training data set has 785 columns. first column is the “label”, indicating the digit that was drawn by the user.
- The rest of the columns has a name like ***pixel$x$,*** where $x$ is an integer between **0 and 783**.

→ To map this pixel on the image, we have to decompose $x$ as 

$$
x = i * 28 + j
$$

⇒ ***pixel$x$*** is located on row $i$ and column $j$ of a 28x28 matrix

- Rows indicate different digits

## Submission type

```cpp
ImageId, Label
1,3
2,7
3,8
(...)
```

---

# Model

## 1st Submission

- Model : Logistic Regression

## 2nd Submission

- Model : MLP
    - ***28x28*** image is flattened into ***784-dimension vector***
    - ***Dense(256)→Dropout→Dense(128)→Dropout→Dense(10)***
        - **Dense (256)** : First hidden layer, 256 neurons
        - **Dropout (0.3)** : Prevent overfitting, randomly drop out 30% of the neurons during training
        - **Dense (128)** : Second hidden layer, 128 neurons
        - **Dropout (0.3)** : Same as before
        - **Dense (10)** : Output layer
    - **ReLU** in the hidden layers, **Softmax** in the output layer

## 3rd Submission

- Model : CNN

## 4th Submission

- CNN with additional 128-hidden layer + more epochs

---

# Results

| Model | Score |
| --- | --- |
| LogReg | 0.91642 |
| MLP | 0.97850 |
| CNN | 0.98900 |
| CNN2 | 0.99150 |