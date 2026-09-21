# Ex. No: 18E - Count the Number of Triangles in an Undirected Graph

## AIM:
To write a Python program to **count the number of triangles** present in an **undirected graph** using matrix operations.

## ALGORITHM:

**Step 1**: Initialize a matrix `aux2` to store the square of the adjacency matrix (i.e., `graph²`).  
Also, initialize a matrix `aux3` to store the cube of the adjacency matrix (i.e., `graph³`).

**Step 2**: Multiply the adjacency matrix with itself to compute `aux2 = graph × graph`.

**Step 3**: Multiply `aux2` with the adjacency matrix again to compute `aux3 = aux2 × graph`.

**Step 4**: Compute the **trace** of the matrix `aux3` (i.e., the sum of diagonal elements of the matrix).

**Step 5**: Divide the trace by **6** to get the number of triangles in the graph.  
*(Each triangle is counted six times in the trace — twice per vertex and once per direction.)*

**Step 6**: Return the result.

## PYTHON PROGRAM

```python

# A Python3 program for finding number of
# triangles in an Undirected Graph. The
# program is for adjacency matrix
# representation of the graph

# Utility function for matrix
# multiplication
def multiply(A, B, C):
	global V
	for i in range(V):
		for j in range(V):
			C[i][j] = 0
			for k in range(V):
				C[i][j] += A[i][k] * B[k][j]

# Utility function to calculate
# trace of a matrix (sum of
# diagonal elements)
def getTrace(graph):
	global V
	trace = 0
	for i in range(V):
		trace += graph[i][i]
	return trace

# Utility function for calculating
# number of triangles in graph
def triangleInGraph(graph):
	global V
	
	# To Store graph^2
	aux2 = [[None] * V for i in range(V)]

	# To Store graph^3
	aux3= [[None]*V for i in range(V)]

	# Initialising aux
	# matrices with 0
	for i in range(V):
		for j in range(V):
			aux2[i][j] = aux3[i][j] = 0
```
## OUTPUT

<img width="718" height="143" alt="Screenshot 2025-09-18 131814" src="https://github.com/user-attachments/assets/f9a98a14-87e2-4144-9097-900473683bad" />

## RESULT

Thus , the python code is written and executed successfully.
