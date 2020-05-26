# Optimization in Visual SLAM

Modern SLAM backend can be categorized into two types which are filter-based approach or optimization-based approach. As the name suggests, the former method utilize the theory of Markov chain and propagates the states based on previous states. As for the optimization-based approach, the problem is modeled as a minimization of specific cost function, such as least square estimation.

<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
$$ F(x)=\frac{1}{2}\sum\_{i=1}^{m}(f(x\_i))^2 $$
</script>

## Reference
 [1] Y.He, X.Gao, C.Kun. Visual SLAM Online Course. shenlanxueyuan.com/my/course/225
