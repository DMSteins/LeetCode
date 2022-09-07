### [剑指 Offer 30. 包含min函数的栈](https://leetcode.cn/problems/bao-han-minhan-shu-de-zhan-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
定义栈的数据结构，请在该类型中实现一个能够得到栈的最小元素的 min 函数在该栈中，调用 min、push 及 pop 的时间复杂度都是 O(1)。
```

#### 解法思路
```
要让时间复杂度为O(1),主要问题是解决min
可以用另一个栈来存储当前栈的最小值
```

#### 题解

```JavaScript
/**
 * initialize your data structure here.
 */
var MinStack = function() {
    this.stack = []
    this.descStack = []
};

/** 
 * @param {number} x
 * @return {void}
 */
MinStack.prototype.push = function(x) {
    this.stack.push(x)
    if(this.descStack.length <= 0 || x <= this.descStack[this.descStack.length - 1]){
        this.descStack.push(x)
    }
};

/**
 * @return {void}
 */
MinStack.prototype.pop = function() {
    const val = this.stack.pop()
    if(val === this.descStack[this.descStack.length - 1]){
        this.descStack.pop()
    }
};

/**
 * @return {number}
 */
MinStack.prototype.top = function() {
    return this.stack[this.stack.length - 1]
};

/**
 * @return {number}
 */
MinStack.prototype.min = function() {
    return this.descStack[this.descStack.length - 1]
};

/**
 * Your MinStack object will be instantiated and called as such:
 * var obj = new MinStack()
 * obj.push(x)
 * obj.pop()
 * var param_3 = obj.top()
 * var param_4 = obj.min()
 */
```