# 771. 宝石与石头

## 题目描述

给定字符串 `J` 代表石头中宝石的类型，和字符串 `S` 代表你拥有的石头。 `S` 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

`J` 中的字母不重复，`J` 和 `S` 中的所有字符都是字母。字母区分大小写，因此 `"a"` 和 `"A"` 是不同类型的石头。

**示例 1:**

```
输入: J = "aA", S = "aAAbbbb"
输出: 3
```

**示例 2:**

```
输入: J = "z", S = "ZZ"
输出: 0
```

**注意:**

* `S` 和 `J` 最多含有 `50` 个字母。
* `J` 中的字符不重复。



## 题解

```cpp
class Solution {
public:
    int numJewelsInStones(string J, string S) {
        int amount[52] = { 0 };
        int ans = 0;
        for (int i = 0; i < S.size(); i++)
        {
            if (S[i] >= 'a')
                amount[S[i] - 'a']++;
            else
                amount[S[i] - 'A' + 26]++;
        }
        for (int i = 0; i < J.size(); i++)
        {
            if (J[i] >= 'a')
                ans += amount[J[i] - 'a'];
            else
                ans += amount[J[i] - 'A' + 26];
        }
        return ans;
    }
};
```