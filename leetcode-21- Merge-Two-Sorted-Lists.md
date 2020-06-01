# 21. Merge Two Sorted Lists
LeetCode / Easy

## 문제 설명
정렬된 두 개의 연결리스트를 정렬된 하나의 연결리스트로 합쳐라.
```
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```

## 풀이

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function(l1, l2) {
    let list = new ListNode(-1);
    let head = list;
    
    while (l1 && l2) {
        if (l1.val <= l2.val) {
            list.next = l1;
            l1 = l1.next;
        } else {
            list.next = l2;
            l2 = l2.next;
        }
        list = list.next;
    }
    
    if (l1) list.next = l1;
    else list.next = l2;
    
    return head.next;
    
};
```
