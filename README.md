# **Overview of the Water Quality Dataset**
The dataset contains measurements related to water quality and potability, with each row representing a water sample. The Potability column indicates whether the water is suitable for human consumption. The dataset includes various features such as pH, Hardness, Solids, Chloramines, Sulfate, Conductivity, Organic Carbon, Trihalomethanes, and Turbidity.

### **Member Model**
1. Geu Aguto Garang - Regularized Deep Neural Network (DNN) with Adam optimizer, L2 Regularization 
2. Abubakar Ahmed - Lightweight ANN with RMSprop Optimizer
3. Peris Wangui - CNN with Stochastic Gradient Descent (SGD) Optimization
### **Link to presentation video** 
https://youtu.be/ZgAOLtiVAMM?si=I2ej-UOWdjyi0tlT

# **Data Quality and Preprocessing**
In this project, we are using google colab where most of the data loading packages are being installed by default.
We will load the dataset using pandas library and perform initial exploratory data analysis to understand the dataset.

- The dataset contained missing values in several columns, notably in pH and Sulfate, which were addressed by
filling these gaps with the mean of their respective columns. This approach ensured that the dataset remained intact
without losing valuable information.
- Outliers were identified in the Solids feature through boxplots. However, they were retained to preserve data integrity,
  allowing the model to capture all potential patterns essential for accurate predictions.

# **Data Visualization**
In this section, we performed data visualization to understand the distribution of the features in the dataset.
We used `matplotlib` and `seaborn` libraries for data visualization as imported in the colab.

### **1. Correlation Heatmap:**
The heatmap generated using Seaborn provided a visual representation of the correlations between
various features in the dataset. 
Each feature's relationship with others was assessed, showing that no two or more variables were strongly correlated. 
This suggests that all features contribute unique information to the model, reducing the need for dimensionality reduction techniques.

<img width="732" alt="Image" src="https://github.com/user-attachments/assets/0e3d1047-396b-409a-a5bc-c2edeba1df86" />


###  **First Model: Regularized Deep Neural Network (DNN) with Adam optimizer, L2 Regularization**
The model trained on water potability predictions is increasing smoothly in accuracy over the epochs, while it is overfitting at the same time after a certain point in the process.

Key Highlights of the Training:

### **Model Architecture:**
Input Layer: A dense input layer with 128 units and ReLU activation, since the number of features in the data is that much.
Hidden Layer: Comprise one dense layer of 64 units with ReLU activation.
Output Layer: One unit, Sigmoid activation, the task is to provide binary predictions about water potability.
### **Training Progress:**
A decent start where initial accuracies lie in the range of 0.59 and quickly get into the range of 0.70-0.80.

**Overall Best Performance:** Somewhere in epoch 30-35, where training accuracy goes up towards 77-80%, the validation accuracy stays around 69-70%.

**Overfitting Signs:** After the 35th epoch, the validation loss starts to be stuck, or even slightly increase, while the accuracy of training continuously improves-this is a surefire sign of overfitting.

<img width="555" alt="Image" src="https://github.com/user-attachments/assets/3bf9b63f-9f18-4fc9-94e5-b984f79cc873" />

### **Validation Performance:**
The validation accuracy was hovering between 66 and 70%, and hence proved moderate generalization on unseen data but could not show further consistent improvement.
The graph for validation loss did not keep on falling and showed a slight increase toward the later epochs, thus cementing the overfitting signs.

### **Possible Improvements:**
**Early Stopping:** It would be beneficial to avoid overfitting by early stopping, when the validation loss stops improving.
**Regularization:** Overfitting could be prevented by the addition of L2 regularization or dropout.

### **Second model: Lightweight ANN with RMSprop Optimizer**

**- Optimization & Training Strategy Optimizer**: RMSprop (learning rate = 0.001) Loss Function: Binary Crossentropy Regularization: Dropout (0.3 – 0.5) for generalization Callbacks: Early Stopping: Stops training if validation loss doesn’t improve after 5 epochs ReduceLROnPlateau: Adjusts learning rate dynamically

**- Model Architecture Input Layer**: 128 neurons (ReLU activation) Dropout: 30% to reduce overfitting Output Layer: 1 neuron (Sigmoid activation for binary classification)
However it had a very little impact on the validation accuracy and significantly reduced the training accuracy.

**- Model Evaluation & Performance Test Accuracy**: 69.5% F1 Score: 0.67 (Weighted) Precision: 0.69, Recall: 0.70 Confusion Matrix Analysis: Potable Water Detection: Recall = 37% (Needs improvement) Non-Potable Water Detection: Recall = 89% (Good detection)

**Confusion Matrix for model explained above:**

<img width="555" alt="Image" src="https://github.com/user-attachments/assets/96b566d6-7ec0-46d4-a81f-fce761de26ac" />

### **Third Model: CNN with Stochastic Gradient Descent (SGD) Optimization**

###**Training Progress:** Changing the optimiser for L1 only improved the model performance by 2%. which is not significant enough but it goes to show that sometimes changing the optimiser can help.

### **Model Evaluation & Performance Test Accuracy:** 69.5% F1 Score: 0.67 (Weighted) Precision: 0.59, Recall: 0.78 Confusion Matrix Analysis: Potable Water Detection: Recall = 47% (Needs improvement) Non-Potable Water Detection: Recall = 89% (Good detection)

**Confusion Matrix for model above:**

<img width="555" alt="Image" src="https://github.com/user-attachments/assets/e094f471-6d45-49f5-870f-48c87cf2baff" />

As we can see, the confusion matrix did not change compared to the previous one.

### **Model with L2 Regularization and Adam Optimizer comparsion **

In this model, L2 regularization was applied to combat overfitting, using the Adam optimizer for efficient weight updates. Key findings while tuning the learning rate were:

i) Higher Learning Rate: The model trained faster with fewer epochs, but larger weight updates risked overshooting the optimal point, leading to premature early stopping.

ii) Lower Learning Rate: The model trained slower, requiring more epochs but resulted in smoother convergence and more stable training.
The overall overview is that the model results and accuracy did not differ from the previous model as the confusion matrices are almost identical. 


### <u>Authors and Contributors</u>

- Geu Aguto Garang - g.bior@alustudent.com
- Abubakar Ahmed - a.ahmed1.@alustudent.com
- Peris Wangui - p.wangui@alustudent.com
