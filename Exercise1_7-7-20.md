# 7-7-20 Excercise 1

## Q1 In Laurence Maroney’s video, What is ML, he compares traditional programming with machine learning and argues that the main difference between the two is a reorientation of the rules, data and answers.  According to Maroney, what is the difference between traditional programming and machine learning?

In traditional programming you use rules you right and data to get answers. Machine learning takes data and answers to make a set of rules for predicting on future data.
This is useful in cases where the rules are not inherently apparent in a system, or where the data is too large to find it.
In fact, unsupervised learning is capable of sometimes identifying not only the rules for a set of data, but also the groups within it
that humans may not have been able to detect. 

## Q2 With the first basic script that Maroney used to predict a value output from the model he estimated (he initially started with 10 that predicted ~31.  Modify the predict function to produce the output for the value 7.  Do this twice and provide both answers.  Are they the same? Are they different?  Why is this so?

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
If I had set a random seed the answers might have been the same. The answers are near 
the same because models train by looking to minimize their loss function. Models trained with the same parameters are 
likely to fall in the same local minimum. This is't guaranteed, and models trained with the exact same code may get 
extrememly different results if the optimizer finds a different minimum the second time. 

## Q3 Using the script you produced to predict housing price, take the provided six houses and train a neural net model that estimates the relationship between them.  Based on this model, which of the six homes present a good deal?  Which one is the worst deal?  Justify your answer.

Moon is the worst deal, with my model predicting that you'd pay $109,710 than you should.
Hudgins was the best deal, with my model predicting that you'd pay $125,186 less than it should cost.

Comparisons calculated by subtracting predicted from actual price.
Comparison of data to actual values for worth:


|  House | Price discrepancy ($100,000)| 
|---|----|
| Moon | 1.0970985  |
| Church | 0.9491842 |
| Newptcomfort  | 0.06814122   | 
| Mobjack  |   -0.15081573 |
| Mathews  |        -0.38477302        |
| Hudgins  |        -1.2518587        |


If a house costs more than its predicted price I considered it to be a bad deal
