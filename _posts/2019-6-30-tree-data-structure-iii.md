---
layout: post
title: Practice Tree Data Structure
---

## Review - Initializing List (Array)

### Initialize 1-D list

##### Python

```py

A = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

A = [i+1 for i in range(10)]

A = [i for i in range(1, 11)]

A = list(range(1,11))

```

##### Java

```java

int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

int[] arr = new int[10];
for (int i = 0; i < 10; i++) {
  arr[i] = i+1;
}
    
```

### Initialize 2-D list
```py
A = [[0, 0], [0, 0]]

A= [[0]*2 for _ in range(2)]

```


## Binary Tree and Binary Search Tree

### Let's Practice!

1. [Tree: Preorder Traversal](https://www.hackerrank.com/challenges/tree-preorder-traversal/problem)
2. [Tree: Postorder Traversal](https://www.hackerrank.com/challenges/tree-postorder-traversal/problem)
3. [Tree: Inorder Traversal](https://www.hackerrank.com/challenges/tree-inorder-traversal/problem)
4. [Tree: Height of a Binary Tree](https://www.hackerrank.com/challenges/tree-height-of-a-binary-tree/problem)
5. [Binary Search Tree:Insertion](https://www.hackerrank.com/challenges/binary-search-tree-insertion/problem)
6. [Binary Search Tree:Lowest Common Ancestor](https://www.hackerrank.com/challenges/binary-search-tree-lowest-common-ancestor/problem)

##### Sample answer for 1.
```py
def preOrder(root):
    #Write your code here
    if not root:
        return
    print(root.info, end=' ')
    preOrder(root.left)
    preOrder(root.right)
```

##### Sample answer for 2.
```py
def postOrder(root):
    #Write your code here
    if not root:
        return
    postOrder(root.left)
    postOrder(root.right)
    print(root.info, end=' ')
```

##### Sample answer for 3.
```py
def inOrder(root):
    #Write your code here
    if not root:
        return
    inOrder(root.left)
    print(root.info, end=' ')
    inOrder(root.right)
```


##### Sample answer for 4.
```py
from collections import deque

def levelOrder(root):
    #Write your code here
    q = deque()
    q.appendleft(root)
    while q:
        top = q.pop()
        print(top.info, end=' ')
        if top.left:
            q.appendleft(top.left)
        if top.right:
            q.appendleft(top.right)
```

##### Sample answer for 5.
```py
    def insert(self, val):
        #Enter you code here.
        new_node = Node(val)
        if not self.root:
            self.root = new_node
            return
        node = self.root
        while True:
            if val < node.info:
                if node.left:
                    node = node.left
                else:
                    node.left = new_node
                    break
            else:
                if node.right:
                    node = node.right
                else:
                    node.right = new_node
                    break
```

##### Sample answer for 6.
```py
def lca(root, v1, v2):
  #Enter your code here
    while True:
        if v1 < root.info and v2 < root.info:
            root = root.left
        elif v1 > root.info and v2 > root.info:
            root = root.right
        else:
            return root
```

### Depth-First Search (DFS) - In-order traversal
```py
class Node:
  def __init__(self, val):
    self.val = val
    self.left = None
    self.right = None

def dfs(node):
    if not node:
        return None
    dfs(node.left)
    print(node.val, end=' ')
    dfs(node.right)


root = Node(5)
root.left = Node(3)
root.right = Node(7)
root.left.left = Node(2)
root.left.right = Node(4)
root.right.left = Node(6)
root.right.right = Node(8)
root.left.left.left = Node(1)

dfs(root)
```

### Breadth-First Search (BFS)

#### Stack (Last In First Out - LIFO)
```py
stack = []
stack.append(1)
stack.append(2)
stack.append(3)

stack.pop()
stack.pop()
```

##### Question
Remove duplicates from a string.
<pre>
<b>Example 1:</b>
Input: geekdojo

Output: gekdojo

<b>Example 2:</b>
Input: aaaabbbbcccc

Output: abc

</pre>

##### Answer (using Stack)
```py
def dedupe(s):
  stack = []
  for c in s:
    if stack and stack[-1] == c:
      continue
    stack.append(c)
  return ''.join(stack)
```

#### Queue (First In First Out - FIFO)
```py
from collections import deque

q = deque()
q.appendleft(1)
q.appendleft(2)
q.appendleft(3)

q.pop()
q.pop()

```

#### BFS uses Queue
```py
from collections import deque

class Node:
  def __init__(self, val):
    self.val = val
    self.left = None
    self.right = None

def bfs(root):
    q = deque()
    q.appendleft(root)
    while q:
        node = q.pop()
        print(node.val, end=' ')
        if node.left:
            q.appendleft(node.left)
        if node.right:
            q.appendleft(node.right)


root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)
root.right.left = Node(6)
root.right.right = Node(7)
root.left.left.left = Node(8)

bfs(root)

```






### More tree problems

* https://leetcode.com/problems/range-sum-of-bst/

### Java
- https://www.hackerrank.com/challenges/welcome-to-java/problem
- https://www.hackerrank.com/challenges/java-loops/problem
