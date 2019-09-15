---
layout: post
title:Programming Challenges Week 15 - Practice Linked List and Stack
---

### CodingBat
- Go to (CodingBat.com)[https://www.codingbat.com/python] and create an account and log into the website.
- Start to solve problems. If you are new, the [Warmup-1](https://codingbat.com/python/Warmup-1) is a good place to start.
- Let's solve problems in the CodingBat.com website for 45 minutes.
### Explore - Linked List Cycle

[Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)

#### Approach 1 - Hash Table
```py

class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        seen = set()
        cur = head
        while cur:
            if cur in seen:
                return True
            seen.add(cur)
            cur = cur.next
        return False
```        


#### Approach 2 - Two Poiners
```py

class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        slow = fast = head
        while slow and fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        return False
```

#### LinkedList - Explore

#### LinkedList - Summary

- Two Pointers (Fast & Slow)
- Iterate
- Reverse

#### HackerRank

- Python

https://www.hackerrank.com/domains/python?filters%5Bstatus%5D%5B%5D=unsolved&filters%5Bsubdomains%5D%5B%5D=py-sets&filters%5Bsubdomains%5D%5B%5D=py-collections&badge_type=python

### Stack

#### LeetCode problems

https://leetcode.com/explore/learn/card/queue-stack/230/usage-stack/1394/

##### (Minimum Stack)[https://leetcode.com/problems/min-stack/]

##### (Valid Parenthesis)[https://leetcode.com/problems/valid-parentheses/]

##### Daily temperature

##### Calculator
