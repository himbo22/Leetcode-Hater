```cpp
class Solution {
public:
    int rangeSum(vector<int>& nums, int n, int left, int right) {
        vector<int> newArray;
        for(int i=0;i<nums.size();i++){
            int sum = 0;
            for(int j=i;j<nums.size();j++){
                sum += nums[j];
                newArray.push_back(sum);
            }
        }
        sort(newArray.begin(),newArray.end());
        int res = 0;
        int mod = 1000000007;
        for(int i=left-1;i<right;i++) {
          // Ensure `res` always stays below `mod`
          res = (res + newArray[i]) % mod;
        }
        return res;
    }
};
```