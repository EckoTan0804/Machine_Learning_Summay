# Cross Validation

<img src="https://scikit-learn.org/stable/_images/grid_search_cross_validation.png" style="zoom:60%; background-color:white">

|                         | How it works?                                                | Illustration                                                 |
| ----------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **K-fold**              | 1. Create $k$-fold partition of the dataset<br />2. Estimate $k$ hold-out predictors using $1$ partition as validation and $k-1$ partition as training set | <br /><img src="https://miro.medium.com/max/5535/1*QDH0DSCecArPmzQtEBh0yg.png" alt="img" style="zoom: 20%; background-color:white" /> |
| **Leave-One-Out (LOO)** | **(Special case with $k=n$)** <br />Consequently estimate $n$ hold-out predictors using $1$ partition as validation and $n-1$ partition as training set | <br /><img src="https://miro.medium.com/max/5284/1*9bs3OMsKOJntR8blRnVE9g.png" alt="img" style="zoom:20%; background-color:white" /><br /> |
| **Random sub-sampling** | 1. Randomly sample a fraction of $\alpha \cdot n, \alpha \in (0,1)$ data points for validation<br />2. Train on remaining points and validate, repeat $K$ times |                                                              |



## 🎥 Explaination

[Machine Learning Fundamentals: Cross Validation](https://www.youtube.com/watch?v=fSytzGwwBVw)