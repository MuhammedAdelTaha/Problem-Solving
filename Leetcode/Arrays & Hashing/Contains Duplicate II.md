---
tags:
  - CPP
  - Array
  - Hash-Table
  - Sliding-Window
difficulty: Easy
---
# Problem Statement
Given an integer array `nums` and an integer `k`, return `true` _if there are two **distinct indices**_ `i` _and_ `j` _in the array such that_ `nums[i] == nums[j]` _and_ `abs(i - j) <= k`.

**Example 1:**

**Input:** nums = [1,2,3,1], k = 3
**Output:** true

**Example 2:**

**Input:** nums = [1,0,1,1], k = 1
**Output:** true

**Example 3:**

**Input:** nums = [1,2,3,1,2,3], k = 2
**Output:** false
# Solution
```cpp
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        if (!k)
            return false;
        
        int n = nums.size();
        for (int i = 0; i < n - 1; i++)
            for (int j = i + 1; j <= i + k && j < n; j++)
                if (nums[i] == nums[j])
                    return true;

        return false;
    }
};
```
# Comments
- **Time Complexity:** $O(n^2)$
- **Space Complexity:** $O(1)$