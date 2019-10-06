---
layout: post
title:Programming Challenges Week 18 - Dynamic Programming and Introduction to Java
---

# Review Homework (20 min.)
- Clothes
- Tic-Tac-Toe

---

# Dynamic Programming

## Review DP

### Fibonacci numbers
- Review the last lecture

### Stair Case

#### Problem Statement*
Given a stair with ‘n’ steps, implement a method to count how many possible ways are there to reach the top of the staircase, given that, at every step you can either take 1 step, 2 steps, or 3 steps.

#### Example 1:
```
Number of stairs (n) : 3
Number of ways = 4
Explanation: Following are the four ways we can climb : {1,1,1}, {1,2}, {2,1}, {3} 
```

#### Example 2:
```
Number of stairs (n) : 4
Number of ways = 7
Explanation: Following are the seven ways we can climb : {1,1,1,1}, {1,1,2}, {1,2,1}, {2,1,1}, 
{2,2}, {1,3}, {3,1}
```

#### Solution
```py
def count_ways(n):
  dp = [0 for x in range(n+1)]
  dp[0] = 1
  dp[1] = 1
  dp[2] = 2

  for i in range(3, n+1):
    dp[i] = dp[i - 1] + dp[i - 2] + dp[i - 3]

  return dp[n]
```  

```py
def count_ways(n):
  if n < 2:
    return 1
  if n == 2:
    return 2
  n1, n2, n3 = 1, 1, 2
  for i in range(3, n+1):
    n1, n2, n3 = n2, n3, n1+n2+n3
  return n3
```  

### Minimum jumps to reach the end

#### Problem Statement
Given an array of positive numbers, where each element represents the max number of jumps that can be made forward from that element, write a program to find the minimum number of jumps needed to reach the end of the array (starting from the first element). If an element is 0, then we cannot move through that element.

#### Example 1:
```
Input = {2,1,1,1,4}
Output = 3
Explanation: Starting from index '0', we can reach the last index through: 0->2->3->4
```

#### Example 2:
```
Input = {1,1,3,6,9,3,0,1,3}
Output = 4
Explanation: Starting from index '0', we can reach the last index through: 0->1->2->3->8
```

#### Solution (Bottom-up):
```py
def count_min_jumps(jumps):
  n = len(jumps)
  # initialize with infinity, except the first index which should be zero as we
  # start from there
  dp = [math.inf for _ in range(n)]
  dp[0] = 0

  for start in range(n - 1):
    end = start + 1
    while end <= start + jumps[start] and end < n:
      dp[end] = min(dp[end], dp[start] + 1)
      end += 1

  return dp[n - 1]
```

---

# Java

Let's go to CodeAbby.com and create an account

## Sum-of-Two
```java
import java.util.*;

class SumAB {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        System.out.println(a+b);
        sc.close();
    }
}
```
## Sum-in-Loop
```py
_ = int(input())
res = sum(map(int, input().split()))
print(res)
```

```java
import java.util.*;

class SumInLoop {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();
        int sum = 0;
        while (T-- > 0) {
            sum += sc.nextInt();
        }
        System.out.println(sum);
        sc.close();
    }
}
```

## Sums in Loop

```java
import java.util.*;

class SumInLoop {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();
        while (T-- > 0) {
            int a = sc.nextInt();
            int b = sc.nextInt();
            System.out.printf("%d ", a + b);
        }
        sc.close();
    }
}
```
## Minimum of Two

```java
import java.util.*;

class MinOfTwo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();
        while (T-- > 0) {
            int a = sc.nextInt();
            int b = sc.nextInt();
            System.out.printf("%d ", Math.min(a, b));
        }
        sc.close();
    }
}
```
