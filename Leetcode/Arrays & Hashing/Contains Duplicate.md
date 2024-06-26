---
tags:
  - CPP
  - Array
  - Hash-Table
  - Sorting
difficulty: Easy
---
# Problem Statement
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

**Input:** nums = [1,2,3,1]
**Output:** true

**Example 2:**

**Input:** nums = [1,2,3,4]
**Output:** false

**Example 3:**

**Input:** nums = [1,1,1,3,3,4,3,2,4,2]
**Output:** true

**Constraints:**

- `1 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`
# Solution
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> st;
        for (int num: nums)
        {
            if (st.count(num))
                return true;
            st.insert(num);
        }
        return false;
    }
};
```
# Comments
- **Time Complexity:** $O(n)$
- **Space Complexity:** $O(n)$
# Similar Questions
- [[Contains Duplicate II]].
- [[Contains Duplicate III]].
- [[Make Array Zero by Subtracting Equal Amounts]].