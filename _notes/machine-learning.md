---
title: Machine Learning Introduction
tags: ml
status: draft
comments: true
---

There is a really nice definition of machine learning capturing all the important elements through which we can distill the concept. It goes like this:

> Machine learning is an approach to __(1) learn__ __(2) complex patterns__ in __(3) existing data__ and then utilize this knowledge to __(4) make predictions__ on __(5) unseen data__.

Let's break this down:

__(1)__ **Learning** is the process of acquiring knowledge through experience. We can experience the world and gather data through our senses. Similarly, for machine learning we have to collect data on which the model can learn. Most often we collect examples, questions and corresponding answers (input-output pairs) on which the system can learn, this is called _supervised learning_. Though some methods can learn from data without labels, this is called _unsupervised learning_. Or we can construct an environment in which a system can learn by trial-and-error which is called _reinforcement learning_.

__(2)__  There should be **complex patterns** in the data. If the data is random, there is no pattern that can be learned and utilized. If the data is too simple (e.g. linear, look-up-table), there is no need for machine learning. 

__(3)__  For ML we have to collect large amounts of **training data**. The more examples we have the larger the probability that we can learn an underlying repeating pattern.

__(4)__  ML makes **predictions**, estimates of the desired outcome. It is not an exact mathematical model that gives the exact solution rather a universal function approximator. For example, we can simulate a physical phenomenon with a mathematical model and get an exact solution but this might require enormous computing power and time. On the other hand, we can use a neural network to approximate the solution and get a good estimate in a fraction of the time.

__(5)__  The system should be able to make predictions on **unseen data**. If the system can only make predictions on the data it has seen before, then the system is unable to generalize. We can say, it is a look-up-table for the training data. The ML model is overfitted to the noise inherently present in the data and the general patterns are not learned those could be utilized for predictions on unseen data.

## Traditional Algorithms and ML
To better underscore the main properties of machine learning, let's compare it to traditional software development and algorithms.

<figure>
  <img src="/assets/notes/machine-learning/algo.png" alt="Traditional Algorithm" style="width:70%;">
  <figcaption><strong>Fig. 1.</strong> Traditional Algorithm: the patterns or decision logic is hand-crafted. </figcaption>
</figure>

In the traditional algorithmic approach we hand-craft the heuristics/decision logic/patterns. This is efficient if the problem is well-defined and the patterns to handle are simple. However, if the problem is complex , then it is hard to hand-craft the patterns and the decision logic. In this case, we can use machine learning to learn the patterns from data. This is the main difference between traditional algorithms and machine learning.


<figure>
  <img src="/assets/notes/machine-learning/ml.png" alt="Machine Learning" style="width:70%;">
  <figcaption><strong>Fig. 2.</strong> Machine Learning: there is a training stage where the patterns are learned from examples and which is utilized during the prediction/inference stage. </figcaption>
</figure>

In machine learning the system learns the patterns from the provided data and then use this knowledge to make predictions on new inputs.

## References
This note is inspired by Chip Huyen's fascinating [Designing Machine Learning Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/){:target="_blank"} book, page 3, where she introduces the concept of machine learning in a similar way.

