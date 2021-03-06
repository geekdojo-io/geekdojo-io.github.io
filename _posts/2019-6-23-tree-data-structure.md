---
layout: post
title: Practice Tree Data Structure
---

## Review - Class and in-line functions

### Class

#### Example: Calculator
```py

class Calculator:
  def __init__(self):
    self.history = []
    
  def calculate(self, s):
    res = '{}={}'.format(s, eval(s))
    print(res)
    self.history.append(res)
    
  def showHistory(self):
    if not self.history:
      print('There is no history')
    for s in self.history:
      print(s)
      
  def clearHistory(self):
    self.history = []
    print('Successfully cleared history')
  
calc = Calculator()  
while True:
  s = input().strip()
  if s == 'q':
    break
  elif s == 'c':
    calc.clearHistory()
  elif s == 'h':
    calc.showHistory()
  else:
    calc.calculate(s)
    


```

### Example: Car

```py
class Car:
    def __init__(self, name):
        self.name = name
        self.x = 0
        self.y = 0

    def move(self):
        self.x += 5
        print(self.name, self.x)

my_car = Car('My Car')
your_car = Car('Your Car')
while True:
    cmd = input().strip()
    if cmd == 'q':
        break
    if cmd == 'my':
        my_car.move()
    if cmd == 'your':
        your_car.move()
```



#### Constructor
```py


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

### More tree problems

* https://leetcode.com/problems/range-sum-of-bst/

### Java
- https://www.hackerrank.com/challenges/welcome-to-java/problem
- https://www.hackerrank.com/challenges/java-loops/problem
