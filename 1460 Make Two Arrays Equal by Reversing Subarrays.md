```cpp
class Solution {
public:
    bool canBeEqual(vector<int>& target, vector<int>& arr) {
        unordered_map<int,int> mp;
        for(auto n:target){
            mp[n]++;
        }
        for(auto m:arr){
            // if found arr[i] in mp : mp.find(m) != mp.end() and mp[m] is equal 0
            // in other words, if m is still in arr then the size of m in target is not equal with the size of m in target, so that we return false
            // or, if we cannot found m in mp, just return false
            if((mp.find(m) != mp.end() && mp[m] == 0) || mp.find(m) == mp.end()) return false;
            mp[m]--;
        }
        return true;
    }
};
```