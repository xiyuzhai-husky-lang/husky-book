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



### The Model for Mnist

Let's first see what the model is like in the case of Mnist.

We define the following features:

- `raw_input`: this is the raw input of mnist dataset, $28\times 28$ gray scale image;

- `binary_image`: a binary image obtained from thresholding `raw_input`.

- `connected_components`: the set of connected components of `binary_image`.

- `major_connected_component`: a single connected region obtained from connected_components so that:

  - equals `connected_components[0]` when there is only one connected components

  - when there are two very close connected components, say, $A$ and $B$, then `major_connected_component` contains points that satisfies one of

    - is a point in $A$
    - is a point in $B$
    - is a point in a path from $A$ to $B$ of length no more than $dist(A, B) + \epsilon$, where $dist(A, B)$ is the canonical distance between $A$ and $B$ and $\epsilon$ is a very small positive number.

  - otherwise, equals the largest one

- `major_raw_contours`: the set of contours of `major_connected_component` represented by `Vec<Vec<Point2d>>`. The convention is that `major_raw_contours[0]` is always the counterclosewise (also the outer) one.

![alt text](../snapshots/generic-major-raw-contours.png)

- `major_line_segment_sketch`: line segment sketch of `major_raw_contours[0]`. This sketching is roughly speaking, very similar to that in painting. This is key to our interpretable and efficient processing of shapes. It's quite natural, as this technique has been developed in painting for thousands of years.

![alt text](../snapshots/generic-major-line-segment-sketch.png)

- `major_concave_components`

![alt text](../snapshots/generic-major-concave-components.png)





### Parsing in NLP


=======
Let $\mathcal{X}$ denote input space, and $\mathcal{Y}$ denote output space, and $\mathcal{H}$ denote hypothesis class.

TODO: Jian Qian and Haochuan Li

## Computational Complexity of Inference

suppose
we have implement





