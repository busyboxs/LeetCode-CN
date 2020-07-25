# 面试题 02.03. 删除中间节点

## 题目描述

实现一种算法，删除单向链表中间的某个节点（即不是第一个或最后一个节点），假定你只能访问该节点。

**示例：**

输入：单向链表 `a->b->c->d->e->f` 中的节点 `c`
结果：不返回任何数据，但该链表变为 `a->b->d->e->f`

## 题解

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    void deleteNode(ListNode* node) {
        node->val = node->next->val;
        node->next = node->next->next;
    }
};
```