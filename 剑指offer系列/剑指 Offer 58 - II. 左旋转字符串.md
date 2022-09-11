### [剑指 Offer 58 - II. 左旋转字符串](https://leetcode.cn/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。
```

#### 解法思路
```
切片然后拼接
```

#### 题解

```JavaScript
/**
 * @param {string} s
 * @param {number} n
 * @return {string}
 */
var reverseLeftWords = function(s, n) {
    let word = ""
    for(let i = n; i < s.length; i++){
        word = word + s[i]
    }
    for(let i = 0; i < n; i++){
        word = word + s[i]
    }
    
    return word
};

```