#PROGRAM 

graph = {<br>
'1' : ['2','10'],<br>
'2' : ['3','8'],<br>
'3' : ['4'],<br><br>
'4' : ['5','6','7'],<br>
'5' : [],<br>
'6' : [],<br>
'7' : [],<br>
'8' : ['9'],<br>
'9' : [],<br>
'10' : []<br>
}<br>
visited = [] # List for visited nodes.<br>
queue = []     #Initialize a queue<br>

def bfs(visited, graph, node): #function for BFS<br>
  visited.append(node)<br>
  queue.append(node)<br>

  while queue:    <br>      # Creating loop to visit each node
    m = queue.pop(0) <br>
    print (m, end = " ")<br> 
      for neighbour in graph[m]:<br>
      if neighbour not in visited:<br>
        visited.append(neighbour)<br>
        queue.append(neighbour)<br>

#Driver Code
print("Following is the Breadth-First Search")<br>
bfs(visited, graph, '1')    # function calling<br>

OUTPUT:<br>

Following is the Breadth-First Search<br>
1 2 10 3 8 4 9 5 6 7<br>


graph = {
'5' : ['3','7'],
'3' : ['2', '4'],
'7' : ['6'],
'6': [],
'2' : ['1'],
'1':[],
'4' : ['8'],
'8' : []
}
visited = set() # Set to keep track of visited nodes of graph.

def dfs(visited, graph, node):  #function for dfs 
    if node not in visited:
        print (node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

# Driver Code
print("Following is the Depth-First Search")
dfs(visited, graph, '5')

OUTPUT:

Following is the Depth-First Search
5
3
2
1
4
8
7
6


from queue import PriorityQueue
import matplotlib.pyplot as plt
import networkx as nx
# for implementing BFS | returns path having lowest cost
def best_first_search(source, target, n):
 visited = [0] * n
 visited[source] = True
 pq = PriorityQueue()
 pq.put((0, source))
 while pq.empty() == False:
   u = pq.get()[1]

   print(u, end=" ") # the path having lowest cost
   if u == target:
     break
   for v, c in graph[u]:
     if visited[v] == False:
       visited[v] = True
       pq.put((c, v))
       print()
# for adding edges to graph
def addedge(x, y, cost):
 graph[x].append((y, cost))
 graph[y].append((x, cost))

v = int(input("Enter the number of nodes: "))
graph = [[] for i in range(v)] # undirected Graph
e = int(input("Enter the number of edges: "))
print("Enter the edges along with their weights:")
for i in range(e):
 x, y, z = list(map(int, input().split()))
 addedge(x, y, z)
source = int(input("Enter the Source Node: "))
target = int(input("Enter the Target/Destination Node: "))
print("Path: ", end = "")
best_first_search(source, target, v)

OUTPUT:

Enter the number of nodes: 4
Enter the number of edges: 5
Enter the edges along with their weights:
0 1 1
0 2 1
0 3 2 
2 3 2
1 3 3
Enter the Source Node: 2
Enter the Target/Destination Node: 1
Path: 2 
0 
1 


from collections import defaultdict
jug1, jug2, aim = 5,7,4
visited = defaultdict(lambda: False)
def waterJugSolver(amt1, amt2):
 if (amt1 == aim and amt2 == 0) or (amt2 == aim and amt1 == 0):
   print(amt1, amt2)
   return True
 if visited[(amt1, amt2)] == False:
   print(amt1, amt2)
   visited[(amt1, amt2)] = True
   return (waterJugSolver(0, amt2) or
 waterJugSolver(amt1, 0) or
 waterJugSolver(jug1, amt2) or
 waterJugSolver(amt1, jug2) or
 waterJugSolver(amt1 + min(amt2, (jug1-amt1)),
 amt2 - min(amt2, (jug1-amt1))) or
 waterJugSolver(amt1 - min(amt1, (jug2-amt2)),
 amt2 + min(amt1, (jug2-amt2))))
 else:
   return False
print("Steps: ")
waterJugSolver(0, 0)

OUTPUT:

Steps: 
0 0
5 0
5 7
0 7
5 2
0 2
2 0
2 7
5 4
0 4
True


def TowerOfHanoi(n , source, destination, auxiliary):
    if n==1:
        print ("Move disk 1 from source",source,"to destination",destination)
        return
    TowerOfHanoi(n-1, source, auxiliary, destination)
    print ("Move disk",n,"from source",source,"to destination",destination)
    TowerOfHanoi(n-1, auxiliary, destination, source)

n = 3
TowerOfHanoi(n,'A','B','C')

OUTPUT:

Move disk 1 from source A to destination B
Move disk 2 from source A to destination C
Move disk 1 from source B to destination C
Move disk 3 from source A to destination B
Move disk 1 from source C to destination A
Move disk 2 from source C to destination B
Move disk 1 from source A to destination B


# Using a Python dictionary to act as an adjacency list
graph = {
'5' : ['3','7'],
'3' : ['2', '4'],
'7' : ['6'],
'6': [],
'2' : ['1'],
'1':[],
'4' : ['8'],
'8' : []
}
visited = set() # Set to keep track of visited nodes of graph.

def dfs(visited, graph, node):  #function for dfs 
    if node not in visited:
        print (node)
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

# Driver Code
print("Following is the Depth-First Search")
dfs(visited, graph, '5')

OUTPUT:

Following is the Depth-First Search
5
3
2
1
4
8
7
6
