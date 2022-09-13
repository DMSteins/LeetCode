### [剑指 Offer 53 - I. 在排序数组中查找数字 I](https://leetcode.cn/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
统计一个数字在排序数组中出现的次数。
```

#### 解法思路
```
二分查找到target,然后向两边查找出现的次数
```

#### 题解

```JavaScript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    let index = binarySearch(nums, target, 0, nums.length - 1)
    if(index === -1) return 0
    let count = 0
    let i = index
    while(i < nums.length && nums[i] === target){
        i++
        count++
    }
    i = index
    while(i >= 0 && nums[i] === target){
        i--
        count++
    }
    return count - 1
};
var binarySearch = function(nums, target, left, right){
    while(right >= left){
        let mid = parseInt((right - left) / 2) + left
        if(nums[mid] === target){
            return mid
        }else if(nums[mid] > target){
            right = mid - 1
        }else if(nums[mid] < target){
            left = mid + 1
        }
    }
    return -1
}
```