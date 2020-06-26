# 21. 136. Single Number
LeetCode / Easy

## 문제 설명

주어진 정수 배열은 딱 하나의 숫자만 제외하고 같은 숫자가 두 번 나타난다.    
추가적인 메모리 사용 없이 O(n)의 시간 복잡도로 한번만 나타나는 숫자를 찾아보자.

```
Input: [2,2,1]
Output: 1
```

```
Input: [4,1,2,1,2]
Output: 4
```

## 풀이
### Set 사용한 풀이
```javascript
var singleNumber = function(nums) {
    const set = new Set();
    
    nums.forEach(n => {
        if (set.has(n)) {
            set.delete(n);
        } else {
            set.add(n);
        }
    })
    return set.values().next().value;
};
```
### XOR을 이용한 풀이
```javascript
var singleNumber = function(nums) {
    let result = 0;
    
    nums.forEach(n => {
        result ^= n;
    })
    
    return result;
};
```
