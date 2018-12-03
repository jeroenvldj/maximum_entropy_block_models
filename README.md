<p align="center"><img width=60% src="https://github.com/jeroenvldj/maximum_entropy_block_models/blob/master/images/imt_logo_plus_networks.png"></p>

&nbsp;&nbsp;
![Python](https://img.shields.io/badge/python-3.5%2B-orange.svg)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Configuration model for networks with block structures
This code is for the calculation of **maximum entropy null models** for networks with empirically known clusters. 
<p align="center"><img width=90% src="https://github.com/jeroenvldj/maximum_entropy_block_models/blob/master/images/model_explanation.png"></p>

## Method
For networks with known partitions, the configuration model can be used with explicitly modelling these partitions. This code [analytically solves](http://iopscience.iop.org/article/10.1088/1367-2630/13/8/083001/meta) the configuration model within and between all clusters - all 'blocks' in the adjacency matrix. 

### Paper - full details on the method
The details and performance of this method can be found in this open-access [paper](https://arxiv.org/abs/1805.06005). 
[![paper](https://github.com/jeroenvldj/maximum_entropy_block_models/blob/master/images/article_header.png)](https://arxiv.org/abs/1805.06005)

## Code
The code for the analytically solved null models, the Directed Configuration Model and the Reciprocated Configuration Model, is provided in a 'jupyter notebook' (for now) running on 'Python 3.5'. This notebook contains all explanations about the method, the functions and working examples to show how to use the code. 

## Example - Running the code
The provided `jupyter notebook` is written to be self-explanatory and *self-contained*. Once the provided functions in the notebook are loaded, running the algorithm for a given degree sequence or observed network follows:
  1. Loading a network/graph, as the corresponding adjacency matrix in `numpy.array` format 
<p align="center"><img width=25% src="https://github.com/jeroenvldj/maximum_entropy_block_models/blob/master/images/adjacency_matrix_example.png"></p>

  2. Specify the partitioning of the graph into the block structure
```python
planted_partition = np.concatenate([np.zeros(shape=10), np.ones(shape=8)]) 
```
  3. Running the null model solution
```python
probability_adjacency = numerically_solve_block_dcm(adjacency_matrix=adjacency, partitioning=planted_partition)
```
  4. The null model probabilities can be visualised 
<p align="center"><img width=50% src="https://github.com/jeroenvldj/maximum_entropy_block_models/blob/master/images/adjacency_results.png"></p>

## Notes
**Please see the jupyter notebook for more details and examples.**


MIT © Jeroen van Lidth de Jeude - [IMT School For Advanced Studies Lucca](https://www.imtlucca.it/)

"[*Reconstructing mesoscale network structures*](https://arxiv.org/abs/1805.06005)" Jeroen van Lidth de Jeude, [Tiziano Squartini](https://www.imtlucca.it/tiziano.squartini), [Fabio Saracco](https://www.imtlucca.it/fabio.saracco), [Riccardo Di Clemente](http://www.riccardodiclemente.com/), [Guido Caldarelli](http://www.guidocaldarelli.com/), 15 May 2018
