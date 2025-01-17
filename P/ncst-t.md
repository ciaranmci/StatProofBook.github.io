---
layout: proof
mathjax: true

author: "Joram Soch"
affiliation: "BCCN Berlin"
e_mail: "joram.soch@bccn-berlin.de"
date: 2021-05-11 15:46:00

title: "Relationship between non-central scaled t-distribution and t-distribution"
chapter: "Probability Distributions"
section: "Univariate continuous distributions"
topic: "t-distribution"
theorem: "Relationship to non-central scaled t-distribution"

sources:

proof_id: "P232"
shortcut: "ncst-t"
username: "JoramSoch"
---


**Theorem:** Let $X$ be a [random variable](/D/rvar) following a [non-central scaled t-distribution](/D/ncst) with mean $\mu$, scale $\sigma$ and degrees of freedom $\nu$:

$$ \label{eq:X}
X \sim \mathrm{ncst}(\mu, \sigma, \nu) \; .
$$

Then, subtracting the mean and dividing by the square root of the scale results in a [random variable](/D/rvar) following a [t-distribution](/D/t) with degrees of freedom $\nu$:

$$ \label{eq:ncst-t}
Y = \frac{X-\mu}{\sqrt{\sigma}} \sim t(\nu) \; .
$$


**Proof:** The non-central scaled t-distribution [is a special case](/P/ncst-mvt) of the [multivariate t-distribution](/D/mvt) in which the mean vector and scale matrix are scalars:

$$ \label{eq:ncst-mvt}
X \sim \mathrm{ncst}(\mu, \sigma, \nu) \quad \Rightarrow \quad X \sim t(\mu, \sigma, \nu) \; .
$$

Therefore, we can apply the [linear transformation theorem for the multivariate t-distribution](/P/mvt-ltt) for an $n \times 1$ random vector $x$:

$$ \label{eq:mvt-ltt}
x \sim t(\mu, \Sigma, \nu) \quad \Rightarrow \quad y = Ax + b \sim t(A\mu + b, A \Sigma A^\mathrm{T}, \nu) \; .
$$

Comparing with equation \eqref{eq:ncst-t}, we have $A = 1/\sqrt{\sigma}$, $b = -\mu/\sqrt{\sigma}$ and the variable $Y$ is distributed as:

$$ \label{eq:Y-dist}
\begin{split}
Y &= \frac{X-\mu}{\sqrt{\sigma}} = \frac{X}{\sqrt{\sigma}} - \frac{\mu}{\sqrt{\sigma}} \\
&\sim t\left( \frac{\mu}{\sqrt{\sigma}} - \frac{\mu}{\sqrt{\sigma}}, \left( \frac{1}{\sqrt{\sigma}} \right)^2 \sigma, \nu \right) \\
&= t\left( 0, 1, \nu \right) \; .
\end{split}
$$

Plugging $\mu = 0$, $\Sigma = 1$ and $n = 1$ into the [probability density function of the multivariate t-distribution](/P/mvt-pdf),

$$ \label{eq:mvt-pdf}
p(x) = \sqrt{\frac{1}{(\nu \pi)^{n} |\Sigma|}} \, \frac{\Gamma([\nu+n]/2)}{\Gamma(\nu/2)} \, \left[ 1 + \frac{1}{\nu} (x-\mu)^\mathrm{T} \Sigma^{-1} (x-\mu) \right] \; ,
$$

we get

$$ \label{eq:t-pdf}
p(x) = \sqrt{\frac{1}{\nu \pi}} \, \frac{\Gamma([\nu+1]/2)}{\Gamma(\nu/2)} \, \left[ 1 + \frac{x^2}{\nu} \right]
$$

which is the [probability density function of Student's t-distribution](/P/t-pdf) with $\nu$ degrees of freedom.