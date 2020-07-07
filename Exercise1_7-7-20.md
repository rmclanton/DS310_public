#Q1 In Laurence Maroney’s video, What is ML, he compares traditional programming with machine learning and argues that the main difference between the two is a reorientation of the rules, data and answers.  According to Maroney, what is the difference between traditional programming and machine learning?

In traditional programming you use rules you right and data to get answers. Machine learning takes data and answers to make a set of rules for predicting on future data.

#Q2 With the first basic script that Maroney used to predict a value output from the model he estimated (he initially started with 10 that predicted ~31.  Modify the predict function to produce the output for the value 7.  Do this twice and provide both answers.  Are they the same? Are they different?  Why is this so?

```python
import tensorflow as tf
import numpy as np
from tensorflow import keras
model = keras.Sequential([keras.layers.Dense(units=1, input_shape=[1])])
model.compile(optimizer='sgd',loss="mean_squared_error")
xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype="float")
ys = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 4.0], dtype="float")
model.fit(xs,ys, epochs=500)

print(model.predict([7.0]))
```
First run:  10.137107
Second run: 10.136513

The answers are different because the neural network is retrained and fit on the data. 
If I had set a random seed the answers might have been the same

#Q3 Using the script you produced to predict housing price, take the provided six houses and train a neural net model that estimates the relationship between them.  Based on this model, which of the six homes present a good deal?  Which one is the worst deal?  Justify your answer.

Moon is the worst deal, with my model predicting that you'd pay $109,710 than you should.
Hudgins was the best deal, with my model predicting that you'd pay $125,186 less than it should cost.
