# TSP Solver with Reinforcement Learning, Actor-Critic and Active Search strategy 
This is PyTorch implementation of NEURAL COMBINATORIAL OPTIMIZATION WITH REINFORCEMENT LEARNING(Bello et al. 2016)(https://arxiv.org/abs/1611.09940).

Pointer Networks is the model introduced by Vinyals et al. 2015(https://arxiv.org/abs/1506.03134). This model uses attention to output a index permutation of the input.
![Screen Shot 2020-05-12 at 12 15 35 AM](https://user-images.githubusercontent.com/51239551/81578424-bf082f80-93e5-11ea-812a-914c9046587a.png)

## Actor-Critic algorithm to train the Pointer Networks on TSP without supervised solution
In this work, we tackle Traveling Salesman Problem(TSP), which is one of the combinatorial optimization problems known as NP-hard. TSP seeks for the shortest tour for a salesman to visit each city exactly once.

In the training phase, this TSP solver optimizes 2 different types of Pointer Networks which are Actor and Critic model. Given a graph of cities where the cities are the nodes, critic model predicts expected tour length, which is generally called state value. Parameter of critic model is optimized as estimated tour length catch up with actual length sampled from the tour(city permutation) predicted by actor model. Actor model updates its policy parameter with advantage value which subtracts state value from actual tour length.

In the test phase, search strategy called Active Search takes actor model and use policy gradient to search for the best tour.
![Figure_1](https://user-images.githubusercontent.com/51239551/81577550-8451c780-93e4-11ea-8ab3-3b412caf1fcb.png)