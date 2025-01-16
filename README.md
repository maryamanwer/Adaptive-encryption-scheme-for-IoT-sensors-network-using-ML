# Adaptive Encryption Scheme for IoT Sensor Networks

This project implements an adaptive encryption scheme for IoT sensor networks that dynamically selects encryption methods based on data criticality. It uses machine learning to classify network traffic as low-critical (benign) or high-critical (malicious) and applies XOR encryption for low-critical data and homomorphic-like encryption for high-critical data.

## Features
- **Data Classification:** Logistic Regression model to classify IoT network traffic.
- **Adaptive Encryption:** XOR for low-critical and simulated homomorphic encryption for high-critical data.
- **Batch Processing:** Efficient encryption of data in batches.
- **Validation:** Validation process to ensure correct classification and encryption.
- **Visualization:** Confusion matrix, ROC curve, and feature importance plots.

## Dataset
- **Source:** N-BaIoT dataset
- **Files Used:**
  - `1.benign.csv` (Benign traffic)
  - `1.mirai.syn.csv` (Malicious traffic)

## Installation
```bash
pip install pandas sklearn numpy matplotlib seaborn
```

## Usage
1. **Load and Preprocess Data**
```python
benign = pd.read_csv('/nbaiot-dataset/1.benign.csv')
malicious = pd.read_csv('/nbaiot-dataset/1.mirai.syn.csv')
```

2. **Train Model**
```python
model = LogisticRegression(random_state=0)
model.fit(x_train_scaled, y_train)
```

3. **Run Adaptive Encryption**
```python
encrypted_data = adaptive_encryption(x_test, model, scaler, features, batch_size=50)
```

4. **Validate Process**
```python
correct, incorrect = validate_encryption_process(data_subset, labels_subset, model, scaler, features)
```

5. **Visualize Results**
```python
plt.figure(figsize=(8, 6))
sns.heatmap(conf_matrix, annot=True, fmt='d', cmap='Blues')
plt.show()
```

## Results
- **Model Accuracy:** 99.97%
- **ROC AUC:** 1.00
- **Confusion Matrix:** Very few misclassifications

## License
This project is licensed under the MIT License.

## Contact
For any inquiries, please contact maryam.anwer2@gmail.com.
