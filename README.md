# Binary-Classification-using-Tensorflow

## Terminology

* Batch Size</br>
  It is a hyperparameter which defines the number of samples the algorithm would work through before the internal parameters are updated.
* Epoch</br>
  Number of epochs reflects the number of iterations the learning algorithm will undergo while working through the entire dataset.
* Perceptrons</br>
  A machine learning construct usually used for classification tasks.
* Stochastic Gradient Descent</br>
  When the batch_size = 1.
* Batch Gradient Descent</br>
  When epoch = 1.

## Important considerations

* What should be the batch_size?
* Gradient descent vs stochastic gradient descent vs mini-batch gradient descent

## Common questions / issues
* Can we use np.mean instead of tf.reduce_mean? Is there a difference?</br>
  The functionality is the same. However, tf.reduce_mean would work only within a session.
  
  Try this:
   
  ```
  c = np.array([[3.,4], [5.,6], [6.,7]])
  print(np.mean(c,1))

  Mean = tf.reduce_mean(c,1)
  with tf.Session() as sess:
  result = sess.run(Mean)
  print(result)
    
  ```
  Output:
  
  ```
  [ 3.5  5.5  6.5]
  [ 3.5  5.5  6.5]
  ```
  
## Results
  | Batch size |    Cost       | Accuracy|
  |------------|---------------|---------|
  |    32      |  0.079790163  | 0.97696 |
  |    100     |  0.073474707  | 0.98096 |
  
  
## Checklist

- [x] Classification (normally distributed clusters)
- [ ] Plot learning curve of model vaildation error against training time
- [ ] Tune batch size and learning rate 
