# EX 6C TRAVELLING SALES MAN PROBLEM  
## DATE:   

## AIM:  
To solve the Travelling Salesman Problem (TSP) for the given graph using a brute-force approach.  

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)

## Algorithm  
1. Represent the cities and paths using an adjacency matrix.  
2. Generate all possible permutations of cities except the starting city.  
3. Calculate the cost for every permutation path.  
4. Track the minimum cost path.  
5. Return the minimum path cost to complete the tour from the start and back.  

## Program:
```python
# To implement the program for TSP.

# Developed by: Sandhya B N
# Register Number: 212222040144

from sys import maxsize
from itertools import permutations

V = 4

def travellingSalesmanProblem(graph, s):
    # Create a list of vertices excluding the start vertex
    vertex = []
    for i in range(V):
        if i != s:
            vertex.append(i)

    min_path = maxsize
    next_permutation = permutations(vertex)

    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)

    return min_path

if __name__ == "__main__":
    graph = [[0, 10, 15, 20],
             [10, 0, 35, 25],
             [15, 35, 0, 30],
             [20, 25, 30, 0]]
    s = 0
    print("Minimum cost to visit all cities:", travellingSalesmanProblem(graph, s))
```
## Output:
<img width="295" alt="image" src="https://github.com/user-attachments/assets/77a94fe2-1abd-4f5c-85d4-83de5d9a197a" />


## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
