### [剑指 Offer 06. 从尾到头打印链表](https://leetcode.cn/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。
```

#### 解法思路
```
链表特点，只能从前往后访问
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
 * @return {number[]}
 */
var reversePrint = function(head) {
    let res = []
    while(head){
        res.unshift(head.val)
        head = head.next
    }
    return res
};
```