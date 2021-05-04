# Growing neural gas

Code for a growing neural gas (GNG) in Julia: [gng01.ipynb](https://github.com/burubaxair/GNG/blob/main/gng01.ipynb)

Inspired by:

- Mostapha Kalami Heris, Neural Gas and GNG Networks in MATLAB (URL: https://yarpiz.com/77/ypml111-neural-gas-network), Yarpiz, 2015. 
- [Making Art with Growing Neural Gas](http://neupy.com/2018/03/26/making_art_with_growing_neural_gas.html)
- [Quantifying hard retinal exudates using Growing Neural Gas algorithms](https://medium.com/starschema-blog/growing-neural-gas-models-theory-and-practice-b63e5bbe058d)

The algorithm is well described in the following papers:

- [Automatically Building 2D Statistical Shapes Using the Topology Preservation Model GNG](https://link.springer.com/chapter/10.1007/11612032_53)
- [3D gesture recognition with growing neural gas](https://ieeexplore.ieee.org/document/6707129)
- Other numerous papers by Dr. Anastassia Angelopoulou: [Link to her Google Scholar page](https://scholar.google.com/citations?hl=en&user=X_D9qvYAAAAJ&view_op=list_works&sortby=pubdate)

I used the same examples as Mostapha Kalami Heris in his MATLAB code. Just in case, I uploaded his data files here. 

I did some modifications though:

- Instead of increasing the age of the edges, I decrease their time to live at each step. This way, I don't need to explicitly delete an edge when it reaches the maximum age. The times to live are the weights in the adjacency matrix. When TTL = 0, the edge disappears.
- I do not grow the adjacency matrix. It is created in the beginning (being of the maximum size), and then its values are recalculated at each step. It is faster that way in Julia.
- I do the same with the array of neurons and their accumulated errors.
