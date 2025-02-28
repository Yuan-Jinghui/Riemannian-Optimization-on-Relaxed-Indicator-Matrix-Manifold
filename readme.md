This is the official code repository for the paper

 **"Riemannian Optimization on Relaxed Indicator Matrix Manifold."** 

The code is compatible with the open-source manifold optimization toolbox [manopt](https://www.manopt.org/) and runs based on *manopt.* Please ensure that you download and install *manopt* (MATLAB version) before using this code.

### Introduction

We have introduced a novel manifold—the Relaxed Indicator Matrix Manifold, defined as 
$
\{ X \mid X 1_c = 1_n, l < X^T 1_n < u, X > 0 \}
$
, which plays a significant role in fields such as classification and clustering. We have developed a Riemannian optimization toolbox tailored for the Relaxed Indicator Matrix Manifold and conducted extensive experiments. Compared to other algorithms, our approach demonstrates clear advantages in both loss function values and computational speed. Furthermore, we applied this method to graph partitioning and clustering (RCUT), achieving notable improvements in clustering metrics (ACC, NMI, ARI).

### File Placement

Please place the files in the appropriate *manopt* directory as follows:

```matlab
-manopt;
 --manifolds;
    ---multinomial;
        ---Relaxd_Indicator_Matrix_factory.m
```

or

```matlab
-manopt;
 --manifolds;
    ---multinomial;
        ----RIMfactory;
        ----Dykstras;
        ----EProjSimplex_new;
        ----ProjToTangent;
```

### Usage

You can call the functions as follows (The manopt’s rule):

```matlab
RIM_manifold = Relaxd_Indicator_Matrix_factory(n,c,row,upper,lower);
problem.M = RIM_manifold;
problem.cost = @(X) ...;
problem.egrad = @(X) ...;  % Euclidean gradient
[X_rim,~,info_rim,~] = steepestdescent(problem_rim);
```

## Citation

**We have uploaded the article to arXiv. If you find it useful, please cite it, as this would be a great support to us.**

```matlab
title={Riemannian Optimization on Relaxed Indicator Matrix Manifold}, 
author={Jinghui Yuan and Fangyuan Xie and Feiping Nie and Xuelong Li}
```
