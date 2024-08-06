# Time: O(N log N) & Space: O(N)

```cpp
int minimumPushes(string word) {
        unordered_map<char, int> freq;
        int res = 0;
        for (auto c : word) {
            freq[c]++;
        }
        vector<int> freqArray;
        for (auto f : freq) {
            freqArray.push_back(f.second);
        }
        sort(freqArray.begin(), freqArray.end(), greater<>());
        for (int i = 0; i < freqArray.size(); i++) {
            if (i < 8) {
                res += freqArray[i];
            } else if (i >= 8 && i < 16) {
                res += freqArray[i] * 2;
            } else if (i >= 16 && i < 24) {
                res += freqArray[i] * 3;
            } else {
                res += freqArray[i] * 4;
            }
        }
        return res;
    }
```

# Time: O(n) & Space: O(1)

```cpp
int minimumPushes(string word) {
        vector<int> freq(26, 0);
        int res = 0;
        for (auto c : word) {
            freq[c - 'a']++;
        }
        sort(freq.begin(), freq.end(), greater<>());
        for (int i = 0; i < freq.size(); i++) {
            res += freq[i] * (i / 8 + 1);
        }
        return res;
    }
```    