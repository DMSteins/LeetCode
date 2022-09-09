### [剑指 Offer 24. 反转链表](https://leetcode.cn/problems/fan-zhuan-lian-biao-lcof/)

> 难度：简单

#### 描述
```
定义一个函数，输入一个链表的头节点，反转该链表并输出反转后链表的头节点。
```

#### 解法思路
```
双指针迭代
```

#### 题解

```JavaScript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    let prev = null
    let cur = head
    while(cur){
        const next = cur.next
        cur.next = prev
        prev = cur
        cur = next
    }
    return prev
};
```