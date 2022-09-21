### [剑指 Offer 32 - I. 从上到下打印二叉树](https://leetcode.cn/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：中等

#### 描述
```
从上到下打印出二叉树的每个节点，同一层的节点按照从左到右的顺序打印。
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
 * @return {number[]}
 */
var levelOrder = function(root) {
    if(!root) return []
    const stack = []
    stack.push(root)
    const res = []
    while(stack.length > 0){
        const node = stack.shift()
        if(node.left) stack.push(node.left)
        if(node.right) stack.push(node.right)
        res.push(node.val)
    }
    return res
};
```