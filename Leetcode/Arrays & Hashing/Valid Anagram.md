---
tags:
  - CPP
  - Hash-Table
  - String
  - Sorting
difficulty: Easy
---
# Problem Statement
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** s = "anagram", t = "nagaram"
**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"
**Output:** false

**Constraints:**

- `1 <= s.length, t.length <= 5 * 104`
- `s` and `t` consist of lowercase English letters.

**Follow up:** What if the inputs contain Unicode characters? How would you adapt your solution to such a case?
# Solution
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        int n = s.size(), m = t.size();
        if (n != m) return false;

        vector<int> freq(26, 0);
        for (int i = 0; i < n; i++) {
            freq[s[i] - 'a']++; freq[t[i] - 'a']--;
        }
        for (int i = 0; i < 26; i++) {
            if (freq[i]) return false;
        }
        return true;
    }
};
```
# Comments
- **Time Complexity:** $O(n)$
- **Space Complexity:** $O(1)$
# Similar Questions
- [[Group Anagrams]]
- [[Palindrome Permutation]]
- [[Find All Anagrams in a String]]
- [[Find Resultant Array After Removing Anagrams]]