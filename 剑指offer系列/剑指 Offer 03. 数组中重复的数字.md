### [剑指 Offer 03. 数组中重复的数字](https://leetcode.cn/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。
```

#### 解法思路
```

```

#### 题解

> 原地交换

```JavaScript
/**
 * @param {number[]} nums
 * @return {number}
 */
var findRepeatNumber = function(nums) {
    let i = 0
    while(i < nums.length){
        if(nums[i] === i){
            i++
            continue
        }
        if(nums[nums[i]] === nums[i]) return nums[i]
        const temp = nums[nums[i]]
        nums[nums[i]] = nums[i]
        nums[i] = temp
    }
    return -1
};
```

> 哈希 

```JavaScript
/**
 * @param {number[]} nums
 * @return {number}
 */
var findRepeatNumber = function(nums) {
    let arr = new Array(nums.length).fill(0)
    for(let i = 0; i < nums.length; i++){
        if(arr[nums[i]] > 0) return nums[i]
        arr[nums[i]]++
    }
    return -1
};
```