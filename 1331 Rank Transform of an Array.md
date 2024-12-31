**Time O(NLogN)
Space O(N)**

```cpp
vector<int> arrayRankTransform(vector<int>& arr) {
        unordered_map<int,int> mp;
        vector<int> res = arr;
        sort(arr.begin(),arr.end());
        int ranking = 1;
        for(int i=0;i<arr.size();i++) if(!mp.count(arr[i])) mp[arr[i]] = ranking++;
        
        for(int i=0;i<res.size();i++) res[i] = mp[res[i]];
        
        return res;
    }
```