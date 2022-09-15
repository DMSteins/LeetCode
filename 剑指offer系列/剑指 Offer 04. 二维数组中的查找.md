### [剑指 Offer 04. 二维数组中的查找](https://leetcode.cn/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：中等

#### 描述
```
在一个 n * m 的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个高效的函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。
```

#### 解法思路
```
二维数组从左向右递增，从上到下递增，所以矩阵右上角向左递减，向下递增，根据值的比较进行z形查找
```

#### 题解

```JavaScript
/**
 * @param {number[][]} matrix
 * @param {number} target
 * @return {boolean}
 */
var findNumberIn2DArray = function(matrix, target) {
    let m = matrix.length
    let n = m && matrix[0].length
    let x = 0, y = n - 1
    while(x < m && y >= 0){
        if(matrix[x][y] === target){
            return true
        }else if(matrix[x][y] > target){
            y--
        }else{
            x++
        }
    }
    return false
};
```