# Machine Learning

## Problem Setup

Consider the setup with an input space $\mathcal{X}$, an output space $\mathcal{Y}$, and a hypothesis class $\mathcal{H}$ containing functions from $\mathcal{X}$ to $\mathcal{Y}$. There is an unknown fixed $h\in\mathcal{H}$, and samples $(x_i,h(x_i))\in\mathcal{X}\times\mathcal{Y}, i=0,1,\ldots$

Our goal is to approximate $h$. However, $h$ can be hard to compute from its mathematical definition, so may have to choose a different representation.

## The twofold difficulty
The difficulty here is twofold. 
- Complexity of the hypothesis class: $\mathcal{H}$ contains more than one element. (to be refined)
- Computational complexity: $h(x)$ can be hard to compute for given $h\in\mathcal{H}$ and $x\in\mathcal{X}$.

So in machine learning, people tend to use another $\mathcal{H}'$ easier to compute and easy to search by machine such as:
- linear regression
- nearest neighbor
- neural networks

## Examples
### Digit recognization in MNIST 

Consider the task of recognizing digit $1$.
Let $\mathcal{X}$ and $x\in\mathcal{X}$ be the space of grey images and an image in the space. The target function $h$ is such that $h(x) = 1$ only when $x$ is a picture of digit $1$. 

An ideal image of the digit $1$ is characterized by a line segment $\overline{AB}$, where $A,B$ are the two endpoints. Thus for an input image $x$ and two points $A,B$, we can use a scoring function $s(x,\overline{AB})$ to measure the similarity of $x$ with an ideal $1$ determined by $\overline{AB}$. The image $x$ will be classified as $1$ if there is $\overline{AB}$ such that the scoring function $s(x, \overline{AB})$ is larger than a predetermined threshold $\theta$. 
More precisely
$$ h(x) = \exists \overline{AB}, s(x,\overline{AB}) \geq \theta. $$



Too many choices: 28*28*28*28=1M, hard to compute

[1.png *2]

### Parsing in NLP


