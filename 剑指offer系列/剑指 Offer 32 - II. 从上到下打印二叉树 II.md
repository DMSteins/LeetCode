### [剑指 Offer 32 - II. 从上到下打印二叉树 II](https://leetcode.cn/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
从上到下按层打印二叉树，同一层的节点按从左到右的顺序打印，每一层打印到一行。
```

#### 解法思路
```
广度优先搜索
```

#### 题解

```JavaScript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrder = function(root) {
    if(!root) return []
    let stack = [root]
    let itemStack = []
    const res = []
    let itemRes = []
    while(stack.length > 0 || itemStack.length > 0){
        const node = stack.shift()
        if(node.left) itemStack.push(node.left)
        if(node.right) itemStack.push(node.right)
        itemRes.push(node.val)
        if(stack.length === 0){
            stack = itemStack
            itemStack = []
            res.push(itemRes)
            itemRes = []
        }
    }
    return res
};
```