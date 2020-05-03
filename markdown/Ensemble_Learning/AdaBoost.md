# AdaBoost

**Ada**ptive **Boost**ing:

Correct its predecessor by paying a bit more attention to the training instance that the predecessor underfitted. This results in new predictors focusing more and more on the hard cases.

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost.png" alt="AdaBoost" style="zoom:80%;" />



## Pseudocode

1. Assign observation $i$ the weight for $d_{1,i}=\frac{1}{n}$ (equal weights)

2. For $t=1:T$
    1) Train weak learning algorithm using data weighted by $d_{ti}$. This produces weak classifier $h_t$

    2) Choose coefficient $\alpha_t$ (tells us how good is the classifier is at that round)
    
    ​	$
    ​    \begin{aligned}
    ​        \operatorname{Error}_{t} &= \displaystyle\sum_{i;  h_{t}\left(x_{i}\right) \neq y_{i}} d_{t} \quad \text{(sum of weights of misclassified points)} \\
    ​        \alpha_t &= \frac{1}{2} (\frac{1 - \operatorname{Error}_{t}}{\operatorname{Error}_{t}})
    ​    \end{aligned}
    $
    
    3) Update weights
    
    ​	$
    ​    d_{t+1, i}=\frac{d_{t, i} \cdot \exp (-\alpha_{t} y_{i} h_{t}\left(x_{i}\right))}{Z_{t}}
    $
    
    Where 
    - $
        Z_t = \displaystyle \sum_{i=1}^{n} d_{t,i} 
    $:  **normalization factor**
    
       > - If prediction $i$ is correct $\rightarrow y_i h_t(x_i) = 1 \rightarrow $ Weight of observation $i$ will be decreased by $\exp(-\alpha_t)$
       > - If prediction $i$ is incorrect $ \rightarrow y_i h_t(x_i) = -1 \rightarrow $ Weight of observation $i$ will be increased by $\exp(\alpha_t)$
    
    EndFor
    
3. Output the final classifier 

    $
        H(x)=\operatorname{sign}\left(\sum_{t=1}^{T} \alpha_{t} h_{t}\left(x_{i}\right)\right)
    $
    
    

## Example

<img src="/Users/EckoTan/Dropbox/Quiver.qvlibrary/F1E667B9-3878-45D3-AD49-380782A80C11.qvnotebook/98909639-867D-4930-87DD-9316AB50FA45.qvnote/resources/AdaBoost_Eg-07.png" alt="AdaBoost_Eg-07" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost_Eg-00.png" alt="AdaBoost_Eg-00" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost_Eg-01.png" alt="AdaBoost_Eg-01" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost_Eg-02.png" alt="AdaBoost_Eg-02" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost_Eg-03.png" alt="AdaBoost_Eg-03" style="zoom:50%;" />

<img src="/Users/EckoTan/Dropbox/Quiver.qvlibrary/F1E667B9-3878-45D3-AD49-380782A80C11.qvnotebook/98909639-867D-4930-87DD-9316AB50FA45.qvnote/resources/AdaBoost_Eg-04.png" alt="AdaBoost_Eg-04" style="zoom:50%;" />

<img src="/Users/EckoTan/Dropbox/Quiver.qvlibrary/F1E667B9-3878-45D3-AD49-380782A80C11.qvnotebook/98909639-867D-4930-87DD-9316AB50FA45.qvnote/resources/AdaBoost_Eg-05.png" alt="AdaBoost_Eg-05" style="zoom:50%;" />

<img src="/Users/EckoTan/Dropbox/Quiver.qvlibrary/F1E667B9-3878-45D3-AD49-380782A80C11.qvnotebook/98909639-867D-4930-87DD-9316AB50FA45.qvnote/resources/AdaBoost_Eg-06.png" alt="AdaBoost_Eg-06" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/AdaBoost_Eg-07.png" alt="AdaBoost_Eg-07" style="zoom:50%;" />

## Tutorial

🎥 : [Principles of Machine Learning | AdaBoost](https://www.youtube.com/watch?v=-DUxtdeCiB4)