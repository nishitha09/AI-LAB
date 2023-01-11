**1. PROGRAM TO FIND BFS:**<br>

graph = {<br>
'1' : ['2','10'],<br>
'2' : ['3','8'],<br>
'3' : ['4'],<br>
'4' : ['5','6','7'],<br>
'5' : [],<br>
'6' : [],<br>
'7' : [],<br>
'8' : ['9']<br>,
'9' : [],<br>
'10' : []<br>
}<br>
visited = [] # List for visited nodes.<br>
queue = []     #Initialize a queue<br>
def bfs(visited, graph, node): #function for BFS<br>
  visited.append(node)<br>
  queue.append(node)<br>
   while queue:          # Creating loop to visit each node<br>
    m = queue.pop(0) <br>
    print (m, end = " ") <br>
     for neighbour in graph[m]:<br>
      if neighbour not in visited:<br>
        visited.append(neighbour)<br>
        queue.append(neighbour)<br>
#Driver Code<br>
print("Following is the Breadth-First Search")<br>
bfs(visited, graph, '1')    # function calling<br>

**OUTPUT:**<br>

Following is the Breadth-First Search<br>
1 2 10 3 8 4 9 5 6 7<br>
graph = {<br>

**2. PROGRAM TO FIND DEPTH FIRST SEARCH:**<br>

graph = {<br>
'5' : ['3','7'],<br>
'3' : ['2', '4'],<br>
'7' : ['6'],<br>
'6': [],<br>
'2' : ['1'],<br>
'1':[],<br>
'4' : ['8'],<br>
'8' : []<br>
}<br>
visited = set() # Set to keep track of visited nodes of graph.<br>
def dfs(visited, graph, node):  #function for dfs<br> 
    if node not in visited:<br>
        print (node)<br>
        visited.add(node)<br>
        for neighbour in graph[node]:<br>
            dfs(visited, graph, neighbour)<br>
#Driver Code<br>
print("Following is the Depth-First Search")<br>
dfs(visited, graph, '5')<br>

**OUTPUT:**<br>

Following is the Depth-First Search<br>
5<br>
3<br>
2<br>
1<br>
4<br>
8<br>
7<br>
6<br>

**3. PROGRAM TO FIND BEST FIRST SEARCH:**<br>

from queue import PriorityQueue<br>
import matplotlib.pyplot as plt<br>
import networkx as nx<br>
#for implementing BFS | returns path having lowest cost<br>
def best_first_search(source, target, n)<br>
:
 visited = [0] * n<br>
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
       pq.put((c, v))<br>
       print()<br>
#for adding edges to graph<br>
def addedge(x, y, cost):
 graph[x].append((y, cost))<br>
 graph[y].append((x, cost))<br>
v = int(input("Enter the number of nodes: "))<br>
graph = [[] for i in range(v)] # undirected Graph<br>
e = int(input("Enter the number of edges: "))<br>
print("Enter the edges along with their weights:")<br>
for i in range(e):<br>
 x, y, z = list(map(int, input().split()))<br>
 addedge(x, y, z)<br>
source = int(input("Enter the Source Node: "))<br>
target = int(input("Enter the Target/Destination Node: "))<br>
print("Path: ", end = "")<br>
best_first_search(source, target, v)<br>

**OUTPUT:**<br>

Enter the number of nodes: 4<br>
Enter the number of edges: 5<br>
Enter the edges along with their weights:<br>
0 1 1<br>
0 2 1<br>
0 3 2<br>
2 3 2<br>
1 3 3 <br>
Enter the Source Node: 2<br>
Enter the Target/Destination Node: 1<br>
Path: 2<br> 

0<br>
1<br> 
