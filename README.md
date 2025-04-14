# 🛡️ Enhancing Network Anomaly Detection – A Machine Learning Approach

This project presents an intelligent approach to **network anomaly detection** by addressing the core challenge of **class imbalance** in intrusion detection datasets. By combining advanced **resampling techniques** and **ensemble-based models**, this system boosts predictive accuracy and robustness—achieving a final accuracy of **96%** after hyperparameter optimization.

---

## 🧠 Objective

Cybersecurity datasets often suffer from **severely skewed class distributions**, where normal traffic significantly outweighs anomalous events. To counteract this, the project blends **oversampling** and **undersampling** strategies to rebalance the training data and improve the reliability of anomaly classification.

---

## ⚙️ Key Components

### 📈 Oversampling Strategies
These techniques artificially increase the number of rare (minority) class instances:

- **Random Oversampling**: Duplicates minority class records at random.
- **SMOTE (Synthetic Minority Over-sampling Technique)**: Generates synthetic samples between minority class neighbors.
- **ADASYN (Adaptive Synthetic Sampling)**: Focuses on harder-to-learn minority examples, producing data based on local distributions.

### 📉 Undersampling Strategies
These methods reduce the overwhelming majority class to balance the class ratio:

- **Random Undersampling**: Randomly removes majority class records.
- **NearMiss**: Retains majority class samples closest to minority instances, improving boundary learning.

---

## 🤖 Models Used

The following machine learning models were evaluated after rebalancing the dataset:

- **Random Forest**
- **Gradient Boosting Classifier**
- **Stacked Ensemble**: Combines multiple base models to generate stronger predictions.

📌 **Final Model**: A stacking ensemble provided the best performance, yielding a **96% accuracy** score after grid search-based hyperparameter tuning.

---

## 💻 Usage

The full pipeline is implemented in a Jupyter Notebook, covering:

- Data preprocessing & balancing
- Model training & evaluation
- Serialization of the best-performing model

### 🔍 Predicting with the Final Model:

```python
import pickle
model = pickle.load(open('final_model.pkl', 'rb'))
predictions = model.predict(new_data)

🧪 Results
Model	Accuracy	Notes
Random Forest	~93%	Strong baseline
Gradient Boosting	~94%	Improved generalization
Stacking Ensemble	96%	Best performance (final model)
📦 Deliverables
enhanced_anomaly_detection.ipynb: Full ML pipeline notebook

final_model.pkl: Serialized ensemble model for deployment

Visualizations & confusion matrices for all classifiers

📌 Summary
By rebalancing the training dataset using a smart fusion of over- and undersampling techniques and leveraging ensemble models, this project demonstrates a powerful solution to network intrusion detection challenges in imbalanced environments.
