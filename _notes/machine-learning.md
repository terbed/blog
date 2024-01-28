---
title: "Machine Learning: The Art of Guiding Computers to Learn and Evolve"
tags: ml
status: draft
comments: true
---

 [[Cultural Reference: This vision of intelligent machines aligns with sci-fi classics like HAL 9000 from '2001: A Space Odyssey' and Marvin the Paranoid Android from 'The Hitchhiker's Guide to the Galaxy'.::rmn]]

Imagine a world where computers not only compute but also learn and evolve. This is not science fiction; it's the reality of machine learning (ML). At its core, machine learning is a transformative approach that allows machines to learn from data, uncover patterns, and make decisions without being explicitly programmed, all with minimal human intervention.

There is a concise yet comprehensive definition of machine learning capturing all the important components -- through which we can dissect the approach. It goes like this:

> Machine learning is an approach to __(1) learn__ __(2) complex patterns__ in __(3) existing data__ and then utilize this knowledge to __(4) make predictions__ on __(5) unseen data__.

Now, let's unpack this definition:

__(1)__ **Learning:** Learning in both humans and machines involves acquiring knowledge. Humans gather information through their senses, which is then processed by the brain to form understanding. Similarly, machine learning models acquire knowledge through processing digital data. There are three main approaches for this: (1) in _supervised learning_ the model learns from example input-output pairs (labeled data); (2) in _unsupervised learning_ the model discovers patterns in unlabeled data; (3) in _reinforcement learning_ the model learns through trial and error within a specific environment, adapting based on rewards or penalties received[[Analogy: Supervised learning is like teaching a child with flashcards, unsupervised learning is like letting them explore a room, and reinforcement learning is like teaching them to ride a bike with trial and error.::lsn]].

__(2)__ **Complex Patterns:** For machine learning to be effective, the data must contain complex, hidden relationships -- unlike random or overly simple data which either offers no learnable patterns or requires no advanced machine learning techniques[[In this case a linear model or a look-up-table might be just perfect.::rsn]]. These intricate patterns are not immediately obvious to the human eye. However, we can utilize ML methods to uncover and understand the underlying non-linear relationships hidden in the data[[Machine learning can be like a detective, uncovering hidden clues in data that humans might overlook.::lsn]]. So ML is not for making untraceable predictions, but also for understanding the underlying mechanisms. In fact, it is a really important aspect that the ML system should be explainable, and we should be able to understand why the system made a certain prediction[[Analogy: A doctor who can't explain their diagnosis is not a good doctor.::rsn]].

__(3) Training Data:__ The foundation of machine learning is substantial amounts of training data. The more examples the system has, the better it can identify and learn repeating patterns. For example, a model trained on 100,000 images of cats and dogs will be more accurate than one trained on 100 images. However, the quality of the data is just as important as the quantity. The data must be representative of the real-world problem we are trying to solve. For example, if we want to build a model to predict the price of a house, we need to train it on data that is representative of the real-world housing market. If we train it on data from a different country, it will not be able to generalize to the real-world problem.

__(4) Predictions__: Unlike exact mathematical models, machine learning functions as a universal function approximator. It estimates outcomes, providing useful predictions even when an exact mathematical solution is unfeasible or too resource-intensive. For example, approximating solutions in physical simulations can be much quicker with machine learning than with traditional computational methods.

__(5) Unseen Data:__ The ability to make accurate predictions on unseen data is crucial in machine learning. If a model only performs well on its training data, it's akin to a look-up-table, simply recalling specific answers rather than truly understanding patterns[[For example, a model that only performs well on its training data is akin to a student who memorizes course material verbatim rather than understanding the underlying phenomenons; in unfamiliar situations, both will likely underperform.::lsn]]. This is a classic sign of overfitting, and lack of generalization, where the model is excessively tailored to the training data, including its noise, and fails to generalize to new data. Generalization is the hallmark of a robust machine learning model, allowing it to apply learned patterns to novel situations effectively[[Analogy: A model that doesn't generalize is like a musician who can only play songs they've practiced, but cannot improvise on new tunes.::rsn]].

## Traditional Algorithms and ML
To better underscore the main properties of machine learning, let's compare it to traditional software development and algorithms.

<figure>
  <img src="/assets/notes/machine-learning/algo.png" alt="Traditional Algorithm" style="width:70%;">
  <figcaption><strong>Fig. 1.</strong> Traditional Algorithm: the patterns or decision logic is hand-crafted. </figcaption>
</figure>

In the traditional algorithmic approach, we hand-craft heuristics, decision logic, and patterns. Take trading algorithms as an example: a simple rule might be to buy when the Relative Strength Index (RSI) is below 30[[Understanding RSI: The Relative Strength Index (RSI) is a popular technical indicator used in trading. It measures the speed and change of price movements, typically on a scale from 0 to 100. An RSI below 30 often signals that a stock is oversold and potentially undervalued, prompting traders to consider buying. Conversely, an RSI above 70 may indicate an overbought, possibly overvalued condition, suggesting a selling opportunity. This simple yet powerful tool helps traders make informed decisions based on market trends.::rsn]]. This approach is efficient for well-defined problems with simple patterns. However, when facing complex problems where patterns are not easily discernable, traditional methods fall short. This is where machine learning comes into play. In machine learning, the system doesn't just follow explicitly programmed instructions. Instead, it learns patterns from data during a training stage. This learned knowledge is then applied to make predictions on new, unseen data. This is the main difference between traditional algorithms and machine learning.

[[Statistic: According to a survey, over 70% of businesses today prefer machine learning over traditional algorithms for complex problem-solving.::lmn]]

<figure>
  <img src="/assets/notes/machine-learning/ml.png" alt="Machine Learning" style="width:70%;">
  <figcaption><strong>Fig. 2.</strong> Machine Learning: there is a training stage where the patterns are learned from examples and which is utilized during the prediction/inference stage. </figcaption>
</figure>

As depicted in Fig. 1, traditional algorithms rely on hand-crafted logic. Contrastingly, as shown in Fig. 2, machine learning involves a training phase to learn from examples.
The key distinction lies in their approach to problem-solving: traditional algorithms depend on predefined rules, while machine learning algorithms derive rules from data itself.

## References
This note is inspired by Chip Huyen's fascinating [Designing Machine Learning Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/){:target="_blank"} book, page 3, where she introduces the concept of machine learning in a similar way.

