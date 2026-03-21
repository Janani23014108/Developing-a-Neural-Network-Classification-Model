# Developing a Neural Network Classification Model

## AIM
To develop a neural network classification model for the given dataset.

## THEORY
An automobile company has plans to enter new markets with their existing products. After intensive market research, they’ve decided that the behavior of the new market is similar to their existing market.

In their existing market, the sales team has classified all customers into 4 segments (A, B, C, D ). Then, they performed segmented outreach and communication for a different segment of customers. This strategy has work exceptionally well for them. They plan to use the same strategy for the new markets.

You are required to help the manager to predict the right group of the new customers.

## Neural Network Model

![547513375-dd5f490b-4ea3-4abe-9eb0-496ce50e2dce](https://github.com/user-attachments/assets/23c18e1b-8766-4f21-b077-ed5af5e8e446)

## DESIGN STEPS
### STEP 1: 

Load and Preprocess Data

### STEP 2: 
Feature Scaling and Data Split


### STEP 3: 

Convert Data to PyTorch Tensors

### STEP 4: 
Define the Neural Network Model


### STEP 5: 

Train the Model

### STEP 6: 
Evaluate and Predict




## PROGRAM

### Name:J.JANANI

### Register Number: 212223230085

```python
# Define Neural Network(Model1)
class PeopleClassifier(nn.Module):
    def __init__(self, input_size):
        super(PeopleClassifier, self).__init__()
        self.fc1=nn.Linear(input_size,32)
        self.fc2=nn.Linear(32,16)
        self.fc3=nn.Linear(16,8)
        self.fc4=nn.Linear(8,4)

    def forward(self, x):
        x=F.relu(self.fc1(x))
        x=F.relu(self.fc2(x))
        x=F.relu(self.fc3(x))
        x=self.fc4(x)
        return x

     
        
# Initialize the Model, Loss Function, and Optimizer

model =PeopleClassifier(input_size=X_train.shape[1])
criterion =nn.CrossEntropyLoss()
optimizer =optim.Adam(model.parameters(),lr=0.001)
# Training Loop
def train_model(model, train_loader, criterion, optimizer, epochs):
  model.train()
  for epoch in range(epochs):
    for inputs,labels in train_loader:
      optimizer.zero_grad()
      outputs=model(inputs)
      loss=criterion(outputs,labels)
      loss.backward()
      optimizer.step()

    if (epoch + 1) % 10 == 0:
        print(f'Epoch [{epoch+1}/{epochs}], Loss: {loss.item():.4f}')


```

### Dataset Information


### OUTPUT

## Confusion Matrix
<img width="748" height="577" alt="Screenshot 2026-02-23 204736" src="https://github.com/user-attachments/assets/662fad12-69d7-430e-8d54-352820a05b75" />


## Classification Report

<img width="661" height="427" alt="image" src="https://github.com/user-attachments/assets/ab209489-4625-405b-9746-e732b29308ea" />

### New Sample Data Prediction
<img width="377" height="105" alt="image" src="https://github.com/user-attachments/assets/c040db25-ce6c-4ab7-947e-887d889d4527" />


## RESULT

This program has been executed successfully
