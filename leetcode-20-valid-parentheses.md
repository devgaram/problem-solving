# 20. Valid Parentheses
LeetCode / Easy

## 문제 설명
`'(', ')', '{', '}', '[', ']'` 로 구성된 문자열이 주어질 때, 올바른 패턴의 문자열인지 판별하라.

## 풀이

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    const stack = [];
    const obj = {
        '(': ')',
        '{': '}',
        '[': ']'
    };
    
    if (!s) return true;
    
    for (let i=0; i<s.length; i++) {
        if (obj[s[i]]) stack.push(obj[s[i]]);
        else {
            const last = stack.pop();
            if (last !== s[i]) return false;
        }
    }
    return stack.length === 0;
};


```
