Runtime: O()
Memory: O()

```cpp
class Solution {
public:
    int num(string s) {
        int res = 0;
        for (int i = 0; i < s.size(); i++) {
            res += pow(10, s.size() - 1 - i) * (s[i] - 'a');
        }
        return res;
    }
    bool isSumEqual(string f, string s, string t) {
        return num(f) + num(s) == num(t);
    }
};
```