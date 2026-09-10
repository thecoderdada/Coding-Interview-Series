# Problem https://leetcode.com/problems/two-sum/description/

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        // Aapan pratyek number ani tyacha index HashMap madhe store karu
        unordered_map<int, int> umap;

        for (int i = 0; i < nums.size(); i++) {

            // Current number sobat target complete karnyasathi
            // aaplyala konta number pahije te shodhu
            int needed = target - nums[i];

            // Jar needed number aadhi HashMap madhe asel,
            // tar aaplyala answer milala
            if (umap.find(needed) != umap.end()) {
                return {umap[needed], i};
            }

            // Current number ani tyacha index HashMap madhe store karu
            umap[nums[i]] = i;
        }

        // Jar kontihi valid pair sapadli nahi tar empty vector return karu
        return {};
    }
};

```
