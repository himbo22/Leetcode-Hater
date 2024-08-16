# Time: O(N) | Space: O(1)

```cpp
class Solution {
public:
    int maxDistance(vector<vector<int>>& arrays) {

        int res = 0;
        int max_value = arrays[0].back();
        int min_value = arrays[0][0];

        for (int i = 1; i < arrays.size(); i++) {
            int left = arrays[i][0];
            int right = arrays[i].back();
            res = max(res, max(max_value - left, right - min_value));
            min_value = min(min_value, left);
            max_value = max(max_value, right);
        }

        return res;
    }
};
```