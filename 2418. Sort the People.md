# Approach 1:
Runtime O(N2) 
Memory O(1)
```cpp
class Solution {
public:
    vector<string> sortPeople(vector<string>& names, vector<int>& heights) {
        int n = names.size();
        for(int i=0;i<n-1;i++){
            for(int j=i+1;j<n;j++){
                if(heights[i] < heights[j]){
                    swap(heights[i],heights[j]);
                    swap(names[i],names[j]);
                }
            }
        }
        return names;
    }
};
```

# Approach 2:
Runtime O(N log N) 
Memory O(N)
```cpp
class Solution {
public:
    vector<string> sortPeople(vector<string>& names, vector<int>& heights) {
        vector<pair<int, string>> mp;
        for(int i=0;i<names.size();i++){
            mp.push_back(pair<int,string>(heights[i],names[i]));
        }
        sort(mp.begin(),mp.end(), greater<>());
        for(int i=0;i<names.size();i++){
            names[i] = mp[i].second;
        }
        return names;
    }
};
```