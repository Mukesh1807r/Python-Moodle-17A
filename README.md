# Adjacency List Representation of a Graph

## Aim

To write a Python program that demonstrates the **adjacency list representation** of an undirected graph using classes.

## Algorithm

1. Define a class `AdjNode` to represent a node in the adjacency list.
2. Define a class `Graph` with:
   - Constructor to initialize the number of vertices.
   - A method `add_edge(src, dest)` to add an edge between two vertices.
   - A method `print_graph()` to display the adjacency list of each vertex.
3. In the driver code:
   - Create a graph object with a specified number of vertices.
   - Add edges between the vertices.
   - Print the adjacency list.

## Program

```python
class AdjNode:
    def __init__(self, data):
        self.vertex = data
        self.next = None

class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [None] * self.V

    def add_edge(self, src, dest):
        # Adding the node to the source node
        node = AdjNode(dest)
        node.next = self.graph[src]
        self.graph[src] = node

        # Adding the source node to the destination node
        node = AdjNode(src)
        node.next = self.graph[dest]
        self.graph[dest] = node

    def print_graph(self):
        for i in range(self.V):
            print("Adjacency list of vertex {}\n {}".format(i, i), end="")
            temp = self.graph[i]
            while temp:
                print(" -> {}".format(temp.vertex), end="")
                temp = temp.next
            print(" \n")

# Driver program
if __name__ == "__main__":
    V = 5
    graph = Graph(V)
    graph.add_edge(0, 1)
    graph.add_edge(0, 4)
    graph.add_edge(1, 2)
    graph.add_edge(1, 3)
    graph.add_edge(1, 4)
    graph.add_edge(2, 3)
    graph.add_edge(3, 4)

    graph.print_graph()
```
---
## Output

![image](https://github.com/user-attachments/assets/ae1d67a5-deed-41e9-a706-e1c04ca4ff3e)

## Result 

Successfully demonstrated adjacency list representation of the graph!


