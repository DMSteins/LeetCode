### [剑指 Offer 50. 第一个只出现一次的字符](https://leetcode.cn/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
在字符串 s 中找出第一个只出现一次的字符。如果没有，返回一个单空格。 s 只包含小写字母。
```

#### 解法思路
```
哈希表存储字符出现的次数
```

#### 题解

```JavaScript
/**
 * @param {string} s
 * @return {character}
 */
var firstUniqChar = function(s) {
    let charObj = {}
    for(let i = 0; i < s.length; i++){
        const char = s[i]
        if(charObj[char]){
            charObj[char]++
        }else{
            charObj[char] = 1
        }
    }

    for(let key in charObj){
        if(charObj[key] === 1){
            return key
        }
    }
    return ' '
};
```