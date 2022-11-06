# Mnist


### Fermi match

1. Given a type E, a scoring function f of type E: E -> ?f32 is a map from type E to ?f32, 

2. Given a vector V_input of E of any size and composite template which is a vector of scoring functions of size n, return a matched vector V_matched of ?E of size n and the rest of the input vector E

Determine V_matched sequentially:
    the k-th element of V_matched is the None if:
        1. all the elements in f_k(V_input) is a list of None or
        2. all the elements of f_k(V_input) that are not None are picked by f_1,...,f_{k-1}
    else it picks the largest element in V_input that is not picked before in terms of the value f_k



### Hausdoff distance

d_H(C_1,C_2) = \max_{x\in C_1}\min_{y\in C_2} d(x,y)