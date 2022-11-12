# Mnist
todo: code

Let's first see what the model is like in the case of Mnist.

## Features

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




## Debugger frontend
todo: features of the debugger frontend
todo: pin
todo: partition
todo: focus on branch
todo: trace statistics

### Arrive/Return/True/False/Null[0]/Null[_]


## Feature construction processes (??)
todo: Morphism 
todo: function

### Example
todo: fermi match
todo: narrow down


### Fermi match

1. Given a type E, a scoring function f of type E: E -> ?f32 is a map from type E to ?f32, 

2. Given a vector V_input of E of any size and composite template which is a vector of scoring functions of size n, return a matched vector V_matched of ?E of size n and the rest of the input vector E

Determine V_matched sequentially:
    the k-th element of V_matched is the None if:
        1. all the elements in f_k(V_input) is a list of None or
        2. all the elements of f_k(V_input) that are not None are picked by f_1,...,f_{k-1}
    else it picks the largest element in V_input that is not picked before in terms of the value f_k


## Current implementation
todo: The actual implementation of the classification of digits

