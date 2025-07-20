# 🎧 Audiobook Subscription Prediction using TensorFlow

This project features a deep learning model designed to predict whether a customer will **convert** and purchase another audiobook after their initial purchase. It is a **binary classification** problem that leverages customer data to provide valuable business insights and improve targeted marketing strategies.

---

## 🎯 Project Objective

The primary goal is to classify customers into two categories:

- **Will Convert (Target = 1):** Customers who are likely to purchase again.  
  → Use loyalty programs or exclusive offers to retain them.

- **Will Not Convert (Target = 0):** Customers unlikely to return.  
  → Use different re-engagement strategies to win them back.

> By accurately predicting customer churn, the business can optimize marketing spend and increase customer retention rates.

---

## 🛠️ Workflow Overview

The project is divided into two main parts, handled in separate Jupyter notebooks:

### 1️⃣ Data Preprocessing (`TensorFlow_Audiobooks_Preprocessing.ipynb`)

- **Data Loading and Extraction:** Loaded from `Audiobooks_data.csv`.
- **Balancing the Dataset:** Removed extra rows from majority class (target = 0) to prevent model bias.
- **Feature Scaling:** Standardized all input features using `sklearn.preprocessing.scale`.
- **Shuffling and Splitting:** Data was shuffled and split into:
  - 80% Training
  - 10% Validation
  - 10% Test
- **Saving:** Saved as `.npz` files:  
  `Audiobooks_data_train.npz`, `Audiobooks_data_validation.npz`, and `Audiobooks_data_test.npz`.

---

### 2️⃣ Model Building & Training (`TensorFlow_Audiobooks_Model.ipynb`)

- **Model Architecture:** Built using TensorFlow & Keras Sequential API:
  - Input Layer: 10 features
  - 2 Hidden Layers: 60 neurons each, ReLU activation
  - Output Layer: 2 neurons, Softmax activation

- **Compilation:**
  - Optimizer: `adam`
  - Loss: `sparse_categorical_crossentropy` (for integer targets)

- **Training:**
  - Epochs: Max 100
  - Batch Size: 100
  - Early Stopping: Patience = 1 (training stopped after 9 epochs)

---

## 📊 Results

| Metric        | Value        |
|---------------|--------------|
| **Test Loss** | 0.35         |
| **Accuracy**  | 82.37%       |

The model can correctly predict customer behavior with over **82% accuracy**, making it valuable for retention strategies and marketing optimization.

---

## 💻 Technologies Used

- Python  
- TensorFlow / Keras  
- NumPy  
- Scikit-learn (for preprocessing)

---

## 🚀 How to Run

1. **Clone this repository**:
   ```bash
   git clone https://github.com/yourusername/audiobook-subscription-prediction.git
   cd audiobook-subscription-prediction
