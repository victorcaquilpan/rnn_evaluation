# RNN Evaluation

In this repository, we use different RNN approaches to evaluate and compare their performance in the context of **Stock Market Prediction**. For this task, we implement **RNN**, **LSTM** and **GRU** architectures to do one-day ahead prediction (many-to-one problem) using different window slices. 

Moreover, this repository is divided in two parts. First part evaluate different RNN models, including results from a common statistical approach called **ARIMA**. For evaluation of models, **Mean Average Error (MAE)** is used. Second part, it dives in the implementation of different techniques to tackle different vanishing and exploding gradient problems.

## 1) Evaluation of models

The next table summarizes the results given by our models (RNN, LSTM and GRU). 

|Setting|MAE (Using 1 Stack layers)| Prediction (Using 1 Stack layers)|MAE (Using 3 Stack layers)| Prediction (Using 3 Stack layers)|
| ----- | --------- |-----| ----- | --------- |
|RNN, Sequence Lenght: 5| 7.55 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq5_stack1.PNG" width="300" height="200">|40.14 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq5_stack3.PNG" width="300" height="200">|
|RNN, Sequence Lenght: 15| 6.43 |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq15_stack1.PNG" width="300" height="200"> | 39.20 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq15_stack3.PNG" width="300" height="200">|
|RNN, Sequence Lenght: 30| 7.53| <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq30_stack1.PNG" width="300" height="200">| 41.08 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq30_stack3.PNG" width="300" height="200">|
|LSTM, Sequence Lenght: 5| 11.54 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq5_stack1.PNG" width="300" height="200">|17.76 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq5_stack3.PNG" width="300" height="200">|
|LSTM, Sequence Lenght: 15| 6.52 |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq15_stack1.PNG" width="300" height="200"> | 142.59 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq15_stack3.PNG" width="300" height="200">|
|LSTM, Sequence Lenght: 30| 8.2| <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq30_stack1.PNG" width="300" height="200">| 93.68 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/lstm/seq30_stack3.PNG" width="300" height="200">|

Codes are available in the next Jupyter notebooks.

* [RNN Models](https://github.com/victorcaquilpan/rnn_evaluation/blob/main/code/RNN_Models_Stock_Predictions.ipynb)



## 2) Tackling gradient problems

Considering previous results, we have seen that when we use a longer sequence (i.e. 50 days), **RNN** suffers of the vanishing gradient problem. So, we apply different techniques to tackle this problem, such as:

* **Use ReLU (activation function)**
* **Weights initialization**

In the next table we can see the performance of our RNN model using different techniques. We can see the prediction (in testing data) given in each case and its loss function and mean gradients values (given in training). Mean absolute error (MAE) in testing also is given. The results of these experiments are available in [this Jupyter notebook](https://github.com/victorcaquilpan/rnn_evaluation/blob/main/code/Facing_Gradient_Problems_Stock_Predictions.ipynb).

| Model | Technique |MAE| Prediction |Loss function|Mean gradients|
| ----- | --------- |-----|-------------|--------------|---|          
|RNN    | **Base model**  |40.65           |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_simple.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_simple.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_simple.PNG" width="300" height="200">|
|RNN    |  **Use ReLU (activation function)**  |23.46|<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_relu.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_relu.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_relu.PNG" width="300" height="200">|
|RNN    | **Weights initialization** |41.82 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_identity.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_identity.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_identity.PNG" width="300" height="200">|





