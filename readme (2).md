# Graph Theory

# Directed Graphs (Digraph)

A directed graph is a graph in which edges have orientations. For example the edge (u,v) is the edge from node u to node v.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled.png)

In the above graph the nodes could represent people and an edge (u,v) could represent that person u bought person v a gift.

# Weighted Graphs

Many graphs can have edges that contain a certain weight to represent an arbitrary value such as cost, distance , quantity, etc...

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%201.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%201.png)

# Special graphs

## Trees!

A tree is an undirected graph with no cycles. it is a connected graph with N nodes and N-1 edges

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%202.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%202.png)

## Rooted Trees

A rooted tree is a tree with a designated root node where every edge either points away from or towards the root node. 

When edges point away from the root the graph is called an arbourescence (out tree) 

.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%203.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%203.png)

## Directed Acyclic Graph (DAGs)

DAGs are directed graphs with no cycles.

they play an important role in representing structures with dependencies. 

several efficent algorithms exist to operate on DAGs

All out trees are DAGs but not all DAGs are out trees.

 

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%204.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%204.png)

## Bipartite Graph

A bipartite graph is one whose verticies can be split into two independent groups U, V such that every edge connects between U and V. 

The graph is two colorable or there is no odd lenght cycle.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%205.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%205.png)

 

## Complete Graphs

A complete graph is one where there is a unique edge between every pair of nodes. A complete graph with n vertices is denoted as the graph Kn.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%206.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%206.png)

# Representing Graphs

## Adjacency Matrix

The cell m[i][j] represents the edge weight of going from node i to node j.

It is assumed that the edge of going from a node to itself has a cost of zero.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%207.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%207.png)

[Pros and Cons](https://www.notion.so/72ac7902dacb4a1bbaf4e9fb24d96289)

## Adjacency List

Represent a graph as a map from nodes to lists to edges .

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%208.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%208.png)

[Untitled](https://www.notion.so/3037ccfae13e4f0e8148560dc624c172)

## Edge list

Represents graphs simply as unordered list of edges. 

This representation is seldomly used because of its lack of structure. However, it is conceptually simple and practical in a handful of algorithms

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%209.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%209.png)

# Common Graph Theory Problem

For the problems ask yourself:

- Is the graph directed or undirected?
- Are the edges weighted ?
- Is the graph I will encounter likely to be sparse or dense with edges?
- Should I use adjacency matrix, adjacency list , an edge list or other structure to represent the graph efficiently ?

 

## Shortest Path Problem

Given a weighted graph, find the shortest path of edges from node A to node B.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2010.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2010.png)

Algorithms:

1. BFS(unweighted graph)
2. Dijkstra's
3. Bellman-Ford 
4. Floyd Warshall
5. A*
6. many more

### Connectivity

does there exist a path between node A and B?

Typical solution: Use union find data structure or any search algorithm(e.g., DFS)

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2011.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2011.png)

### Negative cycles

Does my weighted graph have any negative cycles? If so, where ?

Algorithms : Bellman-Ford and Floyd-Warshall

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2012.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2012.png)

### Strongly Connected Components

Strongly connected commponents(SCCs) can be thought of as self-contained cycles within a directed graph where every vertex in a given cycle can reach every other vertex in the same cycle.

Algorithms :Tarjan's and Kosaraju's algorithm

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2013.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2013.png)

## Travelling Salesman Problem

 The travelling salesman problem asks the following question: "Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city exactly once and returns to the origin city?"

Algorithms : Held-Karp, branch and bound and ant colony optimisation and other approximation algorithms

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2014.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2014.png)

## Bridges

A bridge/cut edge is any edge in a graph whose removal increases the number of connected components.

They often hint at weak points, bottlenecks or vulnerabilities in a graph

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2015.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2015.png)

## Articulation points

An articulation point / cut vertex is any node in a graph whose removal increases the number of connected components.

Articulation points are important in graph theory because they often hint at weak points, bottlenecks or vulnerabilities in a graph.

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2016.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2016.png)

## Minimum Spanning Tree (MST)

A minimum spanning tree (MST) is a subset of the edges of a connected , edge-weighted graph that connects all the vertices together, without any cycles and with minimum possible total edge weight.

Algorithms : Kruskal's , Prim's & Boruvka's algorithm

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2017.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2017.png)

in that graph a possible MST is 

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2018.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2018.png)

MSTs are not always unique but all have the same cost

## Network flow: max flow

Q: with an infinte input source how much "flow" can we push through the network ?

Suppose the edges are roads with cars, pipes with water or hallways packed with people. Flow represents the volume of water allowed to flow through the pipes, the number of cars the roads can sustain in traffic and the maximum amount of people that can navigate through the hallways.

Algorithms: Ford F ulkerson , Edmunds-karp & Dinic's algorithm

![Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2019.png](Graph%20Theory%20bd6d1996d4954d3d9abd38c6e0aa92ba/Untitled%2019.png)