---
title: "Machine Learning: The Art of Guiding Computers to Learn and Evolve"
tags: ml
status: draft
comments: true
---
Imagine a world where computers not only compute but also learn and evolve. This is not science fiction; it's the reality of machine learning (ML). At its core, machine learning is a transformative approach that allows machines to learn from data, uncover patterns, and make decisions without being explicitly programmed, all with minimal human intervention.

 [[Historical Insight: The concept of intelligent machines dates back to ancient myths, with one of the earliest examples being the Greek myth of Talos, a giant bronze automaton. During the Renaissance, Leonardo da Vinci sketched designs for a mechanical knight, an early concept of robotics. This idea evolved through the centuries, gaining prominence in modern times with science fiction classics like Maria from 'Metropolis' and later,  Marvin the Paranoid Android from 'The Hitchhiker's Guide to the Galaxy', and HAL 9000 from '2001: A Space Odyssey'.::rmn]]

There is a concise yet comprehensive definition of machine learning capturing all of its important components -- through which we can dissect the approach. It goes like this:

> Machine learning is an approach to __(1) learn__ __(2) complex patterns__ in __(3) existing data__ and then utilize this knowledge to __(4) make predictions__ on __(5) unseen data__.

Now, let's unpack this definition:

__(1)__ **Learning:** Learning in both humans and machines involves acquiring knowledge. Humans gather information through their senses, which is then processed by the brain to form understanding. Similarly, machine learning models acquire knowledge through processing digital data. There are three main approaches for this: (1) in _supervised learning_ the model learns from example input-output pairs (labeled data); (2) in _unsupervised learning_ the model discovers patterns in unlabeled data; (3) in _reinforcement learning_ the model learns through trial and error within a specific environment, adapting based on rewards or penalties received[[Analogy: Supervised learning is like teaching a child with flashcards, unsupervised learning is like letting them explore a room, and reinforcement learning is like teaching them to ride a bike with trial and error.::lsn]].

__(2)__ **Complex Patterns:** Machine learning truly excels when it encounters data imbued with complex, hidden relationships. This is quite different from dealing with random data, which lacks discernible patterns, rendering ML techniques unnecessary. On the other hand, overly simplistic data presents only straightforward patterns, where a linear model or a look-up table might be perfectly adequate. The real power of ML lies in its ability to unearth intricate patterns that are not immediately obvious to the human eye. ML is not only for predicting outcomes but also for clarifying the reasons behind these projections. A crucial element of an effective ML system is its explainability, ensuring we can follow and comprehend the logic behind its predictions[[Explainability in ML is akin to a teacher who not only provides the answer but also explains the 'why' and 'how' behind it.::rsn]]. An explainable ML model can unveil the hidden patterns within the data, fostering a deeper understanding and enabling us to craft well-informed hypotheses based on these insights.

__(3) Training Data:__ Essential to the success of machine learning is a large set of training data. The ability of a system to learn and recognize patterns is greatly enhanced by the number of examples it's trained on. For example, a machine learning model trained on a dataset of 100,000 images of cats and dogs is typically more accurate than one trained with only 100 images. But it's not just the amount of data that matters; the quality is equally important. The training data must accurately represent the problem we're trying to solve. For instance, in building a model to predict house prices, the training data should reflect the real conditions of the housing market. Using data from an unrelated market would hinder the model's ability to generalize and effectively address the real-world problem it's designed to solve.

__(4) Predictions__: Unlike exact mathematical models, machine learning models (more specifically deep learning ones) are universal function approximators[[A multi-layer perceptron can be used to approximate any function. The Universal Approximation theorem states that any continuous function with finite support can be approximated by at-least a one hidden layer based perceptron.::rsn]]. It estimates outcomes, providing useful predictions even when an exact mathematical solution is unfeasible or too resource-intensive. For example, approximating solutions in physical simulations can be much quicker with machine learning than with traditional computational methods.

__(5) Unseen Data:__ The ability to make accurate predictions on unseen data is crucial in machine learning. If a model only performs well on its training data, it's akin to a look-up-table, simply recalling specific answers rather than truly understanding patterns[[For example, a model that only performs well on its training data is akin to a student who memorizes course material verbatim rather than understanding the underlying phenomenons; in unfamiliar situations, both will likely underperform.::lsn]]. This is a classic sign of overfitting, and lack of generalization, where the model is excessively tailored to the training data, including its noise, and fails to generalize to new data. Generalization is the hallmark of a robust machine learning model, allowing it to apply learned patterns to novel situations effectively[[Analogy: A model that doesn't generalize is like a musician who can only play songs they've practiced, but cannot improvise on new tunes.::rsn]]. Making an ML model on a fix offline dataset is relatively easy, but the real challenge lies in making an ML system that continuously operates on online data in-production because the data is constantly changing and evolving in time making tha model trained on old data stale. There is a whole field of research dedicated to this problem called _continual learning_ and approaches like MLOps are developed to effectively monitor and retrain models in production.

## Traditional Algorithms and ML
To better underscore the main properties of machine learning, let's compare it to traditional algorithms.

<figure>
  <img src="/assets/notes/machine-learning/algo.png" alt="Traditional Algorithm" style="width:70%;">
  <figcaption><strong>Fig. 1.</strong> Traditional Algorithm: the patterns or decision logic is hand-crafted. </figcaption>
</figure>

In the traditional algorithmic approach, we hand-craft heuristics, decision logic, and patterns. Take trading algorithms as an example: a simple rule might be to buy when the Relative Strength Index (RSI) is below 30[[Understanding RSI: The Relative Strength Index (RSI) is a popular technical indicator used in trading. It measures the speed and change of price movements, typically on a scale from 0 to 100. An RSI below 30 often signals that a stock is oversold and potentially undervalued, prompting traders to consider buying. Conversely, an RSI above 70 may indicate an overbought, possibly overvalued condition, suggesting a selling opportunity. This simple yet powerful tool helps traders make informed decisions based on market trends.::rsn]]. This approach is efficient for well-defined problems with simple patterns. However, traditional methods often fall short when faced with complex problems where patterns are not easily discernible or where hand-crafting them is impractical[[An example of hand-crafting features is the use of Haar features in face detection algorithms. This process is laborious and challenging, as it requires extensive manual effort to design and test each feature for effectiveness. In contrast, machine learning methods have outperformed these techniques by automating feature learning, significantly improving both accuracy and efficiency, and marking a shift from manual to automated processes in feature design.::lsn]]. This is where machine learning comes into play. In machine learning, the system doesn't just follow explicitly programmed instructions. Instead, it learns patterns from data during a training stage. This learned knowledge is then applied to make predictions on new, unseen data. This is the main difference between traditional algorithms and machine learning.


<figure>
  <img src="/assets/notes/machine-learning/ml.png" alt="Machine Learning" style="width:70%;">
  <figcaption><strong>Fig. 2.</strong> Machine Learning: there is a training stage where the patterns are learned from examples and which is utilized during the prediction/inference stage. </figcaption>
</figure>

[[Statistic: According to a survey, over 70% of businesses today prefer machine learning over traditional algorithms for complex problem-solving.::lmn]]

As depicted in Fig. 1, traditional algorithms rely on hand-crafted logic. Contrastingly, as shown in Fig. 2, machine learning involves a training phase to learn from examples.
The key distinction lies in their approach to problem-solving: traditional algorithms depend on predefined rules, while machine learning algorithms derive rules from data itself.

## References
This note is inspired by Chip Huyen's fascinating [Designing Machine Learning Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/){:target="_blank"} book, page 3, where she introduces the concept of machine learning in a similar way.

