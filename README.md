# shapley-the-brute
poor &amp; inefficient implementation of the shapley method for simple functions

This repo implements Shapley allocation for functions with one input and one output.
The specific use case provided is a sigmoid, where a collection of elements are summed
(to form x) and generate an output (y).

For example, given x = [1,1] and y = sigmoid(np.sum(x)), the contributions of
x[0] and x[1], with respect to the output y, is x_contrib = ~[0.19, 0.19].

[Shapley values](https://en.wikipedia.org/wiki/Shapley_value) have a several great properties,
one of which is that that contributions will sum to the output. From the previous example,
x_contrib[0] + x_contrib[1] + sigmoid(0) = 0.88, which also equals sigmoid(1+1). Sigmoid of 0
must be considered as it represents the null set, or equivalently, E[f(x)].

Note, this implementaion is far from optimal and, furthermore, computing Shapley for most problems is intractible.
Also, a linear mapping function has been added to compare with the results of Shapley,
to understand the degree to which the comparitive fit is linear.
