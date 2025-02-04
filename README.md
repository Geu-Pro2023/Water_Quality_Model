Water Quality Model assignments


**🔹 Lightweight ANN for Classification**

**1️⃣ Model Architecture**
Input Layer: 128 neurons (ReLU activation)
Dropout: 30% to reduce overfitting
Output Layer: 1 neuron (Sigmoid activation for binary classification)

**2️⃣ Optimization & Training Strategy**
Optimizer: RMSprop (learning rate = 0.001)
Loss Function: Binary Crossentropy
Regularization: Dropout (0.3 – 0.5) for generalization
Callbacks:
Early Stopping: Stops training if validation loss doesn’t improve after 5 epochs
ReduceLROnPlateau: Adjusts learning rate dynamically


**3️⃣ Model Evaluation & Performance**
Test Accuracy: 69.5%
F1 Score: 0.67 (Weighted)
Precision: 0.69, Recall: 0.70
Confusion Matrix Analysis:
Potable Water Detection: Recall = 37% (Needs improvement)
Non-Potable Water Detection: Recall = 89% (Good detection)

**📌 Training Summary Table**
| Optimizer | Dropout | Accuracy | F1 Score | Recall | Precision |
|-----------|---------|----------|----------|--------|-----------|
| RMSprop   | 0.5     | 69.5%    | 0.67     | 0.70   | 0.69      |

**🔹 Developed by: Abubakar Ahmed**
