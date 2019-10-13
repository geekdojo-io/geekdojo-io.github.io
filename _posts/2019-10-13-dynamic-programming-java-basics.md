---
layout: post
title: Java - Week 2 and Maze
---

### Review LeetCode Problem #2 - Weekly 158

### Maze

```py
# M: mouse
# C: cheese
# T: Trap
B = ['M..T....',
'........',
'..T.....',
'........',
'.T......',
'.TTTTTTT',
'...C....',
'........']

def printPath(path):
  for i in range(8):
    for j in range(8):
      if B[i][j] == 'M':
        print('M',end='')
      elif B[i][j] == 'C':
        print('C',end='')
      elif B[i][j] == 'T':
        print('T',end='')        
      elif (i,j) in path:
        print('*',end='')
      elif B[i][j] == 'M':
        print('M',end='')
      else:
        print('.',end='')
    print()
  print()

def dfs(row, col, path):
  if (row, col) == end:
    printPath(path)
    return
  visited.add((row,col))
  for d in [(0,1),(0,-1),(-1,0),(1,0)]:
    row2, col2 = row + d[0], col + d[1]
    if 0 <= row2 < 8 and 0 <= col2 < 8 and B[row2][col2] != 'T' and (row2,col2) not in visited:
      dfs(row2, col2, path + [(row2, col2)])


start = None
end = None
for i in range(len(B)):
  for j in range(len(B[0])):
    if B[i][j] == 'M':
      start = (i,j)
    elif B[i][j] == 'C':
      end = (i,j)

visited = set()
dfs(start[0], start[1], [start])
```

### Maze and Java

-- https://docs.google.com/presentation/d/1jsvHTAdILInUwDNUyhCuIHVUg4-zdi584LBRCTZKqWA/edit?usp=sharing
