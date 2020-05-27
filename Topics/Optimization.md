# Optimization in Visual SLAM

Modern SLAM backend can be categorized into two types which are filter-based approach or graph/optimization-based approach. As the name suggests, the former method utilize the theory of Markov chain and propagates the states based on previous states. As for the optimization-based approach, the problem is modeled as a minimization of specific cost function, such as least square estimation.

## Least Square Estimation
In a graph-based SLAM, the pose and measurements can be visualized as the figure above where the rectangular block resembles constraints from measurements and each node representing target variable.
A more intuitive way of understanding the relationship of least square estimation and graph-based slam is that we are looking for the "best" target variable for the given measurements or constraints.
Therefore, it is important to understand the optimization process in graph-based SLAM.

![Cost Function](./Images/optimization1.png)

From the equation above, the cost function, _**F(x)**_ consists of _**m**_ residual functions _**f<sub>i</sub>(x)**_.
The residual functions can be the difference between an predicted value and actual measurements.
As mentioned before, we are seeking the optimum value of _**x**_ that will produce the lowest cost function.
In order to do so, several options are available to solve this non-linear least square problem such as _**gradient descent**_, _**Newton's method**_, _**Gauss-Newton**_, and _**Levenberg-Marquardt algorithm**_.
___
## Gradient Descent
Similar to other methods mentioned above, gradient descent is an iterative method to solve non-linear least square problem. Just like the name suggests, this method search for a "direction" to minimize the cost function. A more intuitive way of visualizing it is to think of the gradient of the cost function as the opposite "direction" and incrementally adjust the target variables towards it until convergence occurs.
First order Taylor expansion is first performed on the cost function.

![First Order Taylor Expanded Cost Function](./Images/optimization2.png)

The Jacobian matrix, _**J**_ is the partial deriavative of the function _**F(x)**_ with respecto to variable _**x**. Since only the first order expansion is performed, the desired descent direction will be negative gradient which is _**-J**_ in this case. Next, we will have to decide how large is the step, _**λ**_ that we would like to take for each iteration. This so called step or learning rate in nomenclature of deep learning or machine learning is a hyperparameter that required to be tuned. 

Cons:
* Will oscillates around the optimal point.
* Slow converging speed.

## Newton's Method
Instead of first order Taylor expansion, the second order expansion term is kept in Newton's Method
![Second Order Taylor Expanded Cost Function](./Images/optimization3.png)
![Newton's Method](./Images/optimization4.png)
## Reference
[1] Y.He, X.Gao, C.Kun. Visual SLAM Online Course. shenlanxueyuan.com/my/course/225
