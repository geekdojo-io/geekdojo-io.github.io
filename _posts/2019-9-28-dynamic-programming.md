---
layout: post
title:Programming Challenges Week 17 - Dynamic Programming
---

### Warm-up (20 min.)
- CodingBat (String-1)
- CodingBat (String-2)

---

### Dynamic Programming

#### Fibonacci number
- https://www.mathsisfun.com/numbers/fibonacci-sequence.html
- https://en.wikipedia.org/wiki/Fibonacci_number

##### Top-to-bottom Recursion
```py
def fib(n):
  global cnt
  cnt += 1
  if n < 2:
    return n
  else:
    return fib(n-1) + fib(n-2)

cnt = 0
ans = fib(20)
print(ans)
print('ticks', cnt)

```
- Time complexity: O(2^N)
- Space complexity: O(1)

##### Memoization using Hashtable

```py
def fib(n):
  global cnt
  cnt += 1

  if n in memo:
    return memo[n]
  if n < 2:
    return n
  else:
    memo[n] = fib(n-1) + fib(n-2)
    return memo[n]
    
cnt = 0
ans = fib(20)
print(ans)
print('ticks', cnt)    
```    
- Time complexity: O(N)
- Space complexity: O(N)

##### Dynamic Programming
```py
def fib(n):
  global cnt
  dp = [0]*(n+1)
  dp[1] = 1
  for i in range(2, n+1):
    cnt += 1
    dp[i] = dp[i-2] + dp[i-1]
  return dp[n]
  
cnt = 0
ans = fib(20)
print(ans)
print('ticks', cnt)
```
- Time complexity: O(N)
- Space complexity: O(N)

##### Bottom-up Recursion
```py
def fib(n):
  global cnt
  cnt += 1

  if n < 2:
    return n
  f1, f2 = 0, 1
  for i in range(2, n+1):
    cnt += 1
    tmp = f1 + f2
    f1 = f2
    f2 = tmp
  return f2
  ```
- Time complexity: O(N)
- Space complexity: O(1)

---
### Practice

1. Clothes - https://www.cs.plu.edu/~blahakd/HSProgrammingContest/Contest2019/ProblemsNovice2019.pdf 

#### Soluton
1.in
```py
2
6
mario logo (shirt)
red (pants)
hawaiian (shirt)
baggy (pants)
white (socks)
fancy (socks)
10
khaki (pants)
blueish green (shirt)
apple (shirt)
bright (socks)
blue (pants)
red (pants)
purple (socks)
ugly (shirt)
stupid (socks)
big red (pants)
```


main.py
```py
f = open('1.in','r')
T = int(f.readline())
for _ in range(T):
  n = int(f.readline())
  stack1, stack2, stack3 = [], [], []
  for _ in range(n):
    s = f.readline().strip()
    x = s.find('(shirt)')
    if x != -1:
      stack1.append(s[:x-1])
      continue
    x = s.find('(pants)')
    if x != -1:
      stack2.append(s[:x-1])
      continue
    x = s.find('(socks)')
    if x != -1:
      stack3.append(s[:x-1])
      continue
  
  while stack1 and stack2 and stack3:
    print('{}, {}, {}'.format(stack1.pop(), stack2.pop(), stack3.pop()))
  print('')
```  
```
