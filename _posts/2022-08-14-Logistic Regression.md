---
title: 'Why do we use sigmoid for Logistic Regression?'
date: 2022-08-27
permalink: /posts/sigmoid/
tags:
  - cool posts
  - category1
  - category2
---

For classification why do we use the sigmoid function and not just $$w^T x$$ ? 

In classification problem what we are trying to predict is the probability of a data point belonging to a particular class. Now $$w^T x \in (-\infty, \infty)$$, but we want to model probabilities which have range:

$$
\begin{equation}
    p(y=1|x,w) \in [0,1]
\end{equation}
$$

$$
\begin{equation}
    p(y=0|x,w) = 1-p(y=1|x,w) \in [0,1]
\end{equation}
$$

If we look at odds:

$$
\begin{equation}
    \frac{p}{1-p} \in [0, \infty)
\end{equation}
$$



$$
\begin{equation}
    log (odds) = log(\frac{p}{1-p}) \in (-\infty, \infty)
\end{equation}
$$

hence if 

$$
\begin{equation}
    w^T x  = log(\frac{p}{1-p})
    
\end{equation}
$$

$$
\begin{equation}
    \frac{p}{1-p} = e^{(w^T x)}
\end{equation}
$$

$$
\begin{equation}
    p = e^{(w^T x)} - p e^{(w^T x)}
\end{equation}
$$

$$
\begin{equation}
    \implies p = \frac{e^{(w^T x)}}{1+e^{(w^T x)}}
\end{equation}
$$

Hence $$w^T x$$ models log (odds) and to model the probabilities directly we use the sigmoid function.


## Why do we use log loss for logistic regression?

Log loss:

$$
\begin{equation}
    loss =  -\sum_{i=1}^{n} y_i log(p(y_i))
\end{equation}
$$

For binary classification it becomes:

$$
\begin{equation}
    loss =  -y log(p) - (1-y) log(1-p)
\end{equation}
$$

Probability density function of a bernoulli random variable:

$$
\begin{equation}
    pdf = p^y (1-p)^{(1-y)}
\end{equation}
$$

log likelihood:
$$
\begin{equation}
    l = ylog p + (1-y)log (1-p)
\end{equation}
$$

Therefore, by using log loss we are trying to find the maximum likelihood estimation of the parameters w.
