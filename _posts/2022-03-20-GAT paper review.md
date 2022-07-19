---
title: 'Graph Attention Networks'
date: 2022-07-19
permalink: /posts/gat/
tags:
  - Graph Neural Networks
  - Embeddings
---

The paper performs node classification of graph data by computing the hidden representations of each node by attending over its neighbors, following a self-attention strategy. Self-attention is an attention mechanism applied to compute a representation of a single sequence.  
<br>
GAT is a spatial method on graph-structured data. Performs well on both transductive and inductive learning. In transductive learning we already have both training and testing datasets when training the model. Inductive learning encounters only the training data when training the model and applies the learned model on a dataset never seen before. [This](https://towardsdatascience.com/inductive-vs-transductive-learning-e608e786f7d) article explains it better.
<br>
The key contribution of the paper is that the method does not require knowing the graph structure upfront. 
There are two types of approaches in graph ml: spectral approach and non-spectral approach.
<br>

*GNNs consist of an iterative process, which propagates the node states until equilibrium, followed by a neural network, which produces an output for each node based on its state.*
<br>
GraphSAGE: is a method for computing node representations in an inductive manner. This technique samples a fixed size neighborhood of each node and then performs an aggregator (mean, pass thru RNN)over it.
<br>
Attention mechanism is used in sequence based tasks. Its key benefit is that it allows for dealing with variable sized inputs.
<br>
Basically the Graph Attention layer tries to find the good representation of the node feature vectors by computing normalized  attention coefficients.
<br>

The results are discussed on 4 datasets: Cora, Citeseer, Pubmed, PPI. The results are compared with several state of the art transductive learning methods such as: Label propagation, semi-supervised embedding, manifold regularization, skip-gram based graph embedding(DeepWalk), iterative classification algorithm, Planetoid, GCNs, MoNet. And on inductive learning methods: GraphSAGE-GCN, GraphSAGE-mean, GraphSAGE-LSTM, GraphSAGE-pool.






<!-- Headings are cool
======

You can have many headings
======

Aren't headings cool?
------ -->
