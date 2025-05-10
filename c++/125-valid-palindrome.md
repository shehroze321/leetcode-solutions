# [Leetcode 125: Valid Palindrome]
(https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/)

## Table of Contents
- [Approach 1: Brute Force](#approach-1-brute-force)

---

## Approach 1: Brute Force

### Intuition

The problem at hand is to determine the maximum profit we can get by making at most two transactions on given stock prices. A brute force method would involve exploring all combinations of two transactions to find the maximum possible profit. Each transaction involves buying on one day and selling on another subsequent day.

### Code



### Complexity Analysis

- **Time Complexity**: `O(n)`. We iterate through the prices in a linear fashion.
- **Space Complexity**: `O(n)`. Our DP table size is `n * 2 * 2`.

---

## Approach 3: Optimized Dynamic Programming

### Intuition

The space complexity of the previous approach can be further optimized. We observe that the DP table only requires information from the previous day. Thus, we can optimize the space used, converting it from `O(n)` to `O(1)` by using variables to track the previous state.

### Code

```cpp
// Optimized Dynamic Programming Approach with reduced space usage
// Time Complexity: O(n)
// Space Complexity: O(1)

#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    bool isPalindrome(string s) {
         int left = 0;
    int right = s.length() - 1;

    while (left < right) {
        while (left < right && !isalnum(s[left]))
            left++;
        while (left < right && !isalnum(s[right]))
            right--;

        if (tolower(s[left]) != tolower(s[right]))
            return false;

        left++;
        right--;
    }

    return true;
    }
};
```

### Complexity Analysis

- **Time Complexity**: `O(n)`. We traverse the prices once.
- **Space Complexity**: `O(1)`. We use only a fixed amount of space to track the profits.

In conclusion, transitioning from a brute-force method to an optimized dynamic programming solution increases the efficiency greatly, making it feasible to handle larger inputs efficiently.

