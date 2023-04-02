# knights-travails
## The Odin Project: Knights Travails

### Table of Contents
[Edge Lists](#edge-list(s))

[Adjacency Matrices](#adjacency-matrices)

[Adjacency Lists](#adjacency-lists)

[Traversal](#traversal!)

[Healthful Sites](#helpful-sites)

### [Click here](https://www.theodinproject.com/lessons/javascript-knights-travails) to go to project instructions.

According to [Wikipedia](https://en.wikipedia.org/wiki/Data_structure):
> Different types of data structures are suited to different kinds of applications, and some are highly specialized to specific tasks. Data structures provide a means to manage large amounts of data efficiently for uses such as large databases and internet indexing services. Usually, efficient data structures are key to designing efficient algorithms.

+ Graphs are important cause they have many applications. They show the relatoionship between two objects, or nodes; also known as VERTEX(singular), or VERTICES (plural). 
+ The relationship between them are shown/represented via line/link, or EDGE(singular) or EDGES(plural).
+ Vertices are adjacent if they are connected by an edge. 
+ Consider the following graph 

![alt text](https://cdn.kastatic.org/ka-perseus-images/21cd2731928c7c13057eee000e3697de82ccc058.png)
+ How can we represent this with code?
## Edge List(s):
```javascript
[ [0,1], [0,6], [0,8], [1,4], [1,6], [1,9], [2,4], [2,6], [3,4], [3,5], [3,8], [4,5], [4,9], [7,8], [7,9] ]
```
+ Egde List total time (unordered): O(E).
+ Egde List total space: Θ(E).
+ This is a simple way to represent the information but the order is random, making this a linear search. We need a way to organize the data to make searching quicker. 

## Adjacency Matrices
+ Here is an example of an adjacency matrix.
![alt text](https://cdn.kastatic.org/ka-perseus-images/549bca1a52774846b25caff86d244d03ee63fd38.png)
+ O's imply no connection, and 1's imply a connection. 
+ If the matrix is symetrical the graph is undirected.
+ If the graph is directed (ex. one-way streets), then the matrix will be non-symetrical.
+ Below is the representation of our data. 
```javascript
[ [0, 1, 0, 0, 0, 0, 1, 0, 1, 0],
  [1, 0, 0, 0, 1, 0, 1, 0, 0, 1],
  [0, 0, 0, 0, 1, 0, 1, 0, 0, 0],
  [0, 0, 0, 0, 1, 1, 0, 0, 1, 0],
  [0, 1, 1, 1, 0, 1, 0, 0, 0, 1],
  [0, 0, 0, 1, 1, 0, 0, 0, 0, 0],
  [1, 1, 1, 0, 0, 0, 0, 0, 0, 0],
  [0, 0, 0, 0, 0, 0, 0, 0, 1, 1],
  [1, 0, 0, 1, 0, 0, 0, 1, 0, 0],
  [0, 1, 0, 0, 1, 0, 0, 1, 0, 0] ]
```
+ Adjacency Matrix total time: O(1).
+ Adjacency Matrix total space: Θ(V<sup>2</sup>). **not the best**
+ The adjacency matrix is considered *sparse* if there is more 0's, than 1's; few edges.  

## Adjacency Lists
+ Here is an example of an adjacency matrix.
![alt text](https://cdn.kastatic.org/ka-perseus-images/cc82379521bd84738e86d6cf9552738ca9138420.png)
+ Below is the representation of our data. 
```javascript
[ [1, 6, 8],
  [0, 4, 6, 9],
  [4, 6],
  [4, 5, 8],
  [1, 2, 3, 5, 9],
  [3, 4],
  [0, 1, 2],
  [8, 9],
  [0, 3, 7],
  [1, 4, 7] ]
```
+ Adjacency List total time: O(d). (d= degree of each vertex).
+ Adjacency List total space: Θ(V+E). 
+ Combines edge lists, and adjacency matrices.

+ lets look at other examples. 
+ the following is an image and an adjecency list.
![alt text](https://jarednielsen.com/static/1354cd83ef97d77fb1f1d6a2aa6b45c7/f058b/jarednielsen-data-structure-graph-javascript-sketch.png)
```javascript
[
    [`B`, `C`, `D`],
    [`A`, `C`, `D`],
    [`B`, `D`],
    [`A`, `B`, `C`, `E`],
    [`D`]
]
```
+ One problem. since we are dealing with numbers, and not letters, we need a way to track with vertex correspond with which array.
+ Below is one way to do this. 
```javascript
{
    A: [`B`, `C`, `D`],
    B: [`A`, `C`, `D`],
    C: [`B`, `D`],
    D: [`A`, `B`, `C`, `E`],
    E: [`D`]
}
```

## Traversal!
+ Time to learn how to traverse the graph...finally!
+ How would you traverse this simple graph?
![alt text](https://jarednielsen.com/static/1684b319a2c635b5df99e3fdc7227dbc/29007/jarednielsen-data-structure-graph-bfs-a-g.png)
+ Unlike binary search tress, graphs dont have any order, specific layout, or specific root. So we can start anywhere.
+ Lets start at `A` to be simple, and go to `G`.
+ How should we initiate the search?
    + Search all vertices connected to `A`?
    + Or search *one* of vertices connected to `A` and continue seaerching the verticies connected to that.
+ There are two algorithms used for graph traversal
    + Breadth-first search (BFS).
        + 
    + Depth-firest search (DFS).

## Helpful Sites:

[Intro to graphs.](https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/describing-graphs)

[How to represent graphs.](https://jarednielsen.com/data-structure-graph-javascript/)

[Intro to traversing graphs.](https://www.khanacademy.org/computing/computer-science/algorithms/breadth-first-search/a/the-breadth-first-search-algorithm)

[More on traversing graphs.](https://jarednielsen.com/data-structure-graph-breadth-first-search/)

Special Thanks to Khan Academy, and jarednielsen.com, for valuable information, and images used. 

[Return to top](#knights-travails)