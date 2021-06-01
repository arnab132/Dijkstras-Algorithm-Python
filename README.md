# Implement Dijkstra's algorithm in Python

Provided that all of the vertices are reachable from the source vertex; Dijkstra’s algorithm can be used to find the shortest distance from the source vertex to all other vertices in a weighted graph. The graph can be directed or undirected, cyclic or acyclic, but the weights on all edges need to be nonnegative.

Given a graph and a source vertex in the graph, find the shortest paths from source to all vertices in the given graph.

Dijkstra’s algorithm is very similar to Prim’s algorithm for minimum spanning tree. Like Prim’s MST, we generate an SPT (shortest path tree) with a given source as root. We maintain two sets, one set contains vertices included in the shortest-path tree, another set includes vertices not yet included in the shortest-path tree. At every step of the algorithm, we find a vertex that is in the other set (set of not yet included) and has a minimum distance from the source.

Below are the detailed steps used in Dijkstra’s algorithm to find the shortest path from a single source vertex to all other vertices in the given graph. 

Algorithm 
1) Create a set sptSet (shortest path tree set) that keeps track of vertices included in shortest path tree, i.e., whose minimum distance from source is calculated and finalized. Initially, this set is empty. 
2) Assign a distance value to all vertices in the input graph. Initialize all distance values as INFINITE. Assign distance value as 0 for the source vertex so that it is picked first. 
3) While sptSet doesn’t include all vertices: 

Pick a vertex u which is not there in sptSet and has minimum distance value. 
Include u to sptSet. 
Update distance value of all adjacent vertices of u. To update the distance values, iterate through all adjacent vertices. For every adjacent vertex v, if the sum of a distance value of u (from source) and weight of edge u-v, is less than the distance value of v, then update the distance value of v.  

Basic algorithm

From each of the unvisited vertices, choose the vertex with the smallest distance and visit it.
Update the distance for each neighboring vertex, of the visited vertex, whose current distance is greater than its sum and the weight of the edge between them.
Repeat steps 1 and 2 until all the vertices are visited.

The following illustration shows the algorithm in action. Note that:

a is the source vertex.
distances to all other vertices, from the source, are marked as positive infinity.
edge weights are marked in pink.
