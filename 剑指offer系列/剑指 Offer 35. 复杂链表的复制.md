### [剑指 Offer 35. 复杂链表的复制](https://leetcode.cn/problems/fu-za-lian-biao-de-fu-zhi-lcof/)

> 难度：中等

#### 描述
```
请实现 copyRandomList 函数，复制一个复杂链表。在复杂链表中，每个节点除了有一个 next 指针指向下一个节点，还有一个 random 指针指向链表中的任意节点或者 null。
```

#### 解法思路
```
哈希表加迭代
```

#### 题解

```JavaScript
/**
 * // Definition for a Node.
 * function Node(val, next, random) {
 *    this.val = val;
 *    this.next = next;
 *    this.random = random;
 * };
 */

/**
 * @param {Node} head
 * @return {Node}
 */
var copyRandomList = function(head) {
    const hashMap = new Map()
    let copyHead = new Node()
    let prev = copyHead
    let node = null
    while(head){

        
        node = new Node()
        node.val = head.val
        node.random = head.random
        hashMap.set(head, node)
        
        copyHead.next = node
        copyHead = copyHead.next
        head = head.next
    }
    let curNode = prev
    while(curNode){
        if(curNode.random){
            curNode.random = hashMap.get(curNode.random)
        }
        curNode = curNode.next
    }
    return prev.next
};
```