## Problem : https://leetcode.com/problems/maximum-subarray/description/

## Approach — Kadane's Algorithm

Aapan array madhun ek-ek element traverse karu.

Pratyek element sathi don options astat:

1. Current subarray continue karaycha
2. Current element pasun navin subarray start karaycha

Mhanun:

```text
currentSum = max(nums[i], currentSum + nums[i])
```

Jar `currentSum` negative asel, tar to pudhe carry karnyapeksha current element pasun navin subarray start karne better.

### C++ Solution

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        // Pahilya element pasun currentSum ani maxSum initialize karu
        // 0 ne initialize karu naye, karan sagle numbers negative asu shaktat
        int currentSum = nums[0];
        int maxSum = nums[0];

        for (int i = 1; i < nums.size(); i++) {

            // Current subarray continue karaycha
            // kiwa current element pasun navin subarray start karaycha
            currentSum = max(nums[i], currentSum + nums[i]);

            // Aataparyant cha maximum sum update karu
            maxSum = max(maxSum, currentSum);
        }

        return maxSum;
    }
};
```

### Complexity

* **Time:** `O(n)`
* **Space:** `O(1)`
