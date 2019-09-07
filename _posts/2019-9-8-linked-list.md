---
layout: post
title: Practice Linked List
---

### Review of LeetCode

- Daily practice
- Have a break
- Revisit a problem and solve again

### Review of Linked List

[HackerRank video](https://www.youtube.com/watch?v=njTh_OwMljA)

```py
class Node:
  def __init__(self, x):
    self.val = x
    self.next = None

```

### Hackerrank problems
#### [Print the Elements of a Linked List](https://www.hackerrank.com/challenges/print-the-elements-of-a-linked-list/problem)
```py
def printLinkedList(head):
    tmp = head
    while tmp:
        print(tmp.data)
        tmp = tmp.next
```

#### [Insert a node at the head of a linked list](https://www.hackerrank.com/challenges/insert-a-node-at-the-head-of-a-linked-list/problem)
```py
def insertNodeAtHead(llist, data):
    # Write your code here
    new_node = SinglyLinkedList()
    new_node.data = data
    new_node.next = None

    if not llist:
        llist = new_node
        return llist
    new_node.next = llist
    llist = new_node
    return llist
```

[Reverse a linked list](https://www.hackerrank.com/challenges/reverse-a-linked-list/problem)
```py
def reverse(head):
    cur, prev, next = head, None, None
    while cur:
        next = cur.next
        cur.next = prev
        prev = cur
        cur = next
    return prev
```


### Practice
#### [Compare two linked list](https://www.hackerrank.com/challenges/compare-two-linked-lists/problem)
```py
def compare_lists(llist1, llist2):
    if not llist1 and not llist2:
        return True
    while llist1 or llist2:
        if not llist1 or not llist2:
            return False
        if llist1.data != llist2.data:
            return False
        llist1 = llist1.next ; llist2 = llist2.next
    return True
```
- [Middle of Linked List](https://leetcode.com/problems/middle-of-the-linked-list)
- [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)



#### Solutions
##### - https://leetcode.com/problems/middle-of-the-linked-list

##### Approach 1: Find the length
```py
class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        def findLength(head):
            cnt = 0
            cur = head
            while cur:
                cnt += 1
                cur = cur.next
            return cnt
        
        cur = head
        mid = findLength(head) // 2
        while mid > 0:
            cur = cur.next
            mid -= 1
        return cur
```
##### Approach 2: Turtle and Rabbit (Tortoise and Hare)
```py
class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        return slow
```        

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


### Review of Binary Search
