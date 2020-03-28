<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

# Hopkins-Statistic-Clustering-Tendency
A python implementation for computing the Hopkins' statistic [(Lawson and Jurs (1990))](https://pubs.acs.org/doi/abs/10.1021/ci00065a010) for measuring clustering tendency of data.

## Clustering Tendency
Cluster analysis or clustering is the task of grouping a set of objects in such a way that objects in the same group (called a cluster) are more similar (in some sense) to each other than to those in other groups (clusters). 

However, clustering algorithms will locate and specify clusters in data even if none are present. It is therefore appropriate to measure the clustering tendency or randomness of a data set before subjecting it to a clustering algorithm.

To measure cluster tendency is to measure to what degree clusters exist in the data to be clustered, and may be performed as an initial test, before attempting clustering. 

## Hopkins' Statistic
Hopkins’ statistic is a simple measure of clustering tendency. It is based on the difference between the distance from a real point to its nearest neighbor, U, and the distance from a randomly chosen point within thedata space to the nearest real data point, W.  


## Algorithm 
- Let X be the set of n data points.
- Consider a random sample (without replacement) of m<<n data points with members <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a>. [Dubes and Jain](https://www.sciencedirect.com/science/article/pii/S1474667017633652) suggest choosing 5% of the data points so that the nearest-neighbor distances will be independent and thus approximate a Beta distribution.
- Generate a set Y of m uniformly randomly distributed data points.
- Define two distance measures,
    - <a href="https://www.codecogs.com/eqnedit.php?latex=u_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?u_{i}" title="u_{i}" /></a> the distance of <a href="https://www.codecogs.com/eqnedit.php?latex=y_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?y_{i}" title="y_{i}" /></a> in Y from its nearest neighbour in X, and
    - <a href="https://www.codecogs.com/eqnedit.php?latex=w_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_{i}" title="w_{i}" /></a> the distance of <a href="https://www.codecogs.com/eqnedit.php?latex=x_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{i}" title="x_{i}" /></a> in X from its nearest neighbour in X.
- if the data is d dimensional, then the Hopkins statistic is defined as:

<img src="http://www.sciweavers.org/tex2img.php?eq=%5C%5BH%20%3D%20%5Cfrac%7B%5Csum_%7Bi%3D1%7D%5E%7Bm%7Du_%7Bi%7D%5Ed%20%7D%7B%5Csum_%7Bi%3D1%7D%5E%7Bm%7Du_%7Bi%7D%5Ed%20%20%2B%20%5Csum_%7Bi%3D1%7D%5E%7Bm%7Dw_%7Bi%7D%5Ed%20%7D%20%5C%5D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="\[H = \frac{\sum_{i=1}^{m}u_{i}^d }{\sum_{i=1}^{m}u_{i}^d  + \sum_{i=1}^{m}w_{i}^d } \]" width="187" height="57" />
