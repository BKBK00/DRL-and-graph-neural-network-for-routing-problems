# Deep-reinforcement-learning-and-graph-neural-network-for-routing-problems
This code is for the published paper 'Solve routing problems with a residual edge-graph attention neural network', link https://www.sciencedirect.com/science/article/pii/S092523122200978X .
Everyone is welcome to use our code and cite our paper.


In this paper, we have solved three types of routing problems, i.e., travel salesman proble (TSP), capacited vehicle routing problem (CVRP), and multi-depot capacited vehicle routing problem (MDCVRP). It's simply to extend our framework to solve other type of routing problem or Combinatorial optimization problem based on our code.

If you have any questions, please feel free to contact with me on kunlei@my.swjtu.edu.cn

# NEEDED
You shoud prepare:
torch              1.4.0;
torch-geometric    1.5.0;
torch-cluster      1.5.2;
torch-scatter      2.0.3;
torch-sparse       0.6.0;
torch-spline-conv  1.2.0
at least.

# Introduction
--Motivation: we exploit both the strong dicision-making power of reinforcement learning and the suprieor representative power of deep learning (e.g., CNN/GNN/Transformer) to solve the combinatorial optimization problems. Many combinatorial optimization problems, such as a TSP or a VRP, are based on a graph structure, which can be easily modeled by the existing graph embedding or network embedding technique. In such a technique, the graph information is embedded in a continuous node representation. The latest development of graph neural network (GNN) can be used in modeling a graph combinatorial problem due to its strong capabilities in information embedding and belief propagation of graph topology. This motivates us to adopt a GNN model to solve combinatorial optimization problems, particularly TSP and CVRP. In this paper, we use the GNN model to build an end-to-end deep reinforcement learning (DRL) framework.

# Neural network 
In our framework, after the features (node coordinates for TSP) of a 2D graph are entered into the model, the encoder encodes the features with GNN. The encoded features are then passed into the decoder with an attention pointer mechanism to predict the probabilities of unselected nodes. The next node is subsequently selected according to the probability distribution by a search strategy, such as a greedy search or a sampling approach. Our encoder amends the Graph Attention Network (GAT) by taking into consideration the edge information in the graph structure and residual connections between layers. We shall call the designed network a residual edge-graph attention network (residual E-GAT). The residual E-GAT encodes the information of edges in addition to nodes in a graph. Edge features can provide additional and more direct information (weighted distance) related to the optimization objective for learning a policy. The optimization goal of the routing problem is to find the shortest weighted route under the corresponding constraints. The weight information (chosen as the distance between nodes in this paper) supplied by edges is not provided by nodes. In addition, entering node and edge information at the same time is conducive to mining the features of spatial adjacency relationships among different nodes. Our decoder is designed based on a Transformer model, which is used primarily in the field of natural language processing. 

# Deep reinforcement learning algorithms
The entire network is optimized using either a proximal policy optimization algorithm (PPO) or an improved baseline REINFORCE algorithm.

# Cite us
{Kun Lei, Peng Guo, Yi Wang, Xiao Wu, Wenchao Zhao,
Solve routing problems with a residual edge-graph attention neural network,
Neurocomputing,
Volume 508,
2022,
Pages 79-98,
ISSN 0925-2312,
https://doi.org/10.1016/j.neucom.2022.08.005.}

For open access source, please cite the work correctly!!!



