# Implementing-Support-Vector-Machine
## Task
Build a Support Vector Machine Classifier from scratch.
## SVM Classifier
### Terms for SVM are
- **Hyperplane**: plane dividing the data Points
- **Support Vectors**: Nearest points to the Hyperplane. If these points changes Hyperplane changes
- **Margin**: Distance between the two set of datas
- Linearly Separatable data
- **Hinge Loss** is used for calculating Loss function
- **SVM Kernels**: Changes the dimensions of the dataset to higher number if required
### Equation of the Hyperplane
**y = wx - b**</br>
y: Target</br>
x: Features</br>
w: Weight</br>
b: Bias</br>
### Gradient Descent
**w = w - L*dw**</br>
**b = b - L*db**</br>
L: Learning Rate</br>
dw and db have 2 different equation depending on the condition **y.(wx+b) >= 1** if True:</br>
<b>dw = 2* lambda * w</b></br>
**db = 0**</br>
lambda: value given manually</br>
if condition false:</br>
<b>dw = 2* lambda - y*x</b></br>
**db = y**</br>
PS: the value of x and y are taken for particular single points.
## Building the SVM Classifier
- Initiating the Hyperpermeter: Learning rate, Number of Iterations, lambda
- Fitting the dataset to the CLassifier
  1. Get the Number of row i.e number of records(m) and The number of columns i.e number of features(n)
  2. Intializing the weight and Bias values
  3. Implement Gradient Descent for Optimization
- Updating the Weight and Bias(Model Parameters)
  1. Label Encoding: change the value of y to -1 if less than 0 else to 1
  2. Getting the value for dw and db (Gradient) according to the condition y.(wx*b) >= 1
- Predict the Label and return the ouput for the given Input
## Implementing the SVM Classifier
### Import the Dependencies
Libraries necessary for the task are:
- NumPy
- Pandas
- Standard Scaler
- Train_test_Split from sklearn
- Accuracy score from sklearn
### Data Collection and Preprocessing
- Load the CSV file to pandas data frame using read_csv function
- Analyse the data using functions head, shape and describe
- Split the features and Target such that Target contains only 'Outcome' column and features containing rest of the column
- Perform Data Standardization using Standard Scaler library
### Model Building and Evaluation
- Split the data into Training and test data
- Load the built model and define the hyper parameters learning rate, number of iterations and lambda
- Fit the model according to the training data
- Model Evaluation: done on both Training and test data
  1. Accuracy Score of Training data:  0.7768729641693811
  2. Accuracy Score of Test data:  0.7532467532467533
### Build a Predictive System
- Take random data from the dataset
- Convert it to numpy array and reshape it to 2 dimension
- Perform Standardization
- Feed it to the built model
- Predict and print the Outcome</br></br></br>

Reference: 7.3.7. Implementing Support Vector Machine Classifier from Scratch in Python, Siddhardhan, https://www.youtube.com/watch?v=5egiXYde6PY&list=PLfFghEzKVmjsNtIRwErklMAN8nJmebB0I&index=102
