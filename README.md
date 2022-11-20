# RNN Evaluation

In this repository, we use different RNN approaches to evaluate and compare their performance in the context of **Stock Market Prediction**. For this task, we implement **RNN**, **LSTM** and **GRU** architectures to do one-day ahead prediction (many-to-one problem) using different window slices. 

Moreover, this repository is divided in two parts. First part evaluate different RNN models, including results from a common statistical approach called **ARIMA**. For evaluation of models, **Mean Average Error (MAE)** is used. Second part, it dives in the implementation of different techniques to tackle different vanishing and exploding gradient problems.

## 1) Evaluation of models

The next table summarizes the results given by our models (RNN, LSTM and GRU). 

|Model|Setting|MAE| Prediction|
| ----- | --------- |-----|-------------|
|RNN       |Sequence Lenght: 10, Stack layers: 2| 19.15 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq10_stack2.PNG" width="300" height="200">|
|RNN       |Sequence Lenght: 10, Stack layers: 5| 39.93 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq10_stack5.PNG" width="300" height="200">|
|RNN       |Sequence Lenght: 25, Stack layers: 2| 17.13 |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq25_stack2.PNG" width="300" height="200"> |
|RNN       |Sequence Lenght: 25, Stack layers: 5| 39.83 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq25_stack5.PNG" width="300" height="200">|
|RNN       |Sequence Lenght: 50, Stack layers: 2| 19.78 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq50_stack2.PNG" width="300" height="200">|
|RNN       |Sequence Lenght: 50, Stack layers: 5| 43.07 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/rnn/seq50_stack5.PNG" width="300" height="200">|

Codes are available in the next Jupyter notebooks.

* [RNN Models](https://github.com/victorcaquilpan/rnn_evaluation/blob/main/code/RNN_Models_Stock_Predictions.ipynb)



## 2) Tackling gradient problems

Considering previous results, we have seen that when we use a longer sequence (i.e. 50 days), **RNN** suffers of the vanishing gradient problem. So, we apply different techniques to tackle this problem, such as:

* **Use ReLU (activation function)**
* **Weights initialization**

In the next table we can see the performance of our RNN model using different techniques. We can see the prediction (in testing data) given in each case and its loss function and mean gradients values (given in training). Mean absolute error (MAE) in testing also is given. The results of these experiments are available in [this Jupyter notebook](https://github.com/victorcaquilpan/CNN_evaluation/blob/main/code/basic_cnn.ipynb).

| Model | Technique |MAE| Prediction |Loss function|Mean gradients|
| ----- | --------- |-----|-------------|--------------|---|          
|RNN    | **Base model**  |40.14           |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_simple.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_simple.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_simple.PNG" width="300" height="200">|
|RNN    |  **Use ReLU (activation function)**  |26.3|<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_relu.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_relu.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_relu.PNG" width="300" height="200">|
|RNN    | **Weights initialization** |43.78 | <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/prediction_rnn_identity.PNG" width="300" height="200">         |     <img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/loss_rnn_identity.PNG" width="300" height="200">        |<img src="https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_identity.PNG" width="300" height="200">|





