# Forecasting

Generally, the forecasting problem is to predict the future state of an object based on its observed state and other related information. Here we can fomulate the problem as follows:
$$x_{t+1} = f(x_t, r_t)$$
$x_{t+1}$ is the state in the future, $x_t$ is the observed state and $r_t$ is the related information.

Compared to other real-world problems, the forecasting problem has its own unique features:
* Periodicity: Time series data often can be decomposed into various components, such as trend, seasonality, and noise. Naturally, someone might raise a question "if we preidct the trend and seasonality, can we preidct time seires more accurately?"

* Unevenness: The observed data is not necessarily evenly spaced. Some time series data are irregular such as clinical data, where the time interval between two consecutive measurements is not fixed. Given this irregularity, some models may not be able to extract the pattern from data correctly like Vanilla convolutional neural network and recurrent neural network.

* Unstability: The distribution of time series data is not stable and the pattern behind the data changes over time. For example, a model trained on last month data may not be able to predict the next month data well. And practioneras might want a model is robust and efficient model training paradigm. Why more efficient training paradigm? Because we can utilize the lastest data to make better predictions. With unefficient training paradigm, we may not be able to train big and robust model.

From the above, we need to look for some ways to get the $f(*)$ mapping function from data. More specifically, we can use Fourier transform to extarct `Periodicity`, use Generative method to solve the `Unevenness` problem, and reply on transfer learning to make our network more robust and efficient.