**#PROGRAM TO FIND BFS:**<br>

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

**PROGRAM TO FIND DEPTH FIRST SEARCH:**<br>

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
