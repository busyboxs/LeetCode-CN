# LCP 01. 猜数字

## 题目描述

小 A 和小 B 在玩猜数字。小 B 每次从 1, 2, 3 中随机选择一个，小 A 每次也从 1, 2, 3 中选择一个猜。他们一共进行三次这个游戏，请返回小 A 猜对了几次？ 

输入的 `guess` 数组为小 A 每次的猜测，`answer`数组为小 B 每次的选择。`guess` 和 `answer` 的长度都等于 `3`。


**示例 1：**

```
输入：guess = [1,2,3], answer = [1,2,3]
输出：3
解释：小A 每次都猜对了。
```

**示例 2：**

```
输入：guess = [2,2,3], answer = [3,2,1]
输出：1
解释：小A 只猜对了第二次。
```

**限制：**

* `guess 的长度 = 3`
* `answer 的长度 = 3`
* `guess` 的元素取值为 `{1, 2, 3}` 之一。
* `answer` 的元素取值为 `{1, 2, 3}` 之一。


## 题解

```cpp
class Solution {
public:
    int game(vector<int>& guess, vector<int>& answer) {
        int count = 0;
        for (int i = 0; i < guess.size(); ++i) {
            if (guess[i] == answer[i]) {
                count++;
            }
        }

        return count;
    }
};
```