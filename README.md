# RNN Evaluation

In this repository, we use different RNN approaches to evaluate and compare their performance in the context of **Stock Market Prediction**. For this task, we implement **RNN**, **LSTM** and **GRU** architectures to do one-day ahead prediction (many-to-one problem) using different window slices. 

Moreover, this repository is divided in two parts. First part evaluate different RNN models, including results from a common statistical approach called **ARIMA**. For evaluation of models, **Mean Average Error (MAE)** is used. Second part, it dives in the implementation of different techniques to tackle different vanishing and exploding gradient problems.

## 1) Evaluation of models


## 2) Tackling gradient problems

Considering previous results, we have seen that when we use a longer sequence (i.e. 50 days), **RNN** suffers of the vanishing gradient problem. So, we apply different techniques to tackle this problem, such as:

* **Use ReLU (activation function)**
* **Weights initialization**

| Model | Technique | MAE |Loss function|Mean gradients|
| ----- | --------- |-----|-------------|--------------|          
|RNN    | **Base model**              |    ---          |     ---          |![Mean gradient simple](https://github.com/victorcaquilpan/rnn_evaluation/blob/main/images/mean_gradient_rnn_simple.PNG)|
|RNN    |  **Use ReLU (activation function)** |    ---          |     ---          |---|
|RNN    | **Weights initialization** |    ---          |     ---          |---|





