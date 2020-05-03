# Discriminative Vs. Generative

## TL;DR

|                    | Discriminative model                                         | Generative model                                             |
| ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Goal**           | Directly estimate $P(y\mid x)$                               | Estimate $P(x \mid y)$ to then deduce $P(y \mid x)$          |
| **What's learned** | Decision boundary between classes                            | Probability distributions of the data                        |
| **Illustration**   | ![Discriminative model](https://stanford.edu/~shervine/teaching/cs-229/illustrations/discriminative-model.png) | ![Generative model](https://stanford.edu/~shervine/teaching/cs-229/illustrations/generative-model.png) |
| **Examples**       | Regressions, SVMs                                            | GDA, Naive Bayes                                             |

- The distribution $p(y\mid x)$ is the natural distribution for classifying a given example $x$ into a class $y$, which is why algorithms that model this directly are called **discriminative algorithms**. 
- **Generative algorithms** model $p(x,y)$ (or rather $p(x \mid y)$ and $p(y)$), which can be transformed into $p(y \mid x)$ by applying Bayes rule and then used for classification. However, the distribution $p(x,y)$ can also be used for other purposes. For example, you could use $p(x,y)$ to *generate* likely $(x,y)$ pairs.



## In classification
- Generative classifier:
    1. Learn a model of the joint probablity $p(x, y)$ of the input $x$ and the label $y$
    2. Make their predictions by using Bayes rule to calculate $p(y \mid x)$
    3. Pick the most likely $y$
    
- Discriminative classifier: \ Model the posterior $p(y\ mid x)$ directly or learn a direct map from inputs $x$ to the class labels

    

## Example

Consider a classification problem in which we want to learn to distinguish between elephants ($y=1$) and dogs ($y=0$), based on some features of an animal

What discriminative model does is:
Given a training set:
1. An algorithm like logistic regression or the perceptron algorithm (basically) **tries to find a straight line—that is, a decision boundary—that separates the elephants and dogs.** 
2. To classify a new animal as either an elephant or a dog, it checks on **which side of the decision boundary it falls**, and makes its prediction accordingly.

Generative model uses a different approach:
1. First, looking at elephants, we can build a model of what elephants look like ($p(x \mid y=1)$)
2. Then, looking at dogs, we can build a separate model of what dogs look like ($p(x \mid y=0)$)
3. Finally, to classify a new animal, we can match the new animal against the elephant model, and match it against the dog model, to see whether the new animal looks more like the elephants or more like the dogs we had seen in the training set. 

$$
p(y \mid x)=\frac{p(x \mid y) p(y)}{p(x)}=\frac{p(x \mid y) p(y)}{p(x \mid y=1) p(y=1)+p(x \mid y=0) p(y=0)} \\
    \hat{y} = \arg \max _{y} p(y \mid x)=\arg \max _{y} \frac{p(x \mid y) p(y)}{p(x)}=\arg \max _{y} p(x \mid y) p(y)
$$



## Example 2

Source: https://www.zhihu.com/question/20446337

**判别式(discriminative)** 模型举例：要确定一个羊是山羊还是绵羊，用判别模型的方法是从历史数据中学习到模型，然后通过提取这只羊的特征来预测出这只羊是山羊的概率，是绵羊的概率。

**生成式(generative)** 模型举例：利用生成模型是根据山羊的特征首先学习出一个山羊的模型，然后根据绵羊的特征学习出一个绵羊的模型，然后从这只羊中提取特征，放到山羊模型中看概率是多少，在放到绵羊模型中看概率是多少，哪个大就是哪个。

细细品味上面的例子，判别式模型是根据一只羊的特征可以直接给出这只羊的概率（比如logistic regression，这概率大于0.5时则为正例，否则为反例），而生成式模型是要都试一试，最大的概率的那个就是最后结果~



## Helpful Resource

- [What is the difference between a generative and a discriminative algorithm?](https://stackoverflow.com/questions/879432/what-is-the-difference-between-a-generative-and-a-discriminative-algorithm)
- [Supervised Learning Cheatsheet](https://stanford.edu/~shervine/teaching/cs-229/cheatsheet-supervised-learning)
- [Standford CS229 Notes_2](http://cs229.stanford.edu/notes/cs229-notes2.pdf)