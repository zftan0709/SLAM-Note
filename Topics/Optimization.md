# Optimization in Visual SLAM

Modern SLAM backend can be categorized into two types which are filter-based approach or graph/optimization-based approach. As the name suggests, the former method utilize the theory of Markov chain and propagates the states based on previous states. As for the optimization-based approach, the problem is modeled as a minimization of specific cost function, such as least square estimation.

## Least Square
In a graph-based SLAM, the pose and measurements can be visualized as the figure above where the rectangular block resembles constraints from measurements and each node representing target variable.
A more intuitive way of understanding the relationship of least square estimation and graph-based slam is that we are looking for the "best" target variable for the given measurements or constraints.
Therefore, it is important to understand the optimization process in graph-based SLAM.

<img src="http://chart.googleapis.com/chart?cht=tx&chl= F(x)=\frac{1}{2}\sum_{i=1}^{m}(f_i(x))^2" style="border:none;">

From the equation above, the cost function, _**F(x)**_ consists of _**m**_ residual functions _**f<sub>i</sub>(x)**_.
The residual functions can be the difference between an predicted value and actual measurements.
As mentioned before, we are seeking the optimum value of _**x**_ that will produce the lowest cost function.
In order to do so, we will first perform a taylor expansion.

<img src="http://chart.googleapis.com/chart?cht=tx&chl={F(x+\Delta{}x)=F(x)+J \Delta{}x + \frac{1}{2}\Delta{}x^TH\Delta{}x + ...}" style="border:none;">

## Reference [1] Y.He, X.Gao, C.Kun. Visual SLAM Online Course. shenlanxueyuan.com/my/course/225
