```cpp
class Solution {
public:
    int countConsistentStrings(string allowed, vector<string>& words) {
        int c[26] = {0};
        int res = words.size();
        for(int i=0;i<allowed.size();i++){
            c[allowed[i] - 'a']++;
        }
        for(int i=0;i<words.size();i++){
            for(int j=0;j<words[i].size();j++){
                if(c[words[i][j]-'a'] == 0) {
                    res--;
                    break;
                }
            }
        }
        return res;
    }
};
```