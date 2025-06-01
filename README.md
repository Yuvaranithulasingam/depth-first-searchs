<h1>ExpNo 2 : Implement Depth First Search Traversal of a Graph</h1> 

<h3>Name: Yuvarani T</h3>
<h3>Register Number: 212222110057</h3>

<H3>Aim:</H3>
<p> To Implement Depth First Search Traversal of a Graph using Python 3.</p>

<h3>Theory:</h3>
<strong>Depth First Traversal </strong>(or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. 
Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
Step 1: Initially, stack and visited arrays are empty.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446)

Queue and visited arrays are empty initially.
Stack and visited arrays are empty initially.
Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)

Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack
Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)

Visit node 1
Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)

Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack
Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)

Visit node 4
Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)

Visit node 3
Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

<h3>Algorithm:</h3>
<B><ol>
 <li>Construct a Graph with Nodes and Edges</li>
 <li>Depth First Search Uses Stack and Recursion</li>
 <li>Insert a START node to the STACK</li>
 <li>Find its Successors Or neighbors and Check whether the node is visited or not</li>
 <li>If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.</li>
</ol></B>

<hr>
<h3>Program:</h3>
<pre>
from collections import defaultdict
def parse_node(x):
    try:
        return int(x)
    except ValueError:
        return x
def dfs(graph, start, visited, path):
    visited[start] = True
    path.append(start)
    for neighbour in graph[start]:
        if not visited.get(neighbour, False):
            dfs(graph, neighbour, visited, path)
    return path
n, e = map(int, input().split())
graph = defaultdict(list)
for _ in range(e):
    u, v = input().split()
    u = parse_node(u)
    v = parse_node(v)
    graph[u].append(v)
    graph[v].append(u)

start = next(iter(graph))
visited = {}
path = []
traversed_path = dfs(graph, start, visited, path)
print([str(node) for node in traversed_path])
</pre>
<hr>

<hr>
<h3>Sample Input:</h3>
<hr>
8 9 <br>
A B <br>
A C <br>
B E <br>
C D <br>
B D <br>
C G <br>
D F <br>
G F <br>
F H <br>
<hr>
<h3>Sample Output:</h3>
<hr>
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']

<hr>
<h3>Output:</h3>

![{F899A638-41E9-4CD8-95B9-6B3D70D998E6}](https://github.com/user-attachments/assets/13c5f2d5-606f-4c59-989b-9b0fc0ff3499)

<hr>
<h3>Sample Input</h3>
<hr>
5 5 <br>
0 1 <br>
0 2 <br>
0 3 <br>
2 3 <br>
2 4 <br>
<hr>
<h3>Sample Output</h3>
<hr>
['0', '1', '2', '3', '4']
<hr>
<h3>Output:</h3>

![image](https://github.com/user-attachments/assets/f7dbc99c-d552-4f34-b912-19e6c8118e00)

<hr>
<h3>Result:</h3>
<hr>
<p>Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.</p>
