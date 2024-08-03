```cpp
class Solution {
public:
    vector<int> sortJumbled(vector<int>& mapping, vector<int>& nums) {
        vector<pair<int, int>> mp;
        for (int i = 0; i < nums.size(); i++) {
            int newNumber = 0;
            int power = 0;
            int currentNumber = nums[i];
            while (currentNumber >= 0) {
                newNumber += pow(10, power) * mapping[currentNumber % 10];
                power++;
                if (currentNumber / 10 == 0){
                    break;
                } else {
                    currentNumber /= 10;
                }
            }
            mp.push_back(pair<int, int>(nums[i], newNumber));
        }
        sort(mp.begin(), mp.end(),
             [](auto& a, auto& b) { return a.second < b.second; });
        for (int i = 0; i < mp.size(); i++) {
            nums[i] = mp[i].first;
        }
        return nums;
    }
};
```
> not yet optimized