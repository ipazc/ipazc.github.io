---
layout: page
title: DeepEvolution
description: An Evolution Algorithm Implementation for TensorFlow Keras Models
img: assets/img/deepevolution.png
importance: 2
category: Artificial Intelligence
featured: true
---

The **DEEPEVOLUTION** project offers an implementation of an evolutionary algorithm for TensorFlow Keras models. It provides a solution for scenarios where differentiable loss functions are not applicable.

## Installation

You can install DEEPEVOLUTION using pip:

```bash
$ pip install deepevolution
```

It requires TensorFlow > 2.0.0

## USAGE EXAMPLE

After importing the package and TensorFlow Keras models, the `fit_evolve()` method can be easily utilized for evolutionary training:

```python
from tensorflow.keras.models import Model
from deepevolution import wrap_keras

wrap_keras()

# ... Build a Keras model `model`...

keras_model.fit_evolve(x_train, y_train, max_generations=100)
```

By default, the fitness function is the negative loss function of the model, which must be compiled. For different fitness functions, check the ADVANCED section at the official documentation in [GitHub](https://github.com/ipazc/deepevolution).



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/deepevolution.jpg" title="Loss vs Accuracy while training" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The evolution of the loss compared to the evolution of the accuracy while training a network with this package.
</div>


## Under-the-Hood

The evolution process involves the following steps:

1. **Network Duplication:** The network's weights are duplicated to create a population of N networks (default is 16). Each individual network is distinguished by adding noise sampled from a normal distribution (default std=0.3) to each weight.

2. **Weight Evaluation:** Weights are evaluated by applying them to the fitness function along with the training data. This fitness function assesses how well the network's weights perform with the given data and is fully customizable.

3. **Elitism:** The top_k (default 4) models are selected for reproduction from the population, and the rest are discarded.

4. **Crossover:** Crossover occurs between pairs of top models. Each model's weights are combined with subsequent models until all combinations are met. The crossover consists of merging 50% of one model's weights with 50% of another's, plus applying random mutations sampled from a normal distribution to a % of the weights (default 20%).

5. **Generation Update:** The generated models after crossover are combined with the top_k from the previous generation to create a new generation, which can be evolved again.

DEEPEVOLUTION's flexibility makes it suitable for reinforcement learning problems, as it allows the definition of fitness functions that evaluate the model's performance for various tasks.

## REFERENCES

You can find this project's website at the following links:

 * Source code: [GitHub](https://github.com/ipazc/deepevolution/)
 * PyPI Package: [PyPI](https://pypi.org/project/deepevolution/)
