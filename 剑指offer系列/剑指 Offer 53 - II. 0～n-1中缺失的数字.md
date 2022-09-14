### [剑指 Offer 53 - II. 0～n-1中缺失的数字](https://leetcode.cn/problems/que-shi-de-shu-zi-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。
```

#### 解法思路
```
二分查找到第一个大于索引index的索引
```

#### 题解

```JavaScript
/**
 * @param {number[]} nums
 * @return {number}
 */
var missingNumber = function(nums) {
    let n = nums.length
    let left = 0, right = n - 1
    let ans = n
    while(left <= right){
        const mid = parseInt((right - left) / 2) + left
        if(nums[mid] > mid){
            right = mid - 1
            ans = mid
        }else{
            left = mid + 1
        }
    }
    return ans
};
```