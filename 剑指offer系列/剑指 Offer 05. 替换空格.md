### [剑指 Offer 05. 替换空格](https://leetcode.cn/problems/ti-huan-kong-ge-lcof/?plan=lcof&plan_progress=zuo0mji)

> 难度：简单

#### 描述
```
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。
```

#### 解法思路
```

```

#### 题解

```JavaScript
/**
 * @param {string} s
 * @return {string}
 */
var replaceSpace = function(s) {
    let code = " ".charCodeAt()
    let strArr = s.split('')
    for(let i = 0; i < strArr.length; i++){
        if(strArr[i].charCodeAt() === code){
            strArr[i] = "%20"
        }
    }
    return strArr.join('')
};
```