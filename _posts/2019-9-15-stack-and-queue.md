---
layout: post
title:Programming Challenges Week 15 - Practice Linked List
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

### Stack

#### HackerRank and LeetCode problems

##### Minimum Stack

##### Daily temperature

##### Calculator
