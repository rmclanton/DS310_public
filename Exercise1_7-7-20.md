#In Laurence Maroney’s video, What is ML, he compares traditional programming with machine learning and argues that the main difference between the two is a reorientation of the rules, data and answers.  According to Maroney, what is the difference between traditional programming and machine learning?

In traditional programming you use rules you right and data to get answers. Machine learning takes data and answers to make a set of rules for predicting on future data.

#With the first basic script that Maroney used to predict a value output from the model he estimated (he initially started with 10 that predicted ~31.  Modify the predict function to produce the output for the value 7.  Do this twice and provide both answers.  Are they the same? Are they different?  Why is this so?

//Code

```python
import tensorflow as tf
import numpy as np
from tensorflow import keras
model = keras.Sequential([keras.layers.Dense(units=1. input_shape=[1])])
model.compile(optimizer='sgd',loss="mean_squared_error")
xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype="float")
ys = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 4.0], dtype="float")
model.fit(xs,ys, epochs=500)
print(model.predict([7.0]))
```
