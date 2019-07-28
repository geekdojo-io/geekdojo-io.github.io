---
layout: post
title: Practice Tree Data Structure and Binary Search
---

### Review on Iterations

#### Iteration
Let's generate a list with 10 random values
```py
>>> import random
>>> A = [random.randint(0,10) for _ in range(10)]
[1, 10, 7, 7, 3, 2, 2, 0, 5, 3]
```

Iterate through values - three different ways
1. Using *range*
```py
>>> for i in range(len(A)):
        print(A[i], end=' ')
```

2. Using *in*
```py
>>> for num in A:
        print(num, end=' ')
```

3. Using *enumerate*
```py
>>> for i, num in enumerate(A):
        print(i, num)
```


3.1. Using *enumerate* with 1 as a starting index
```py
>>> for i, num in enumerate(A, 1):
        print(i, num)
```

#### Reverse Iteration
```py
>>> for i in reversed(range(len(A))):
        print(i, end=' ')
```

Reverse using step as -1
```py
>>> for i in range(10, -1, -1):
        print(i, end=' ')
```

#### Sorting
```py
>>> A = [(1, 2), (7, 5), (2, 4), (3, 6)]
>>> A.sort()
```

```py
>>> A = [(1, 2), (7, 5), (2, 4), (3, 6)]
>>> B = sorted(A)
```

##### Reversed sort

```py
>>> A = [(1, 2), (7, 5), (2, 4), (3, 6)]
>>> A.sort(reverse=True)
```

```py
>>> A = [(1, 2), (7, 5), (2, 4), (3, 6)]
>>> B = sorted(A, reverse=True)
```

##### Custom Sort

```py
[[1, 3], [1, 4], [2, 4], [3, 6], [4, 2], [7, 5]]
>>> A.sort(key=lambda x: x[1])
```

```py
A = ['aba', 'ABA', 'James', 'john', 'Andrew', 'lewis', 'Sol', 'Ben', 'Soo', 'jason']
A.sort(key=lambda s: s.lower())
```

### Tree Recursion

### Tree practice (Review)
- Create a tree class (IDLE)
- Create a tree
<pre>
         5
       /   \
      6     10
</pre>

- [Pre-order](https://www.hackerrank.com/challenges/tree-preorder-traversal/problem)
- [Post-order](https://www.hackerrank.com/challenges/tree-postorder-traversal/problem)
- [In-order](https://www.hackerrank.com/challenges/tree-inorder-traversal)
- [Level-order](https://www.hackerrank.com/challenges/tree-level-order-traversal)

### Height of tree
- [Get height of tree](https://www.hackerrank.com/challenges/tree-height-of-a-binary-tree/problem)

### Insert a node to Binary Search Tree
- [Binary Search Tree: Insertion](https://www.hackerrank.com/challenges/binary-search-tree-insertion)

### Lowest Common Ancestor
- [Binary Search Tree : Lowest Common Ancestor](https://www.hackerrank.com/challenges/binary-search-tree-lowest-common-ancestor)

### More tree problems
- [938. Range Num of BST](https://leetcode.com/problems/range-sum-of-bst/)
- [559. Maximum Depth of N-ary Tree](https://leetcode.com/problems/maximum-depth-of-n-ary-tree) - DFS and BFS
- [531. Find Bottom Left Tree Value](https://leetcode.com/problems/find-bottom-left-tree-value/)

### Note:
- https://www.hackerrank.com/topics/binary-search
- https://leetcode.com/tag/binary-search/
- https://www.hackerearth.com/practice/algorithms/searching/binary-search/practice-problems/
- https://www.interviewbit.com/courses/programming/topics/binary-search/#problems
- https://www.geeksforgeeks.org/tag/binary-search/

