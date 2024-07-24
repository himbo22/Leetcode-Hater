```c++
class Solution {
public:
    static bool cmp(const pair<int, int>& a, const pair<int, int>& b) {
        // key line
        return a.second == b.second ? a.first > b.first : a.second < b.second;
    }

    vector<int> frequencySort(vector<int>& nums) {
        unordered_map<int, int> mp;
        for (auto n : nums) {
            mp[n]++;
        }
        vector<pair<int, int>> temp;
        for (auto m : mp) {
            temp.push_back(m);
        }
        sort(temp.begin(), temp.end(), cmp);
        vector<int> res;
        for (auto& t : temp) {
            res.insert(res.end(), t.second, t.first);
        }
        return res;
    }
};
```