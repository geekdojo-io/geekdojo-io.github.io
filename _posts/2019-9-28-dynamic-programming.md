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
